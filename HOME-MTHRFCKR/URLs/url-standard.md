# URL

Living Standard — Last Updated 23 November 2022

Participate:

[GitHub whatwg/url](https://github.com/whatwg/url) ([new issue](https://github.com/whatwg/url/issues/new), [open issues](https://github.com/whatwg/url/issues))

[Chat on Matrix](https://whatwg.org/chat)

Commits:

[GitHub whatwg/url/commits](https://github.com/whatwg/url/commits)

[Snapshot as of this commit](https://url.spec.whatwg.org/commit-snapshots/48f1e79e5d930bf95eaffbbe6c7ae5ed81d397a0/ "You can also press the 'y' key")

[@urlstandard](https://twitter.com/urlstandard)

Tests:

[web-platform-tests url/](https://github.com/web-platform-tests/wpt/tree/master/url) ([ongoing work](https://github.com/web-platform-tests/wpt/labels/url))

Translations (non-normative):

[日本語](https://triple-underscore.github.io/URL-ja.html)

## Abstract

The URL Standard defines URLs, domains, IP addresses, the `application/x-www-form-urlencoded` format, and their API.

## Table of Contents

1. [Goals](https://url.spec.whatwg.org//#goals)
2. [1 Infrastructure](https://url.spec.whatwg.org//#infrastructure)
    1. [1.1 Writing](https://url.spec.whatwg.org//#writing)
    2. [1.2 Parsers](https://url.spec.whatwg.org//#parsers)
    3. [1.3 Percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-bytes)
3. [2 Security considerations](https://url.spec.whatwg.org//#security-considerations)
4. [3 Hosts (domains and IP addresses)](https://url.spec.whatwg.org//#hosts-(domains-and-ip-addresses))
    1. [3.1 Host representation](https://url.spec.whatwg.org//#host-representation)
    2. [3.2 Host miscellaneous](https://url.spec.whatwg.org//#host-miscellaneous)
    3. [3.3 IDNA](https://url.spec.whatwg.org//#idna)
    4. [3.4 Host writing](https://url.spec.whatwg.org//#host-writing)
    5. [3.5 Host parsing](https://url.spec.whatwg.org//#host-parsing)
    6. [3.6 Host serializing](https://url.spec.whatwg.org//#host-serializing)
    7. [3.7 Host equivalence](https://url.spec.whatwg.org//#host-equivalence)
5. [4 URLs](https://url.spec.whatwg.org//#urls)
    1. [4.1 URL representation](https://url.spec.whatwg.org//#url-representation)
    2. [4.2 URL miscellaneous](https://url.spec.whatwg.org//#url-miscellaneous)
    3. [4.3 URL writing](https://url.spec.whatwg.org//#url-writing)
    4. [4.4 URL parsing](https://url.spec.whatwg.org//#url-parsing)
    5. [4.5 URL serializing](https://url.spec.whatwg.org//#url-serializing)
    6. [4.6 URL equivalence](https://url.spec.whatwg.org//#url-equivalence)
    7. [4.7 Origin](https://url.spec.whatwg.org//#origin)
    8. [4.8 URL rendering](https://url.spec.whatwg.org//#url-rendering)
        1. [4.8.1 Simplify non-human-readable or irrelevant components](https://url.spec.whatwg.org//#url-rendering-simplification)
        2. [4.8.2 Elision](https://url.spec.whatwg.org//#url-rendering-elision)
        3. [4.8.3 Internationalization and special characters](https://url.spec.whatwg.org//#url-rendering-i18n)
6. [5 `application/x-www-form-urlencoded`](https://url.spec.whatwg.org//#application/x-www-form-urlencoded)
    1. [5.1 `application/x-www-form-urlencoded` parsing](https://url.spec.whatwg.org//#urlencoded-parsing)
    2. [5.2 `application/x-www-form-urlencoded` serializing](https://url.spec.whatwg.org//#urlencoded-serializing)
    3. [5.3 Hooks](https://url.spec.whatwg.org//#urlencoded-hooks)
7. [6 API](https://url.spec.whatwg.org//#api)
    1. [6.1 URL class](https://url.spec.whatwg.org//#url-class)
    2. [6.2 URLSearchParams class](https://url.spec.whatwg.org//#interface-urlsearchparams)
    3. [6.3 URL APIs elsewhere](https://url.spec.whatwg.org//#url-apis-elsewhere)
8. [Acknowledgments](https://url.spec.whatwg.org//#acknowledgments)
9. [Intellectual property rights](https://url.spec.whatwg.org//#ipr)
10. [Index](https://url.spec.whatwg.org//#index)
    1.  [Terms defined by this specification](https://url.spec.whatwg.org//#index-defined-here)
    2.  [Terms defined by reference](https://url.spec.whatwg.org//#index-defined-elsewhere)
11. [References](https://url.spec.whatwg.org//#references)
    1.  [Normative References](https://url.spec.whatwg.org//#normative)
    2.  [Informative References](https://url.spec.whatwg.org//#informative)
12. [IDL Index](https://url.spec.whatwg.org//#idl-index)

## Goals

The URL standard takes the following approach towards making URLs fully interoperable:

- Align RFC 3986 and RFC 3987 with contemporary implementations and obsolete them in the process. (E.g., spaces, other "illegal" code points, query encoding, equality, canonicalization, are all concepts not entirely shared, or defined.) URL parsing needs to become as solid as HTML parsing. [[RFC3986]](https://url.spec.whatwg.org//#biblio-rfc3986) [[RFC3987]](https://url.spec.whatwg.org//#biblio-rfc3987)

- Standardize on the term URL. URI and IRI are just confusing. In practice a single algorithm is used for both so keeping them distinct is not helping anyone. URL also easily wins the [search result popularity contest](https://trends.google.com/trends/explore?q=url,uri).

- Supplanting [Origin of a URI [sic]](https://tools.ietf.org/html/rfc6454#section-4). [[RFC6454]](https://url.spec.whatwg.org//#biblio-rfc6454)

- Define URL’s existing JavaScript API in full detail and add enhancements to make it easier to work with. Add a new `[URL](https://url.spec.whatwg.org//#url)` object as well for URL manipulation without usage of HTML elements. (Useful for JavaScript worker environments.)

- Ensure the combination of parser, serializer, and API guarantee idempotence. For example, a non-failure result of a parse-then-serialize operation will not change with any further parse-then-serialize operations applied to it. Similarly, manipulating a non-failure result through the API will not change from applying any number of serialize-then-parse operations to it.

As the editors learn more about the subject matter the goals might increase in scope somewhat.

## 1. Infrastructure[](https://url.spec.whatwg.org//#infrastructure)

This specification depends on the Infra Standard. [[INFRA]](https://url.spec.whatwg.org//#biblio-infra)

Some terms used in this specification are defined in the following standards and specifications:

- DOM Standard [[DOM]](https://url.spec.whatwg.org//#biblio-dom)
- Encoding Standard [[../BOOKMRKS-MTHRFCKR/Software-Tools/encoding.md]](https://url.spec.whatwg.org//#biblio-encoding)
- File API [[FILEAPI]](https://url.spec.whatwg.org//#biblio-fileapi)
- HTML Standard [[HTML]](https://url.spec.whatwg.org//#biblio-html)
- Media Source Extensions [[MEDIA-SOURCE]](https://url.spec.whatwg.org//#biblio-media-source)
- Unicode IDNA Compatibility Processing [[UTS46]](https://url.spec.whatwg.org//#biblio-uts46)
- Web IDL [[WEBIDL]](https://url.spec.whatwg.org//#biblio-webidl)

---

To serialize an integer, represent it as the shortest possible decimal number.

### 1.1. Writing[](https://url.spec.whatwg.org//#writing)

A validation error indicates a mismatch between input and valid input. User agents, especially conformance checkers, are encouraged to report them somewhere.

A [validation error](https://url.spec.whatwg.org//#validation-error) does not mean that the parser terminates. Termination of a parser is always stated explicitly, e.g., through a return statement.

It is useful to signal [validation errors](https://url.spec.whatwg.org//#validation-error) as error-handling can be non-intuitive, legacy user agents might not implement correct error-handling, and the intent of what is written might be unclear to other developers.

### 1.2. Parsers[](https://url.spec.whatwg.org//#parsers)

The EOF code point is a conceptual code point that signifies the end of a string or code point stream.

A pointer for a [string](https://infra.spec.whatwg.org/#string) input is an integer that points to a [code point](https://infra.spec.whatwg.org/#code-point) within input. Initially it points to the start of input. If it is −1 it points nowhere. If it is greater than or equal to input’s [code point length](https://infra.spec.whatwg.org/#string-code-point-length), it points to the [EOF code point](https://url.spec.whatwg.org//#eof-code-point).

When a [pointer](https://url.spec.whatwg.org//#pointer) is used, c references the [code point](https://infra.spec.whatwg.org/#code-point) the [pointer](https://url.spec.whatwg.org//#pointer) points to as long as it does not point nowhere. When the [pointer](https://url.spec.whatwg.org//#pointer) points to nowhere [c](https://url.spec.whatwg.org//#c) cannot be used.

When a [pointer](https://url.spec.whatwg.org//#pointer) is used, remaining references the [code point substring](https://infra.spec.whatwg.org/#code-point-substring-to-the-end-of-the-string) from the [pointer](https://url.spec.whatwg.org//#pointer) + 1 to the end of the string, as long as [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point). When [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point) [remaining](https://url.spec.whatwg.org//#remaining) cannot be used.

[](https://url.spec.whatwg.org//#example-12672b6a)If "`mailto:username@example`" is a [string](https://infra.spec.whatwg.org/#string) being processed and a [pointer](https://url.spec.whatwg.org//#pointer) points to @, [c](https://url.spec.whatwg.org//#c) is U+0040 (@) and [remaining](https://url.spec.whatwg.org//#remaining) is "`example`".

[](https://url.spec.whatwg.org//#example-empty-string)If the empty string is being processed and a [pointer](https://url.spec.whatwg.org//#pointer) points to the start and is then decreased by 1, using [c](https://url.spec.whatwg.org//#c) or [remaining](https://url.spec.whatwg.org//#remaining) would be an error.

### 1.3. Percent-encoded bytes[](https://url.spec.whatwg.org//#percent-encoded-bytes)

A percent-encoded byte is U+0025 (%), followed by two [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit). Sequences of [percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte), [percent-decoded](https://url.spec.whatwg.org//#string-percent-decode), should not cause [UTF-8 decode without BOM or fail](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom-or-fail) to return failure.

To percent-encode a [byte](https://infra.spec.whatwg.org/#byte) byte, return a [string](https://infra.spec.whatwg.org/#string) consisting of U+0025 (%), followed by two [ASCII upper hex digits](https://infra.spec.whatwg.org/#ascii-upper-hex-digit) representing byte.

To percent-decode a [byte sequence](https://infra.spec.whatwg.org/#byte-sequence) input, run these steps:

Using anything but [UTF-8 decode without BOM](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom) when input contains bytes that are not [ASCII bytes](https://infra.spec.whatwg.org/#ascii-byte) might be insecure and is not recommended.

1. Let output be an empty [byte sequence](https://infra.spec.whatwg.org/#byte-sequence).

2. For each byte byte in input:

    1. If byte is not 0x25 (%), then append byte to output.

    2. Otherwise, if byte is 0x25 (%) and the next two bytes after byte in input are not in the ranges 0x30 (0) to 0x39 (9), 0x41 (A) to 0x46 (F), and 0x61 (a) to 0x66 (f), all inclusive, append byte to output.

    3. Otherwise:

        1. Let bytePoint be the two bytes after byte in input, [decoded](https://infra.spec.whatwg.org/#isomorphic-decode), and then interpreted as hexadecimal number.

        2. Append a byte whose value is bytePoint to output.

        3. Skip the next two bytes in input.

3. Return output.

To percent-decode a [string](https://infra.spec.whatwg.org/#string) input, run these steps:

1. Let bytes be the [UTF-8 encoding](https://encoding.spec.whatwg.org/#utf-8-encode) of input.

2. Return the [percent-decoding](https://url.spec.whatwg.org//#percent-decode) of bytes.

In general, percent-encoding results in a string with more U+0025 (%) code points than the input, and percent-decoding results in a byte sequence with less 0x25 (%) bytes than the input.

---

The C0 control percent-encode set are the [C0 controls](https://infra.spec.whatwg.org/#c0-control) and all [code points](https://infra.spec.whatwg.org/#code-point) greater than U+007E (~).

The fragment percent-encode set is the [C0 control percent-encode set](https://url.spec.whatwg.org//#c0-control-percent-encode-set) and U+0020 SPACE, U+0022 ("), U+003C (<), U+003E (>), and U+0060 (`).

The query percent-encode set is the [C0 control percent-encode set](https://url.spec.whatwg.org//#c0-control-percent-encode-set) and U+0020 SPACE, U+0022 ("), U+0023 (#), U+003C (<), and U+003E (>).

The [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set) cannot be defined in terms of the [fragment percent-encode set](https://url.spec.whatwg.org//#fragment-percent-encode-set) due to the omission of U+0060 (`).

The special-query percent-encode set is the [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set) and U+0027 (').

The path percent-encode set is the [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set) and U+003F (?), U+0060 (`), U+007B ({), and U+007D (}).

The userinfo percent-encode set is the [path percent-encode set](https://url.spec.whatwg.org//#path-percent-encode-set) and U+002F (/), U+003A (:), U+003B (;), U+003D (=), U+0040 (@), U+005B ([) to U+005E (^), inclusive, and U+007C (|).

The component percent-encode set is the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set) and U+0024 ($) to U+0026 (&), inclusive, U+002B (+), and U+002C (,).

This is used by HTML for `[registerProtocolHandler()](https://html.spec.whatwg.org/multipage/system-state.html#dom-navigator-registerprotocolhandler)`, and could also be used by other standards to percent-encode data that can then be embedded in a [URL](https://url.spec.whatwg.org//#concept-url)’s [path](https://url.spec.whatwg.org//#concept-url-path), [query](https://url.spec.whatwg.org//#concept-url-query), or [fragment](https://url.spec.whatwg.org//#concept-url-fragment); or in an [opaque host](https://url.spec.whatwg.org//#opaque-host). Using it with [UTF-8 percent-encode](https://url.spec.whatwg.org//#string-utf-8-percent-encode) gives identical results to JavaScript’s [`encodeURIComponent()` [sic]](https://tc39.es/ecma262/#sec-encodeuricomponent-uricomponent). [[HTML]](https://url.spec.whatwg.org//#biblio-html) [[ECMA-262]](https://url.spec.whatwg.org//#biblio-ecma-262)

The `application/x-www-form-urlencoded` percent-encode set is the [component percent-encode set](https://url.spec.whatwg.org//#component-percent-encode-set) and U+0021 (!), U+0027 (') to U+0029 RIGHT PARENTHESIS, inclusive, and U+007E (~).

The [`application/x-www-form-urlencoded` percent-encode set](https://url.spec.whatwg.org//#application-x-www-form-urlencoded-percent-encode-set) contains all code points, except the [ASCII alphanumeric](https://infra.spec.whatwg.org/#ascii-alphanumeric), U+002A (*), U+002D (-), U+002E (.), and U+005F (_).

To percent-encode after encoding, given an [encoding](https://encoding.spec.whatwg.org/#encoding) encoding, [string](https://infra.spec.whatwg.org/#string) input, a percentEncodeSet, and an optional boolean spaceAsPlus (default false), run these steps:

1. Let encoder be the result of [getting an encoder](https://encoding.spec.whatwg.org/#get-an-encoder) from encoding.

2. Let inputQueue be input converted to an [I/O queue](https://encoding.spec.whatwg.org/#concept-stream).

3. Let output be the empty string.

4. Let potentialError be 0.

    This needs to be a non-null value to initiate the subsequent while loop.

5. While potentialError is non-null:

    1. Let encodeOutput be an empty [I/O queue](https://encoding.spec.whatwg.org/#concept-stream).

    2. Set potentialError to the result of running [encode or fail](https://encoding.spec.whatwg.org/#encode-or-fail) with inputQueue, encoder, and encodeOutput.

    3. For each byte of encodeOutput converted to a byte sequence:

        1. If spaceAsPlus is true and byte is 0x20 (SP), then append U+002B (+) to output and [continue](https://infra.spec.whatwg.org/#iteration-continue).

        2. Let isomorph be a [code point](https://infra.spec.whatwg.org/#code-point) whose [value](https://infra.spec.whatwg.org/#code-point-value) is byte’s [value](https://infra.spec.whatwg.org/#byte-value).

        3. Assert: percentEncodeSet includes all non-[ASCII code points](https://infra.spec.whatwg.org/#ascii-code-point).

        4. If isomorph is not in percentEncodeSet, then append isomorph to output.

        5. Otherwise, [percent-encode](https://url.spec.whatwg.org//#percent-encode) byte and append the result to output.

    4. If potentialError is non-null, then append "`%26%23`", followed by the shortest sequence of [ASCII digits](https://infra.spec.whatwg.org/#ascii-digit) representing potentialError in base ten, followed by "`%3B`", to output.

        This can happen when encoding is not [UTF-8](https://encoding.spec.whatwg.org/#utf-8).

6. Return output.

To UTF-8 percent-encode a [code point](https://infra.spec.whatwg.org/#code-point) codePoint using a percentEncodeSet, return the result of running [percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with [UTF-8](https://encoding.spec.whatwg.org/#utf-8), codePoint as a [string](https://infra.spec.whatwg.org/#string), and percentEncodeSet.

To UTF-8 percent-encode a [string](https://infra.spec.whatwg.org/#string) input using a percentEncodeSet, return the result of running [percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with [UTF-8](https://encoding.spec.whatwg.org/#utf-8), input, and percentEncodeSet.

---

[](https://url.spec.whatwg.org//#example-percent-encode-operations)

Here is a summary, by way of example, of the operations defined above:

| Operation | Input | Output |
| --- | --- | --- |
| [Percent-encode](https://url.spec.whatwg.org//#percent-encode) input | 0x23 | "`%23`" |
| 0x7F | "`%7F`" |
| [Percent-decode](https://url.spec.whatwg.org//#percent-decode) input | ``%25%s%1G`` | ``%%s%1G`` |
| [Percent-decode](https://url.spec.whatwg.org//#string-percent-decode) input | "`‽%25%2E`" | 0xE2 0x80 0xBD 0x25 0x2E |
| [Percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with [Shift_JIS](https://encoding.spec.whatwg.org/#shift_jis), input, and the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set) | " " | "`%20`" |
| "`≡`" | "`%81%DF`" |
| "`‽`" | "`%26%238253%3B`" |
| [Percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with [ISO-2022-JP](https://encoding.spec.whatwg.org/#iso-2022-jp), input, and the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set) | "`¥`" | "`%1B(J\%1B(B`" |
| [Percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with [Shift_JIS](https://encoding.spec.whatwg.org/#shift_jis), input, the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set), and true | "`1+1 ≡ 2%20‽`" | "`1+1+%81%DF+2%20%26%238253%3B`" |
| [UTF-8 percent-encode](https://url.spec.whatwg.org//#utf-8-percent-encode) input using the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set) | U+2261 (≡) | "`%E2%89%A1`" |
| U+203D (‽) | "`%E2%80%BD`" |
| [UTF-8 percent-encode](https://url.spec.whatwg.org//#string-utf-8-percent-encode) input using the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set) | "`Say what‽`" | "`Say%20what%E2%80%BD`" |

## 2. Security considerations[](https://url.spec.whatwg.org//#security-considerations)

The security of a [URL](https://url.spec.whatwg.org//#concept-url) is a function of its environment. Care is to be taken when rendering, interpreting, and passing [URLs](https://url.spec.whatwg.org//#concept-url) around.

When rendering and allocating new [URLs](https://url.spec.whatwg.org//#concept-url) "spoofing" needs to be considered. An attack whereby one [host](https://url.spec.whatwg.org//#concept-host) or [URL](https://url.spec.whatwg.org//#concept-url) can be confused for another. For instance, consider how 1/l/I, m/rn/rri, 0/O, and а/a can all appear eerily similar. Or worse, consider how U+202A LEFT-TO-RIGHT EMBEDDING and similar [code points](https://infra.spec.whatwg.org/#code-point) are invisible. [[UTR36]](https://url.spec.whatwg.org//#biblio-utr36)

When passing a [URL](https://url.spec.whatwg.org//#concept-url) from party A to B, both need to carefully consider what is happening. A might end up leaking data it does not want to leak. B might receive input it did not expect and take an action that harms the user. In particular, B should never trust A, as at some point [URLs](https://url.spec.whatwg.org//#concept-url) from A can come from untrusted sources.

## 3. Hosts (domains and IP addresses)[](https://url.spec.whatwg.org//#hosts-(domains-and-ip-addresses))

At a high level, a [host](https://url.spec.whatwg.org//#concept-host), [valid host string](https://url.spec.whatwg.org//#valid-host-string), [host parser](https://url.spec.whatwg.org//#concept-host-parser), and [host serializer](https://url.spec.whatwg.org//#concept-host-serializer) relate as follows:

- The [host parser](https://url.spec.whatwg.org//#concept-host-parser) takes an arbitrary string and returns either failure or a [host](https://url.spec.whatwg.org//#concept-host).

- A [host](https://url.spec.whatwg.org//#concept-host) can be seen as the in-memory representation.

- A [valid host string](https://url.spec.whatwg.org//#valid-host-string) defines what input would not trigger a [validation error](https://url.spec.whatwg.org//#validation-error) or failure when given to the [host parser](https://url.spec.whatwg.org//#concept-host-parser). I.e., input that would be considered conforming or valid.

- The [host serializer](https://url.spec.whatwg.org//#concept-host-serializer) takes a [host](https://url.spec.whatwg.org//#concept-host) and returns a string. (If that string is then [parsed](https://url.spec.whatwg.org//#concept-host-parser), the result will [equal](https://url.spec.whatwg.org//#concept-host-equals) the [host](https://url.spec.whatwg.org//#concept-host) that was [serialized](https://url.spec.whatwg.org//#concept-host-serializer).)

[](https://url.spec.whatwg.org//#example-host-parsing)

A [parse](https://url.spec.whatwg.org//#concept-host-parser)-[serialize](https://url.spec.whatwg.org//#concept-host-serializer) roundtrip gives the following results, depending on the isNotSpecial argument to the [host parser](https://url.spec.whatwg.org//#concept-host-parser):

| Input | Output (isNotSpecial = false) | Output (isNotSpecial = true) |
| --- | --- | --- |
| `EXAMPLE.COM` | `example.com` ([domain](https://url.spec.whatwg.org//#concept-domain)) | `EXAMPLE.COM` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `example%2Ecom` | `example%2Ecom` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `faß.example` | `xn--fa-hia.example` ([domain](https://url.spec.whatwg.org//#concept-domain)) | `fa%C3%9F.example` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `0` | `0.0.0.0` ([IPv4](https://url.spec.whatwg.org//#concept-ipv4)) | `0` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `%30` | `%30` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `0x` | `0x` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `0xffffffff` | `255.255.255.255` ([IPv4](https://url.spec.whatwg.org//#concept-ipv4)) | `0xffffffff` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `[0:0::1]` | `[::1]` ([IPv6](https://url.spec.whatwg.org//#concept-ipv6)) |
| `[0:0::1%5D` | Failure |
| `[0:0::%31]` |
| `09` | Failure | `09` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `example.255` | `example.255` ([opaque host](https://url.spec.whatwg.org//#opaque-host)) |
| `example^example` | Failure |

### 3.1. Host representation[](https://url.spec.whatwg.org//#host-representation)

A host is a [domain](https://url.spec.whatwg.org//#concept-domain), an [IP address](https://url.spec.whatwg.org//#ip-address), an [opaque host](https://url.spec.whatwg.org//#opaque-host), or an [empty host](https://url.spec.whatwg.org//#empty-host). Typically a [host](https://url.spec.whatwg.org//#concept-host) serves as a network address, but it is sometimes used as opaque identifier in [URLs](https://url.spec.whatwg.org//#concept-url) where a network address is not necessary.

[](https://url.spec.whatwg.org//#example-opaque-host-url)A typical [URL](https://url.spec.whatwg.org//#concept-url) whose [host](https://url.spec.whatwg.org//#concept-url-host) is an [opaque host](https://url.spec.whatwg.org//#opaque-host) is `git://github.com/whatwg/url.git`.

The RFCs referenced in the paragraphs below are for informative purposes only. They have no influence on [host](https://url.spec.whatwg.org//#concept-host) writing, parsing, and serialization. Unless stated otherwise in the sections that follow.

A domain is a non-empty [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that identifies a realm within a network. [[RFC1034]](https://url.spec.whatwg.org//#biblio-rfc1034)

The `example.com` and `example.com.` [domains](https://url.spec.whatwg.org//#concept-domain) are not equivalent and typically treated as distinct.

An IP address is an [IPv4 address](https://url.spec.whatwg.org//#concept-ipv4) or an [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6).

An IPv4 address is a 32-bit unsigned integer that identifies a network address. [[RFC791]](https://url.spec.whatwg.org//#biblio-rfc791)

An IPv6 address is a 128-bit unsigned integer that identifies a network address. For the purposes of this standard it is represented as a [list](https://infra.spec.whatwg.org/#list) of eight 16-bit unsigned integers, also known as IPv6 pieces. [[RFC4291]](https://url.spec.whatwg.org//#biblio-rfc4291)

Support for `<zone_id>` is [intentionally omitted](https://www.w3.org/Bugs/Public/show_bug.cgi?id=27234#c2).

An opaque host is a non-empty [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that can be used for further processing.

An empty host is the empty string.

### 3.2. Host miscellaneous[](https://url.spec.whatwg.org//#host-miscellaneous)

A forbidden host code point is U+0000 NULL, U+0009 TAB, U+000A LF, U+000D CR, U+0020 SPACE, U+0023 (#), U+002F (/), U+003A (:), U+003C (<), U+003E (>), U+003F (?), U+0040 (@), U+005B ([), U+005C (\), U+005D (]), U+005E (^), or U+007C (|).

A forbidden domain code point is a [forbidden host code point](https://url.spec.whatwg.org//#forbidden-host-code-point), a [C0 control](https://infra.spec.whatwg.org/#c0-control), U+0025 (%), or U+007F DELETE.

A [host](https://url.spec.whatwg.org//#concept-host)’s public suffix is the portion of a [host](https://url.spec.whatwg.org//#concept-host) which is included on the Public Suffix List. To obtain host’s [public suffix](https://url.spec.whatwg.org//#host-public-suffix), run these steps: [[PSL]](https://url.spec.whatwg.org//#biblio-psl)

1. If host is not a [domain](https://url.spec.whatwg.org//#concept-domain), then return null.

2. Let trailingDot be "`.`" if host [ends with](https://infra.spec.whatwg.org/#string-ends-with) "`.`"; otherwise the empty string.

3. Let publicSuffix be the public suffix determined by running the [Public Suffix List algorithm](https://github.com/publicsuffix/list/wiki/Format#formal-algorithm) with host as domain. [[PSL]](https://url.spec.whatwg.org//#biblio-psl)

4. Assert: publicSuffix is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that does not [end with](https://infra.spec.whatwg.org/#string-ends-with) "`.`".

5. Return publicSuffix and trailingDot concatenated.

A [host](https://url.spec.whatwg.org//#concept-host)’s registrable domain is a [domain](https://url.spec.whatwg.org//#concept-domain) formed by the most specific public suffix, along with the domain label immediately preceding it, if any. To obtain host’s [registrable domain](https://url.spec.whatwg.org//#host-registrable-domain), run these steps:

1. If host’s [public suffix](https://url.spec.whatwg.org//#host-public-suffix) is null or host’s [public suffix](https://url.spec.whatwg.org//#host-public-suffix) [equals](https://url.spec.whatwg.org//#concept-host-equals) host, then return null.

2. Let trailingDot be "`.`" if host [ends with](https://infra.spec.whatwg.org/#string-ends-with) "`.`"; otherwise the empty string.

3. Let registrableDomain be the registrable domain determined by running the [Public Suffix List algorithm](https://github.com/publicsuffix/list/wiki/Format#formal-algorithm) with host as domain. [[PSL]](https://url.spec.whatwg.org//#biblio-psl)

4. Assert: registrableDomain is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that does not [end with](https://infra.spec.whatwg.org/#string-ends-with) "`.`".

5. Return registrableDomain and trailingDot concatenated.

[](https://url.spec.whatwg.org//#example-host-psl)

| Host input | Public suffix | Registrable domain |
| --- | --- | --- |
| `com` | `com` | null |
| `example.com` | `com` | `example.com` |
| `www.example.com` | `com` | `example.com` |
| `sub.www.example.com` | `com` | `example.com` |
| `EXAMPLE.COM` | `com` | `example.com` |
| `example.com.` | `com.` | `example.com.` |
| `github.io` | `github.io` | null |
| `whatwg.github.io` | `github.io` | `whatwg.github.io` |
| `إختبار` | `xn--kgbechtv` | null |
| `example.إختبار` | `xn--kgbechtv` | `example.xn--kgbechtv` |
| `sub.example.إختبار` | `xn--kgbechtv` | `example.xn--kgbechtv` |
| `[2001:0db8:85a3:0000:0000:8a2e:0370:7334]` | null | null |

Specifications should prefer the [origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin) concept for security decisions. The notion of "[public suffix](https://url.spec.whatwg.org//#host-public-suffix)" and "[registrable domain](https://url.spec.whatwg.org//#host-registrable-domain)" cannot be relied-upon to provide a hard security boundary, as the public suffix list will diverge from client to client. Specifications which ignore this advice are encouraged to carefully consider whether URLs' schemes ought to be incorporated into any decisions made, i.e. whether to use the [same site](https://html.spec.whatwg.org/multipage/browsers.html#same-site) or [schemelessly same site](https://html.spec.whatwg.org/multipage/browsers.html#schemelessly-same-site) concepts.

### 3.3. IDNA[](https://url.spec.whatwg.org//#idna)

The domain to ASCII algorithm, given a [string](https://infra.spec.whatwg.org/#string) domain and an optional boolean beStrict (default false), runs these steps:

1. Let result be the result of running [Unicode ToASCII](https://www.unicode.org/reports/tr46/#ToASCII) with *domain_name* set to domain, *UseSTD3ASCIIRules* set to beStrict, *CheckHyphens* set to false, *CheckBidi* set to true, *CheckJoiners* set to true, *Transitional_Processing* set to false, and *VerifyDnsLength* set to beStrict.

    If beStrict is false, domain is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string), and [strictly splitting](https://infra.spec.whatwg.org/#strictly-split) domain on U+002E (.) does not produce any [item](https://infra.spec.whatwg.org/#list-item) that [starts with](https://infra.spec.whatwg.org/#string-starts-with) an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for "`xn--`", this step is equivalent to [ASCII lowercasing](https://infra.spec.whatwg.org/#ascii-lowercase) domain.

2. If result is a failure value, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

3. If result is the empty string, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

4. Return result.

The domain to Unicode algorithm, given a [domain](https://url.spec.whatwg.org//#concept-domain) domain, runs these steps:

1. Let result be the result of running [Unicode ToUnicode](https://www.unicode.org/reports/tr46/#ToUnicode) with *domain_name* set to domain, *CheckHyphens* set to false, *CheckBidi* set to true, *CheckJoiners* set to true, *UseSTD3ASCIIRules* set to false, and *Transitional_Processing* set to false.

2. Signify [validation errors](https://url.spec.whatwg.org//#validation-error) for any returned errors, and then, return result.

### 3.4. Host writing[](https://url.spec.whatwg.org//#host-writing)

A valid host string must be a [valid domain string](https://url.spec.whatwg.org//#valid-domain-string), a [valid IPv4-address string](https://url.spec.whatwg.org//#valid-ipv4-address-string), or: U+005B ([), followed by a [valid IPv6-address string](https://url.spec.whatwg.org//#valid-ipv6-address-string), followed by U+005D (]).

A domain is a valid domain if these steps return success:

1. Let result be the result of running [domain to ASCII](https://url.spec.whatwg.org//#concept-domain-to-ascii) with domain and true.

2. If result is failure, then return failure.

3. Set result to the result of running [Unicode ToUnicode](https://www.unicode.org/reports/tr46/#ToUnicode) with *domain_name* set to result, *CheckHyphens* set to false, *CheckBidi* set to true, *CheckJoiners* set to true, *UseSTD3ASCIIRules* set to true, and *Transitional_Processing* set to false.

4. If result contains any errors, return failure.

5. Return success.

Ideally we define this in terms of a sequence of code points that make up a [valid domain](https://url.spec.whatwg.org//#valid-domain) rather than through a whack-a-mole: [issue 245](https://github.com/whatwg/url/issues/245).

A valid domain string must be a string that is a [valid domain](https://url.spec.whatwg.org//#valid-domain).

A valid IPv4-address string must be four shortest possible strings of [ASCII digits](https://infra.spec.whatwg.org/#ascii-digit), representing a decimal number in the range 0 to 255, inclusive, separated from each other by U+002E (.).

A valid IPv6-address string is defined in the ["Text Representation of Addresses" chapter of IP Version 6 Addressing Architecture](https://tools.ietf.org/html/rfc4291#section-2.2). [[RFC4291]](https://url.spec.whatwg.org//#biblio-rfc4291)

A valid opaque-host string must be one of the following:

- one or more [URL units](https://url.spec.whatwg.org//#url-units) excluding [forbidden host code points](https://url.spec.whatwg.org//#forbidden-host-code-point)

- U+005B ([), followed by a [valid IPv6-address string](https://url.spec.whatwg.org//#valid-ipv6-address-string), followed by U+005D (]).

This is not part of the definition of [valid host string](https://url.spec.whatwg.org//#valid-host-string) as it requires context to be distinguished.

### 3.5. Host parsing[](https://url.spec.whatwg.org//#host-parsing)

The host parser takes a string input with an optional boolean isNotSpecial (default false), and then runs these steps:

1. If input starts with U+005B ([), then:

    1. If input does not end with U+005D (]), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    2. Return the result of [IPv6 parsing](https://url.spec.whatwg.org//#concept-ipv6-parser) input with its leading U+005B ([) and trailing U+005D (]) removed.

2. If isNotSpecial is true, then return the result of [opaque-host parsing](https://url.spec.whatwg.org//#concept-opaque-host-parser) input.

3. Assert: input is not the empty string.

4. Let domain be the result of running [UTF-8 decode without BOM](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom) on the [percent-decoding](https://url.spec.whatwg.org//#string-percent-decode) of input.

    Alternatively [UTF-8 decode without BOM or fail](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom-or-fail) can be used, coupled with an early return for failure, as [domain to ASCII](https://url.spec.whatwg.org//#concept-domain-to-ascii) fails on U+FFFD (�).

5. Let asciiDomain be the result of running [domain to ASCII](https://url.spec.whatwg.org//#concept-domain-to-ascii) on domain.

6. If asciiDomain is failure, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

7. If asciiDomain contains a [forbidden domain code point](https://url.spec.whatwg.org//#forbidden-domain-code-point), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

8. If asciiDomain [ends in a number](https://url.spec.whatwg.org//#ends-in-a-number-checker), then return the result of [IPv4 parsing](https://url.spec.whatwg.org//#concept-ipv4-parser) asciiDomain.

9. Return asciiDomain.

---

The ends in a number checker takes a string input and then runs these steps:

1. Let parts be the result of [strictly splitting](https://infra.spec.whatwg.org/#strictly-split) input on U+002E (.).

2. If the last [item](https://infra.spec.whatwg.org/#list-item) in parts is the empty string, then:

    1. If parts’s [size](https://infra.spec.whatwg.org/#list-size) is 1, then return false.

    2. [Remove](https://infra.spec.whatwg.org/#list-remove) the last [item](https://infra.spec.whatwg.org/#list-item) from parts.

3. Let last be the last [item](https://infra.spec.whatwg.org/#list-item) in parts.

4. If last is non-empty and contains only [ASCII digits](https://infra.spec.whatwg.org/#ascii-digit), then return true.

    The erroneous input "`09`" will be caught by the [IPv4 parser](https://url.spec.whatwg.org//#concept-ipv4-parser) at a later stage.

5. If parsing last as an [IPv4 number](https://url.spec.whatwg.org//#ipv4-number-parser) does not return failure, then return true.

    This is equivalent to checking that last is "`0X`" or "`0x`", followed by zero or more [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit).

6. Return false.

The IPv4 parser takes a string input and then runs these steps:

1. Let validationError be false.

    This uses validationError to track [validation errors](https://url.spec.whatwg.org//#validation-error) to avoid reporting them before we are confident we want to parse input as an IPv4 address as the [host parser](https://url.spec.whatwg.org//#concept-host-parser) almost always invokes the [IPv4 parser](https://url.spec.whatwg.org//#concept-ipv4-parser).

2. Let parts be the result of [strictly splitting](https://infra.spec.whatwg.org/#strictly-split) input on U+002E (.).

3. If the last [item](https://infra.spec.whatwg.org/#list-item) in parts is the empty string, then:

    1. Set validationError to true.

    2. If parts’s [size](https://infra.spec.whatwg.org/#list-size) is greater than 1, then [remove](https://infra.spec.whatwg.org/#list-remove) the last [item](https://infra.spec.whatwg.org/#list-item) from parts.

4. If parts’s [size](https://infra.spec.whatwg.org/#list-size) is greater than 4, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

5. Let numbers be an empty [list](https://infra.spec.whatwg.org/#list).

6. [For each](https://infra.spec.whatwg.org/#list-iterate) part of parts:

    1. Let result be the result of [parsing](https://url.spec.whatwg.org//#ipv4-number-parser) part.

    2. If result is failure, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    3. If result[1] is true, then set validationError to true.

    4. [Append](https://infra.spec.whatwg.org/#list-append) result[0] to numbers.

7. If validationError is true, [validation error](https://url.spec.whatwg.org//#validation-error).

    At this point each part was parsed into a number and input will be treated as an IPv4 address (or failure). And therefore error reporting resumes.

8. If any item in numbers is greater than 255, [validation error](https://url.spec.whatwg.org//#validation-error).

9. If any but the last [item](https://infra.spec.whatwg.org/#list-item) in numbers is greater than 255, then return failure.

10. If the last [item](https://infra.spec.whatwg.org/#list-item) in numbers is greater than or equal to 256<sup>(5 − <var>numbers</var>’s <a data-link-type="dfn" href="https://infra.spec.whatwg.org/#list-size" id="ref-for-list-size③">size</a>)</sup>, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

11. Let ipv4 be the last [item](https://infra.spec.whatwg.org/#list-item) in numbers.

12. [Remove](https://infra.spec.whatwg.org/#list-remove) the last [item](https://infra.spec.whatwg.org/#list-item) from numbers.

13. Let counter be 0.

14. [For each](https://infra.spec.whatwg.org/#list-iterate) n of numbers:

    1.  Increment ipv4 by n × 256<sup>(3 − <var>counter</var>)</sup>.
        
    2.  Increment counter by 1.

15. Return ipv4.

The IPv4 number parser takes a string input and then runs these steps:

1. If input is the empty string, then return failure.

2. Let validationError be false.

3. Let R be 10.

4. If input contains at least two code points and the first two code points are either "`0X`" or "`0x`", then:

    1. Set validationError to true.

    2. Remove the first two code points from input.

    3. Set R to 16.

5. Otherwise, if input contains at least two code points and the first code point is U+0030 (0), then:

    1. Set validationError to true.

    2. Remove the first code point from input.

    3. Set R to 8.

6. If input is the empty string, then return (0, true).

7. If input contains a code point that is not a radix-R digit, then return failure.

8. Let output be the mathematical integer value that is represented by input in radix-R notation, using [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit) for digits with values 0 through 15.

9. Return (output, validationError).

---

The IPv6 parser takes a string input and then runs these steps:

1. Let address be a new [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6) whose [IPv6 pieces](https://url.spec.whatwg.org//#concept-ipv6-piece) are all 0.

2. Let pieceIndex be 0.

3. Let compress be null.

4. Let pointer be a [pointer](https://url.spec.whatwg.org//#pointer) for input.

5. If [c](https://url.spec.whatwg.org//#c) is U+003A (:), then:

    1. If [remaining](https://url.spec.whatwg.org//#remaining) does not start with U+003A (:), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    2. Increase pointer by 2.

    3. Increase pieceIndex by 1 and then set compress to pieceIndex.

6. While [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

    1. If pieceIndex is 8, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    2. If [c](https://url.spec.whatwg.org//#c) is U+003A (:), then:

        1. If compress is non-null, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        2. Increase pointer and pieceIndex by 1, set compress to pieceIndex, and then [continue](https://infra.spec.whatwg.org/#iteration-continue).
    3. Let value and length be 0.

    4. While length is less than 4 and [c](https://url.spec.whatwg.org//#c) is an [ASCII hex digit](https://infra.spec.whatwg.org/#ascii-hex-digit), set value to value × 0x10 + [c](https://url.spec.whatwg.org//#c) interpreted as hexadecimal number, and increase pointer and length by 1.

    5. If [c](https://url.spec.whatwg.org//#c) is U+002E (.), then:

        1. If length is 0, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        2. Decrease pointer by length.

        3. If pieceIndex is greater than 6, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        4. Let numbersSeen be 0.

        5. While [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

            1. Let ipv4Piece be null.

            2. If numbersSeen is greater than 0, then:

                1. If [c](https://url.spec.whatwg.org//#c) is a U+002E (.) and numbersSeen is less than 4, then increase pointer by 1.

                2. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.
            3. If [c](https://url.spec.whatwg.org//#c) is not an [ASCII digit](https://infra.spec.whatwg.org/#ascii-digit), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

            4. While [c](https://url.spec.whatwg.org//#c) is an [ASCII digit](https://infra.spec.whatwg.org/#ascii-digit):

                1. Let number be [c](https://url.spec.whatwg.org//#c) interpreted as decimal number.

                2. If ipv4Piece is null, then set ipv4Piece to number.

                    Otherwise, if ipv4Piece is 0, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

                    Otherwise, set ipv4Piece to ipv4Piece × 10 + number.

                3. If ipv4Piece is greater than 255, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

                4. Increase pointer by 1.

            5. Set address[pieceIndex] to address[pieceIndex] × 0x100 + ipv4Piece.

            6. Increase numbersSeen by 1.

            7. If numbersSeen is 2 or 4, then increase pieceIndex by 1.

        6. If numbersSeen is not 4, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        7. [Break](https://infra.spec.whatwg.org/#iteration-break).

    6. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+003A (:):

        1. Increase pointer by 1.

        2. If [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    7. Otherwise, if [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    8. Set address[pieceIndex] to value.

    9. Increase pieceIndex by 1.

7. If compress is non-null, then:

    1. Let swaps be pieceIndex − compress.

    2. Set pieceIndex to 7.

    3. While pieceIndex is not 0 and swaps is greater than 0, swap address[pieceIndex] with address[compress + swaps − 1], and then decrease both pieceIndex and swaps by 1.

8. Otherwise, if compress is null and pieceIndex is not 8, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

9. Return address.

---

The opaque-host parser takes a string input, and then runs these steps:

1. If input contains a [forbidden host code point](https://url.spec.whatwg.org//#forbidden-host-code-point), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

2. If input contains a [code point](https://infra.spec.whatwg.org/#code-point) that is not a [URL code point](https://url.spec.whatwg.org//#url-code-points) and not U+0025 (%), [validation error](https://url.spec.whatwg.org//#validation-error).

3. If input contains a U+0025 (%) and the two [code points](https://infra.spec.whatwg.org/#code-point) following it are not [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit), [validation error](https://url.spec.whatwg.org//#validation-error).

4. Return the result of running [UTF-8 percent-encode](https://url.spec.whatwg.org//#string-utf-8-percent-encode) on input using the [C0 control percent-encode set](https://url.spec.whatwg.org//#c0-control-percent-encode-set).

### 3.6. Host serializing[](https://url.spec.whatwg.org//#host-serializing)

The host serializer takes a [host](https://url.spec.whatwg.org//#concept-host) host and then runs these steps:

1. If host is an [IPv4 address](https://url.spec.whatwg.org//#concept-ipv4), return the result of running the [IPv4 serializer](https://url.spec.whatwg.org//#concept-ipv4-serializer) on host.

2. Otherwise, if host is an [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6), return U+005B ([), followed by the result of running the [IPv6 serializer](https://url.spec.whatwg.org//#concept-ipv6-serializer) on host, followed by U+005D (]).

3. Otherwise, host is a [domain](https://url.spec.whatwg.org//#concept-domain), [opaque host](https://url.spec.whatwg.org//#opaque-host), or [empty host](https://url.spec.whatwg.org//#empty-host), return host.

The IPv4 serializer takes an [IPv4 address](https://url.spec.whatwg.org//#concept-ipv4) address and then runs these steps:

1. Let output be the empty string.

2. Let n be the value of address.

3. [For each](https://infra.spec.whatwg.org/#list-iterate) i in the range 1 to 4, inclusive:

    1. Prepend n % 256, [serialized](https://url.spec.whatwg.org//#serialize-an-integer), to output.

    2. If i is not 4, then prepend U+002E (.) to output.

    3. Set n to floor(n / 256).

4. Return output.

The IPv6 serializer takes an [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6) address and then runs these steps:

1. Let output be the empty string.

2. Let compress be an index to the first [IPv6 piece](https://url.spec.whatwg.org//#concept-ipv6-piece) in the first longest sequences of address’s [IPv6 pieces](https://url.spec.whatwg.org//#concept-ipv6-piece) that are 0.

    [](https://url.spec.whatwg.org//#example-e2b3492e)In `0:f:0:0:f:f:0:0` it would point to the second 0.

3. If there is no sequence of address’s [IPv6 pieces](https://url.spec.whatwg.org//#concept-ipv6-piece) that are 0 that is longer than 1, then set compress to null.

4. Let ignore0 be false.

5. [For each](https://infra.spec.whatwg.org/#list-iterate) pieceIndex in the range 0 to 7, inclusive:

    1. If ignore0 is true and address[pieceIndex] is 0, then [continue](https://infra.spec.whatwg.org/#iteration-continue).

    2. Otherwise, if ignore0 is true, set ignore0 to false.

    3. If compress is pieceIndex, then:

        1. Let separator be "`::`" if pieceIndex is 0, and U+003A (:) otherwise.

        2. Append separator to output.

        3. Set ignore0 to true and [continue](https://infra.spec.whatwg.org/#iteration-continue).

    4. Append address[pieceIndex], represented as the shortest possible lowercase hexadecimal number, to output.

    5. If pieceIndex is not 7, then append U+003A (:) to output.

6. Return output.

This algorithm requires the recommendation from A Recommendation for IPv6 Address Text Representation. [[RFC5952]](https://url.spec.whatwg.org//#biblio-rfc5952)

### 3.7. Host equivalence[](https://url.spec.whatwg.org//#host-equivalence)

To determine whether a [host](https://url.spec.whatwg.org//#concept-host) A equals [host](https://url.spec.whatwg.org//#concept-host) B, return true if A is B, and false otherwise.

Certificate comparison requires a host equivalence check that ignores the trailing dot of a domain (if any). However, those hosts have also various other facets enforced, such as DNS length, that are not enforced here, as URLs do not enforce them. If anyone has a good suggestion for how to bring these two closer together, or what a good unified model would be, please file an issue.

## 4. URLs[](https://url.spec.whatwg.org//#urls)

At a high level, a [URL](https://url.spec.whatwg.org//#concept-url), [valid URL string](https://url.spec.whatwg.org//#valid-url-string), [URL parser](https://url.spec.whatwg.org//#concept-url-parser), and [URL serializer](https://url.spec.whatwg.org//#concept-url-serializer) relate as follows:

- The [URL parser](https://url.spec.whatwg.org//#concept-url-parser) takes an arbitrary string and returns either failure or a [URL](https://url.spec.whatwg.org//#concept-url).

- A [URL](https://url.spec.whatwg.org//#concept-url) can be seen as the in-memory representation.

- A [valid URL string](https://url.spec.whatwg.org//#valid-url-string) defines what input would not trigger a [validation error](https://url.spec.whatwg.org//#validation-error) or failure when given to the [URL parser](https://url.spec.whatwg.org//#concept-url-parser). I.e., input that would be considered conforming or valid.

- The [URL serializer](https://url.spec.whatwg.org//#concept-url-serializer) takes a [URL](https://url.spec.whatwg.org//#concept-url) and returns an [ASCII string](https://infra.spec.whatwg.org/#ascii-string). (If that string is then [parsed](https://url.spec.whatwg.org//#concept-url-parser), the result will [equal](https://url.spec.whatwg.org//#concept-url-equals) the [URL](https://url.spec.whatwg.org//#concept-url) that was [serialized](https://url.spec.whatwg.org//#concept-url-serializer).)

[](https://url.spec.whatwg.org//#example-url-parsing)

| Input | Base | Valid | Output |
| --- | --- | --- | --- |
| `https:example.org` |  | ❌ | `https://example.org/` |
| `https://////example.com///` |  | ❌ | `https://example.com///` |
| `https://example.com/././foo` |  | ✅ | `https://example.com/foo` |
| `hello:world` | `https://example.com/` | ✅ | `hello:world` |
| `https:example.org` | `https://example.com/` | ❌ | `https://example.com/example.org` |
| `\example\..\demo/.\` | `https://example.com/` | ❌ | `https://example.com/demo/` |
| `example` | `https://example.com/demo` | ✅ | `https://example.com/example` |
| `file:///C|/demo` |  | ❌ | `file:///C:/demo` |
| `..` | `file:///C:/demo` | ✅ | `file:///C:/` |
| `file://loc%61lhost/` |  | ✅ | `file:///` |
| `https://user:password@example.org/` |  | ❌ | `https://user:password@example.org/` |
| `https://example.org/foo bar` |  | ❌ | `https://example.org/foo%20bar` |
| `https://EXAMPLE.com/../x` |  | ✅ | `https://example.com/x` |
| `https://ex ample.org/` |  | ❌ | Failure |
| `example` |  | ❌, due to lack of base | Failure |
| `https://example.com:demo` |  | ❌ | Failure |
| `http://[www.example.com]/` |  | ❌ | Failure |
| `https://example.org//` |  | ✅ | `https://example.org//` |

The base and output [URL](https://url.spec.whatwg.org//#concept-url) are represented in [serialized](https://url.spec.whatwg.org//#concept-url-serializer) form for brevity.

### 4.1. URL representation[](https://url.spec.whatwg.org//#url-representation)

A URL is a [struct](https://infra.spec.whatwg.org/#struct) that represents a universal identifier. To disambiguate from a [valid URL string](https://url.spec.whatwg.org//#valid-url-string) it can also be referred to as a [URL record](https://url.spec.whatwg.org//#concept-url).

A [URL](https://url.spec.whatwg.org//#concept-url)’s scheme is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that identifies the type of [URL](https://url.spec.whatwg.org//#concept-url) and can be used to dispatch a [URL](https://url.spec.whatwg.org//#concept-url) for further processing after [parsing](https://url.spec.whatwg.org//#concept-url-parser). It is initially the empty string.

A [URL](https://url.spec.whatwg.org//#concept-url)’s username is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) identifying a username. It is initially the empty string.

A [URL](https://url.spec.whatwg.org//#concept-url)’s password is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) identifying a password. It is initially the empty string.

A [URL](https://url.spec.whatwg.org//#concept-url)’s host is null or a [host](https://url.spec.whatwg.org//#concept-host). It is initially null.

The following table lists allowed [URL](https://url.spec.whatwg.org//#concept-url)’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) / [host](https://url.spec.whatwg.org//#concept-url-host) combinations.

| [scheme](https://url.spec.whatwg.org//#concept-url-scheme) | [host](https://url.spec.whatwg.org//#concept-url-host) |
| --- | --- |
| [domain](https://url.spec.whatwg.org//#concept-domain) | [IPv4 address](https://url.spec.whatwg.org//#concept-ipv4) | [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6) | [opaque host](https://url.spec.whatwg.org//#opaque-host) | [empty host](https://url.spec.whatwg.org//#empty-host) | null |
| [Special schemes](https://url.spec.whatwg.org//#special-scheme) excluding "`file`" | ✅ | ✅ | ✅ | ❌ | ❌ | ❌ |
| "`file`" | ✅ | ✅ | ✅ | ❌ | ✅ | ❌ |
| Others | ❌ | ❌ | ✅ | ✅ | ✅ | ✅ |

A [URL](https://url.spec.whatwg.org//#concept-url)’s port is either null or a 16-bit unsigned integer that identifies a networking port. It is initially null.

A [URL](https://url.spec.whatwg.org//#concept-url)’s path is either an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) or a [list](https://infra.spec.whatwg.org/#list) of zero or more [ASCII strings](https://infra.spec.whatwg.org/#ascii-string), usually identifying a location. It is initially « ».

A [special](https://url.spec.whatwg.org//#is-special) [URL](https://url.spec.whatwg.org//#concept-url)’s [path](https://url.spec.whatwg.org//#concept-url-path) is always a [list](https://infra.spec.whatwg.org/#list), i.e., it is never [opaque](https://url.spec.whatwg.org//#url-opaque-path).

A [URL](https://url.spec.whatwg.org//#concept-url)’s query is either null or an [ASCII string](https://infra.spec.whatwg.org/#ascii-string). It is initially null.

A [URL](https://url.spec.whatwg.org//#concept-url)’s fragment is either null or an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that can be used for further processing on the resource the [URL](https://url.spec.whatwg.org//#concept-url)’s other components identify. It is initially null.

A [URL](https://url.spec.whatwg.org//#concept-url) also has an associated blob URL entry that is either null or a [blob URL entry](https://w3c.github.io/FileAPI/#blob-url-entry). It is initially null.

This is used to support caching the object a "`blob`" URL refers to as well as its origin. It is important that these are cached as the [URL](https://url.spec.whatwg.org//#concept-url) might be removed from the [blob URL store](https://w3c.github.io/FileAPI/#BlobURLStore) between parsing and fetching, while fetching will still need to succeed.

[](https://url.spec.whatwg.org//#example-url-components)

The following table lists how [valid URL strings](https://url.spec.whatwg.org//#valid-url-string), when [parsed](https://url.spec.whatwg.org//#concept-url-parser), map to a [URL](https://url.spec.whatwg.org//#concept-url)’s components. [Username](https://url.spec.whatwg.org//#concept-url-username), [password](https://url.spec.whatwg.org//#concept-url-password), and [blob URL entry](https://url.spec.whatwg.org//#concept-url-blob-entry) are omitted; in the examples below they are the empty string, the empty string, and null, respectively.

| Input | [Scheme](https://url.spec.whatwg.org//#concept-url-scheme) | [Host](https://url.spec.whatwg.org//#concept-url-host) | [Port](https://url.spec.whatwg.org//#concept-url-port) | [Path](https://url.spec.whatwg.org//#concept-url-path) | [Query](https://url.spec.whatwg.org//#concept-url-query) | [Fragment](https://url.spec.whatwg.org//#concept-url-fragment) |
| --- | --- | --- | --- | --- | --- | --- |
| `https://example.com/` | "`https`" | "`example.com`" | null | « the empty string » | null | null |
| `https://localhost:8000/search?q=text#hello` | "`https`" | "`localhost`" | 8000 | « "`search`" » | "`q=text`" | "`hello`" |
| `urn:isbn:9780307476463` | "`urn`" | null | null | "`isbn:9780307476463`" | null | null |
| `file:///ada/Analytical%20Engine/README.md` | "`file`" | null | null | « "`ada`", "`Analytical%20Engine`", "`README.md`" » | null | null |

### 4.2. URL miscellaneous[](https://url.spec.whatwg.org//#url-miscellaneous)

A special scheme is an [ASCII string](https://infra.spec.whatwg.org/#ascii-string) that is listed in the first column of the following table. The default port for a [special scheme](https://url.spec.whatwg.org//#special-scheme) is listed in the second column on the same row. The [default port](https://url.spec.whatwg.org//#default-port) for any other [ASCII string](https://infra.spec.whatwg.org/#ascii-string) is null.

| [Special scheme](https://url.spec.whatwg.org//#special-scheme) | [Default port](https://url.spec.whatwg.org//#default-port) |
| --- | --- |
| "`ftp`" | 21 |
| "`file`" | null |
| "`http`" | 80 |
| "`https`" | 443 |
| "`ws`" | 80 |
| "`wss`" | 443 |

A [URL](https://url.spec.whatwg.org//#concept-url) is special if its [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is a [special scheme](https://url.spec.whatwg.org//#special-scheme). A [URL](https://url.spec.whatwg.org//#concept-url) is not special if its [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is not a [special scheme](https://url.spec.whatwg.org//#special-scheme).

A [URL](https://url.spec.whatwg.org//#concept-url) includes credentials if its [username](https://url.spec.whatwg.org//#concept-url-username) or [password](https://url.spec.whatwg.org//#concept-url-password) is not the empty string.

A [URL](https://url.spec.whatwg.org//#concept-url) has an opaque path if its [path](https://url.spec.whatwg.org//#concept-url-path) is a [string](https://infra.spec.whatwg.org/#string).

A [URL](https://url.spec.whatwg.org//#concept-url) cannot have a username/password/port if its [host](https://url.spec.whatwg.org//#concept-url-host) is null or the empty string, or its [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`".

A [URL](https://url.spec.whatwg.org//#concept-url) can be designated as base URL.

A [base URL](https://url.spec.whatwg.org//#concept-base-url) is useful for the [URL parser](https://url.spec.whatwg.org//#concept-url-parser) when the input might be a [relative-URL string](https://url.spec.whatwg.org//#relative-url-string).

---

A Windows drive letter is two code points, of which the first is an [ASCII alpha](https://infra.spec.whatwg.org/#ascii-alpha) and the second is either U+003A (:) or U+007C (|).

A normalized Windows drive letter is a [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter) of which the second code point is U+003A (:).

As per the [URL writing](https://url.spec.whatwg.org//#url-writing) section, only a [normalized Windows drive letter](https://url.spec.whatwg.org//#normalized-windows-drive-letter) is conforming.

A string starts with a Windows drive letter if all of the following are true:

- its [length](https://infra.spec.whatwg.org/#string-length) is greater than or equal to 2
- its first two code points are a [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter)
- its [length](https://infra.spec.whatwg.org/#string-length) is 2 or its third code point is U+002F (/), U+005C (\), U+003F (?), or U+0023 (#).

[](https://url.spec.whatwg.org//#example-start-with-a-widows-drive-letter)

| String | Starts with a Windows drive letter |
| --- | --- |
| "`c:`" | ✅ |
| "`c:/`" | ✅ |
| "`c:a`" | ❌ |

To shorten a url’s path:

1. [Assert](https://infra.spec.whatwg.org/#assert): url does not have an [opaque path](https://url.spec.whatwg.org//#url-opaque-path).

2. Let path be url’s [path](https://url.spec.whatwg.org//#concept-url-path).

3. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`", path’s [size](https://infra.spec.whatwg.org/#list-size) is 1, and path[0] is a [normalized Windows drive letter](https://url.spec.whatwg.org//#normalized-windows-drive-letter), then return.

4. [Remove](https://infra.spec.whatwg.org/#list-remove) path’s last item, if any.

### 4.3. URL writing[](https://url.spec.whatwg.org//#url-writing)

A valid URL string must be either a [relative-URL-with-fragment string](https://url.spec.whatwg.org//#relative-url-with-fragment-string) or an [absolute-URL-with-fragment string](https://url.spec.whatwg.org//#absolute-url-with-fragment-string).

An absolute-URL-with-fragment string must be an [absolute-URL string](https://url.spec.whatwg.org//#absolute-url-string), optionally followed by U+0023 (#) and a [URL-fragment string](https://url.spec.whatwg.org//#url-fragment-string).

An absolute-URL string must be one of the following:

- a [URL-scheme string](https://url.spec.whatwg.org//#url-scheme-string) that is an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for a [special scheme](https://url.spec.whatwg.org//#special-scheme) and not an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for "`file`", followed by U+003A (:) and a [scheme-relative-special-URL string](https://url.spec.whatwg.org//#scheme-relative-special-url-string)

- a [URL-scheme string](https://url.spec.whatwg.org//#url-scheme-string) that is *not* an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for a [special scheme](https://url.spec.whatwg.org//#special-scheme), followed by U+003A (:) and a [relative-URL string](https://url.spec.whatwg.org//#relative-url-string)

- a [URL-scheme string](https://url.spec.whatwg.org//#url-scheme-string) that is an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for "`file`", followed by U+003A (:) and a [scheme-relative-file-URL string](https://url.spec.whatwg.org//#scheme-relative-file-url-string)

any optionally followed by U+003F (?) and a [URL-query string](https://url.spec.whatwg.org//#url-query-string).

A URL-scheme string must be one [ASCII alpha](https://infra.spec.whatwg.org/#ascii-alpha), followed by zero or more of [ASCII alphanumeric](https://infra.spec.whatwg.org/#ascii-alphanumeric), U+002B (+), U+002D (-), and U+002E (.). [Schemes](https://url.spec.whatwg.org//#url-scheme-string) should be registered in the IANA URI [sic] Schemes registry. [[IANA-URI-SCHEMES]](https://url.spec.whatwg.org//#biblio-iana-uri-schemes) [[RFC7595]](https://url.spec.whatwg.org//#biblio-rfc7595)

A relative-URL-with-fragment string must be a [relative-URL string](https://url.spec.whatwg.org//#relative-url-string), optionally followed by U+0023 (#) and a [URL-fragment string](https://url.spec.whatwg.org//#url-fragment-string).

A relative-URL string must be one of the following, switching on [base URL](https://url.spec.whatwg.org//#concept-base-url)’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme):

A [special scheme](https://url.spec.whatwg.org//#special-scheme) that is not "`file`"

a [scheme-relative-special-URL string](https://url.spec.whatwg.org//#scheme-relative-special-url-string)

a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string)

a [path-relative-scheme-less-URL string](https://url.spec.whatwg.org//#path-relative-scheme-less-url-string)

"`file`"

a [scheme-relative-file-URL string](https://url.spec.whatwg.org//#scheme-relative-file-url-string)

a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string) if [base URL](https://url.spec.whatwg.org//#concept-base-url)’s [host](https://url.spec.whatwg.org//#concept-url-host) is an [empty host](https://url.spec.whatwg.org//#empty-host)

a [path-absolute-non-Windows-file-URL string](https://url.spec.whatwg.org//#path-absolute-non-windows-file-url-string) if [base URL](https://url.spec.whatwg.org//#concept-base-url)’s [host](https://url.spec.whatwg.org//#concept-url-host) is not an [empty host](https://url.spec.whatwg.org//#empty-host)

a [path-relative-scheme-less-URL string](https://url.spec.whatwg.org//#path-relative-scheme-less-url-string)

Otherwise

a [scheme-relative-URL string](https://url.spec.whatwg.org//#scheme-relative-url-string)

a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string)

a [path-relative-scheme-less-URL string](https://url.spec.whatwg.org//#path-relative-scheme-less-url-string)

any optionally followed by U+003F (?) and a [URL-query string](https://url.spec.whatwg.org//#url-query-string).

A non-null [base URL](https://url.spec.whatwg.org//#concept-base-url) is necessary when [parsing](https://url.spec.whatwg.org//#concept-url-parser) a [relative-URL string](https://url.spec.whatwg.org//#relative-url-string).

A scheme-relative-special-URL string must be "`//`", followed by a [valid host string](https://url.spec.whatwg.org//#valid-host-string), optionally followed by U+003A (:) and a [URL-port string](https://url.spec.whatwg.org//#url-port-string), optionally followed by a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string).

A URL-port string must be one of the following:

- the empty string

- one or more [ASCII digits](https://infra.spec.whatwg.org/#ascii-digit) representing a decimal number no greater than 2<sup>16</sup> − 1.

A scheme-relative-URL string must be "`//`", followed by an [opaque-host-and-port string](https://url.spec.whatwg.org//#opaque-host-and-port-string), optionally followed by a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string).

An opaque-host-and-port string must be either the empty string or: a [valid opaque-host string](https://url.spec.whatwg.org//#valid-opaque-host-string), optionally followed by U+003A (:) and a [URL-port string](https://url.spec.whatwg.org//#url-port-string).

A scheme-relative-file-URL string must be "`//`", followed by one of the following:

- a [valid host string](https://url.spec.whatwg.org//#valid-host-string), optionally followed by a [path-absolute-non-Windows-file-URL string](https://url.spec.whatwg.org//#path-absolute-non-windows-file-url-string)

- a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string).

A path-absolute-URL string must be U+002F (/) followed by a [path-relative-URL string](https://url.spec.whatwg.org//#path-relative-url-string).

A path-absolute-non-Windows-file-URL string must be a [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string) that does not start with: U+002F (/), followed by a [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter), followed by U+002F (/).

A path-relative-URL string must be zero or more [URL-path-segment strings](https://url.spec.whatwg.org//#url-path-segment-string), separated from each other by U+002F (/), and not start with U+002F (/).

A path-relative-scheme-less-URL string must be a [path-relative-URL string](https://url.spec.whatwg.org//#path-relative-url-string) that does not start with: a [URL-scheme string](https://url.spec.whatwg.org//#url-scheme-string), followed by U+003A (:).

A URL-path-segment string must be one of the following:

- zero or more [URL units](https://url.spec.whatwg.org//#url-units) excluding U+002F (/) and U+003F (?), that together are not a [single-dot path segment](https://url.spec.whatwg.org//#single-dot-path-segment) or a [double-dot path segment](https://url.spec.whatwg.org//#double-dot-path-segment).

- a [single-dot path segment](https://url.spec.whatwg.org//#single-dot-path-segment)

- a [double-dot path segment](https://url.spec.whatwg.org//#double-dot-path-segment).

A single-dot path segment must be "`.`" or an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for "`%2e`".

A double-dot path segment must be "`..`" or an [ASCII case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive) match for "`.%2e`", "`%2e.`", or "`%2e%2e`".

A URL-query string must be zero or more [URL units](https://url.spec.whatwg.org//#url-units).

A URL-fragment string must be zero or more [URL units](https://url.spec.whatwg.org//#url-units).

The URL code points are [ASCII alphanumeric](https://infra.spec.whatwg.org/#ascii-alphanumeric), U+0021 (!), U+0024 ($), U+0026 (&), U+0027 ('), U+0028 LEFT PARENTHESIS, U+0029 RIGHT PARENTHESIS, U+002A (*), U+002B (+), U+002C (,), U+002D (-), U+002E (.), U+002F (/), U+003A (:), U+003B (;), U+003D (=), U+003F (?), U+0040 (@), U+005F (_), U+007E (~), and [code points](https://infra.spec.whatwg.org/#code-point) in the range U+00A0 to U+10FFFD, inclusive, excluding [surrogates](https://infra.spec.whatwg.org/#surrogate) and [noncharacters](https://infra.spec.whatwg.org/#noncharacter).

Code points greater than U+007F DELETE will be converted to [percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte) by the [URL parser](https://url.spec.whatwg.org//#concept-url-parser).

In HTML, when the document encoding is a legacy encoding, code points in the [URL-query string](https://url.spec.whatwg.org//#url-query-string) that are higher than U+007F DELETE will be converted to [percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte) *using the document’s encoding*. This can cause problems if a URL that works in one document is copied to another document that uses a different document encoding. Using the [UTF-8](https://encoding.spec.whatwg.org/#utf-8) encoding everywhere solves this problem.

[](https://url.spec.whatwg.org//#query-encoding-example)

For example, consider this HTML document:

```
<!doctype html>
<meta charset="windows-1252">
<a href="?sm&ouml;rg&aring;sbord">Test</a>
```

Since the document encoding is windows-1252, the link’s [URL](https://url.spec.whatwg.org//#concept-url)’s [query](https://url.spec.whatwg.org//#concept-url-query) will be "`sm%F6rg%E5sbord`". If the document encoding had been UTF-8, it would instead be "`sm%C3%B6rg%C3%A5sbord`".

The URL units are [URL code points](https://url.spec.whatwg.org//#url-code-points) and [percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte).

[Percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte) can be used to encode code points that are not [URL code points](https://url.spec.whatwg.org//#url-code-points) or are excluded from being written.

---

There is no way to express a [username](https://url.spec.whatwg.org//#concept-url-username) or [password](https://url.spec.whatwg.org//#concept-url-password) of a [URL record](https://url.spec.whatwg.org//#concept-url) within a [valid URL string](https://url.spec.whatwg.org//#valid-url-string).

### 4.4. URL parsing[](https://url.spec.whatwg.org//#url-parsing)

The URL parser takes a string input, with an optional null or [base URL](https://url.spec.whatwg.org//#concept-base-url) base (default null) and an optional [encoding](https://encoding.spec.whatwg.org/#encoding) encoding (default [UTF-8](https://encoding.spec.whatwg.org/#utf-8)), and then runs these steps:

Non-web-browser implementations only need to implement the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser).

How user input in the web browser’s address bar is converted to a [URL record](https://url.spec.whatwg.org//#concept-url) is out-of-scope of this standard. This standard does include [URL rendering requirements](https://url.spec.whatwg.org//#url-rendering) as they pertain trust decisions.

1. Let url be the result of running the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser) on input with base and encoding.

2. If url is failure, return failure.

3. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is not "`blob`", return url.

4. Set url’s [blob URL entry](https://url.spec.whatwg.org//#concept-url-blob-entry) to the result of [resolving the blob URL](https://w3c.github.io/FileAPI/#blob-url-resolve) url, if that did not return failure, and null otherwise.

5. Return url.

---

The basic URL parser takes a string input, with an optional null or [base URL](https://url.spec.whatwg.org//#concept-base-url) base (default null), an optional [encoding](https://encoding.spec.whatwg.org/#encoding) encoding (default [UTF-8](https://encoding.spec.whatwg.org/#utf-8)), an optional [URL](https://url.spec.whatwg.org//#concept-url) url, and an optional state override state override, and then runs these steps:

The encoding argument is a legacy concept only relevant for HTML. The url and state override arguments are only for use by various APIs. [[HTML]](https://url.spec.whatwg.org//#biblio-html)

When the url and state override arguments are not passed, the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser) returns either a new [URL](https://url.spec.whatwg.org//#concept-url) or failure. If they are passed, the algorithm modifies the passed url and can terminate without returning anything.

1. If url is not given:

    1. Set url to a new [URL](https://url.spec.whatwg.org//#concept-url).

    2. If input contains any leading or trailing [C0 control or space](https://infra.spec.whatwg.org/#c0-control-or-space), [validation error](https://url.spec.whatwg.org//#validation-error).

    3. Remove any leading and trailing [C0 control or space](https://infra.spec.whatwg.org/#c0-control-or-space) from input.

2. If input contains any [ASCII tab or newline](https://infra.spec.whatwg.org/#ascii-tab-or-newline), [validation error](https://url.spec.whatwg.org//#validation-error).

3. Remove all [ASCII tab or newline](https://infra.spec.whatwg.org/#ascii-tab-or-newline) from input.

4. Let state be state override if given, or [scheme start state](https://url.spec.whatwg.org//#scheme-start-state) otherwise.

5. Set encoding to the result of [getting an output encoding](https://encoding.spec.whatwg.org/#get-an-output-encoding) from encoding.

6. Let buffer be the empty string.

7. Let atSignSeen, insideBrackets, and passwordTokenSeen be false.

8. Let pointer be a [pointer](https://url.spec.whatwg.org//#pointer) for input.

9. Keep running the following state machine by switching on state. If after a run pointer points to the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), go to the next step. Otherwise, increase pointer by 1 and continue with the state machine.

    scheme start state

    1. If [c](https://url.spec.whatwg.org//#c) is an [ASCII alpha](https://infra.spec.whatwg.org/#ascii-alpha), append [c](https://url.spec.whatwg.org//#c), [lowercased](https://infra.spec.whatwg.org/#ascii-lowercase), to buffer, and set state to [scheme state](https://url.spec.whatwg.org//#scheme-state).

    2. Otherwise, if state override is not given, set state to [no scheme state](https://url.spec.whatwg.org//#no-scheme-state) and decrease pointer by 1.

    3. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        This indication of failure is used exclusively by the `[Location](https://html.spec.whatwg.org/multipage/nav-history-apis.html#location)` object’s `[protocol](https://html.spec.whatwg.org/multipage/nav-history-apis.html#dom-location-protocol)` setter.

    scheme state

    1. If [c](https://url.spec.whatwg.org//#c) is an [ASCII alphanumeric](https://infra.spec.whatwg.org/#ascii-alphanumeric), U+002B (+), U+002D (-), or U+002E (.), append [c](https://url.spec.whatwg.org//#c), [lowercased](https://infra.spec.whatwg.org/#ascii-lowercase), to buffer.

    2. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+003A (:), then:

        1. If state override is given, then:

            1. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is a [special scheme](https://url.spec.whatwg.org//#special-scheme) and buffer is not a [special scheme](https://url.spec.whatwg.org//#special-scheme), then return.

            2. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is not a [special scheme](https://url.spec.whatwg.org//#special-scheme) and buffer is a [special scheme](https://url.spec.whatwg.org//#special-scheme), then return.

            3. If url [includes credentials](https://url.spec.whatwg.org//#include-credentials) or has a non-null [port](https://url.spec.whatwg.org//#concept-url-port), and buffer is "`file`", then return.

            4. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`" and its [host](https://url.spec.whatwg.org//#concept-url-host) is an [empty host](https://url.spec.whatwg.org//#empty-host), then return.

        2. Set url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) to buffer.

        3. If state override is given, then:

            1. If url’s [port](https://url.spec.whatwg.org//#concept-url-port) is url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme)’s [default port](https://url.spec.whatwg.org//#default-port), then set url’s [port](https://url.spec.whatwg.org//#concept-url-port) to null.

            2. Return.

        4. Set buffer to the empty string.

        5. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`", then:

            1. If [remaining](https://url.spec.whatwg.org//#remaining) does not start with "`//`", [validation error](https://url.spec.whatwg.org//#validation-error).

            2. Set state to [file state](https://url.spec.whatwg.org//#file-state).

        6. Otherwise, if url [is special](https://url.spec.whatwg.org//#is-special), base is non-null, and base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme):

            1. [Assert](https://infra.spec.whatwg.org/#assert): base is [is special](https://url.spec.whatwg.org//#is-special) (and therefore does not have an [opaque path](https://url.spec.whatwg.org//#url-opaque-path)).

            2. Set state to [special relative or authority state](https://url.spec.whatwg.org//#special-relative-or-authority-state).

        7. Otherwise, if url [is special](https://url.spec.whatwg.org//#is-special), set state to [special authority slashes state](https://url.spec.whatwg.org//#special-authority-slashes-state).

        8. Otherwise, if [remaining](https://url.spec.whatwg.org//#remaining) starts with an U+002F (/), set state to [path or authority state](https://url.spec.whatwg.org//#path-or-authority-state) and increase pointer by 1.

        9. Otherwise, set url’s [path](https://url.spec.whatwg.org//#concept-url-path) to the empty string and set state to [opaque path state](https://url.spec.whatwg.org//#cannot-be-a-base-url-path-state).

    3. Otherwise, if state override is not given, set buffer to the empty string, state to [no scheme state](https://url.spec.whatwg.org//#no-scheme-state), and start over (from the first code point in input).

    4. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        This indication of failure is used exclusively by the `[Location](https://html.spec.whatwg.org/multipage/nav-history-apis.html#location)` object’s `[protocol](https://html.spec.whatwg.org/multipage/nav-history-apis.html#dom-location-protocol)` setter. Furthermore, the non-failure termination earlier in this state is an intentional difference for defining that setter.

    no scheme state

    1. If base is null, or base has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path) and [c](https://url.spec.whatwg.org//#c) is not U+0023 (#), [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    2. Otherwise, if base has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path) and [c](https://url.spec.whatwg.org//#c) is U+0023 (#), set url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) to base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme), url’s [path](https://url.spec.whatwg.org//#concept-url-path) to base’s [path](https://url.spec.whatwg.org//#concept-url-path), url’s [query](https://url.spec.whatwg.org//#concept-url-query) to base’s [query](https://url.spec.whatwg.org//#concept-url-query), url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string, and set state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

    3. Otherwise, if base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is not "`file`", set state to [relative state](https://url.spec.whatwg.org//#relative-state) and decrease pointer by 1.

    4. Otherwise, set state to [file state](https://url.spec.whatwg.org//#file-state) and decrease pointer by 1.

    special relative or authority state

    1. If [c](https://url.spec.whatwg.org//#c) is U+002F (/) and [remaining](https://url.spec.whatwg.org//#remaining) starts with U+002F (/), then set state to [special authority ignore slashes state](https://url.spec.whatwg.org//#special-authority-ignore-slashes-state) and increase pointer by 1.

    2. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), set state to [relative state](https://url.spec.whatwg.org//#relative-state) and decrease pointer by 1.

    path or authority state

    1. If [c](https://url.spec.whatwg.org//#c) is U+002F (/), then set state to [authority state](https://url.spec.whatwg.org//#authority-state).

    2. Otherwise, set state to [path state](https://url.spec.whatwg.org//#path-state), and decrease pointer by 1.

    relative state

    1. Assert: base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is not "`file`".

    2. Set url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) to base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme).

    3. If [c](https://url.spec.whatwg.org//#c) is U+002F (/), then set state to [relative slash state](https://url.spec.whatwg.org//#relative-slash-state).

    4. Otherwise, if url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error), set state to [relative slash state](https://url.spec.whatwg.org//#relative-slash-state).

    5. Otherwise:

        1. Set url’s [username](https://url.spec.whatwg.org//#concept-url-username) to base’s [username](https://url.spec.whatwg.org//#concept-url-username), url’s [password](https://url.spec.whatwg.org//#concept-url-password) to base’s [password](https://url.spec.whatwg.org//#concept-url-password), url’s [host](https://url.spec.whatwg.org//#concept-url-host) to base’s [host](https://url.spec.whatwg.org//#concept-url-host), url’s [port](https://url.spec.whatwg.org//#concept-url-port) to base’s [port](https://url.spec.whatwg.org//#concept-url-port), url’s [path](https://url.spec.whatwg.org//#concept-url-path) to a [clone](https://infra.spec.whatwg.org/#list-clone) of base’s [path](https://url.spec.whatwg.org//#concept-url-path), and url’s [query](https://url.spec.whatwg.org//#concept-url-query) to base’s [query](https://url.spec.whatwg.org//#concept-url-query).

        2. If [c](https://url.spec.whatwg.org//#c) is U+003F (?), then set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string, and state to [query state](https://url.spec.whatwg.org//#query-state).

        3. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+0023 (#), set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

        4. Otherwise, if [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

            1. Set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to null.

            2. [Shorten](https://url.spec.whatwg.org//#shorten-a-urls-path) url’s [path](https://url.spec.whatwg.org//#concept-url-path).

            3. Set state to [path state](https://url.spec.whatwg.org//#path-state) and decrease pointer by 1.

    relative slash state

    1. If url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+002F (/) or U+005C (\), then:

        1. If [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. Set state to [special authority ignore slashes state](https://url.spec.whatwg.org//#special-authority-ignore-slashes-state).

    2. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+002F (/), then set state to [authority state](https://url.spec.whatwg.org//#authority-state).

    3. Otherwise, set url’s [username](https://url.spec.whatwg.org//#concept-url-username) to base’s [username](https://url.spec.whatwg.org//#concept-url-username), url’s [password](https://url.spec.whatwg.org//#concept-url-password) to base’s [password](https://url.spec.whatwg.org//#concept-url-password), url’s [host](https://url.spec.whatwg.org//#concept-url-host) to base’s [host](https://url.spec.whatwg.org//#concept-url-host), url’s [port](https://url.spec.whatwg.org//#concept-url-port) to base’s [port](https://url.spec.whatwg.org//#concept-url-port), state to [path state](https://url.spec.whatwg.org//#path-state), and then, decrease pointer by 1.

    special authority slashes state

    1. If [c](https://url.spec.whatwg.org//#c) is U+002F (/) and [remaining](https://url.spec.whatwg.org//#remaining) starts with U+002F (/), then set state to [special authority ignore slashes state](https://url.spec.whatwg.org//#special-authority-ignore-slashes-state) and increase pointer by 1.

    2. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), set state to [special authority ignore slashes state](https://url.spec.whatwg.org//#special-authority-ignore-slashes-state) and decrease pointer by 1.

    special authority ignore slashes state

    1. If [c](https://url.spec.whatwg.org//#c) is neither U+002F (/) nor U+005C (\), then set state to [authority state](https://url.spec.whatwg.org//#authority-state) and decrease pointer by 1.

    2. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error).

    authority state

    1. If [c](https://url.spec.whatwg.org//#c) is U+0040 (@), then:

        1. [Validation error](https://url.spec.whatwg.org//#validation-error).

        2. If atSignSeen is true, then prepend "`%40`" to buffer.

        3. Set atSignSeen to true.

        4. For each codePoint in buffer:

            1. If codePoint is U+003A (:) and passwordTokenSeen is false, then set passwordTokenSeen to true and [continue](https://infra.spec.whatwg.org/#iteration-continue).

            2. Let encodedCodePoints be the result of running [UTF-8 percent-encode](https://url.spec.whatwg.org//#utf-8-percent-encode) codePoint using the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set).

            3. If passwordTokenSeen is true, then append encodedCodePoints to url’s [password](https://url.spec.whatwg.org//#concept-url-password).

            4. Otherwise, append encodedCodePoints to url’s [username](https://url.spec.whatwg.org//#concept-url-username).

        5. Set buffer to the empty string.

    2. Otherwise, if one of the following is true:

        - [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), U+002F (/), U+003F (?), or U+0023 (#)

        - url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\)

        then:

        1. If atSignSeen is true and buffer is the empty string, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        2. Decrease pointer by the number of code points in buffer plus one, set buffer to the empty string, and set state to [host state](https://url.spec.whatwg.org//#host-state).

    3. Otherwise, append [c](https://url.spec.whatwg.org//#c) to buffer.

    host state

    hostname state

    1. If state override is given and url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`", then decrease pointer by 1 and set state to [file host state](https://url.spec.whatwg.org//#file-host-state).

    2. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+003A (:) and insideBrackets is false, then:

        1. If buffer is the empty string, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        2. If state override is given and state override is [hostname state](https://url.spec.whatwg.org//#hostname-state), then return.

        3. Let host be the result of [host parsing](https://url.spec.whatwg.org//#concept-host-parser) buffer with url [is not special](https://url.spec.whatwg.org//#is-not-special).

        4. If host is failure, then return failure.

        5. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to host, buffer to the empty string, and state to [port state](https://url.spec.whatwg.org//#port-state).

    3. Otherwise, if one of the following is true:

        - [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), U+002F (/), U+003F (?), or U+0023 (#)

        - url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\)

        then decrease pointer by 1, and then:

        1. If url [is special](https://url.spec.whatwg.org//#is-special) and buffer is the empty string, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

        2. Otherwise, if state override is given, buffer is the empty string, and either url [includes credentials](https://url.spec.whatwg.org//#include-credentials) or url’s [port](https://url.spec.whatwg.org//#concept-url-port) is non-null, return.

        3. Let host be the result of [host parsing](https://url.spec.whatwg.org//#concept-host-parser) buffer with url [is not special](https://url.spec.whatwg.org//#is-not-special).

        4. If host is failure, then return failure.

        5. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to host, buffer to the empty string, and state to [path start state](https://url.spec.whatwg.org//#path-start-state).

        6. If state override is given, then return.

    4. Otherwise:

        1. If [c](https://url.spec.whatwg.org//#c) is U+005B ([), then set insideBrackets to true.

        2. If [c](https://url.spec.whatwg.org//#c) is U+005D (]), then set insideBrackets to false.

        3. Append [c](https://url.spec.whatwg.org//#c) to buffer.

    port state

    1. If [c](https://url.spec.whatwg.org//#c) is an [ASCII digit](https://infra.spec.whatwg.org/#ascii-digit), append [c](https://url.spec.whatwg.org//#c) to buffer.

    2. Otherwise, if one of the following is true:

        - [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), U+002F (/), U+003F (?), or U+0023 (#)

        - url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\)

        - state override is given

        then:

        1. If buffer is not the empty string, then:

            1. Let port be the mathematical integer value that is represented by buffer in radix-10 using [ASCII digits](https://infra.spec.whatwg.org/#ascii-digit) for digits with values 0 through 9.

            2. If port is greater than 2<sup>16</sup> − 1, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

            3. Set url’s [port](https://url.spec.whatwg.org//#concept-url-port) to null, if port is url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme)’s [default port](https://url.spec.whatwg.org//#default-port); otherwise to port.

            4. Set buffer to the empty string.

        2. If state override is given, then return.

        3. Set state to [path start state](https://url.spec.whatwg.org//#path-start-state) and decrease pointer by 1.

    3. Otherwise, [validation error](https://url.spec.whatwg.org//#validation-error), return failure.

    file state

    1. Set url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) to "`file`".

    2. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to the empty string.

    3. If [c](https://url.spec.whatwg.org//#c) is U+002F (/) or U+005C (\), then:

        1. If [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. Set state to [file slash state](https://url.spec.whatwg.org//#file-slash-state).

    4. Otherwise, if base is non-null and base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`":

        1. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to base’s [host](https://url.spec.whatwg.org//#concept-url-host), url’s [path](https://url.spec.whatwg.org//#concept-url-path) to a [clone](https://infra.spec.whatwg.org/#list-clone) of base’s [path](https://url.spec.whatwg.org//#concept-url-path), and url’s [query](https://url.spec.whatwg.org//#concept-url-query) to base’s [query](https://url.spec.whatwg.org//#concept-url-query).

        2. If [c](https://url.spec.whatwg.org//#c) is U+003F (?), then set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string and state to [query state](https://url.spec.whatwg.org//#query-state).

        3. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+0023 (#), set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

        4. Otherwise, if [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

            1. Set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to null.

            2. If the [code point substring](https://infra.spec.whatwg.org/#code-point-substring-to-the-end-of-the-string) from pointer to the end of input does not [start with a Windows drive letter](https://url.spec.whatwg.org//#start-with-a-windows-drive-letter), then [shorten](https://url.spec.whatwg.org//#shorten-a-urls-path) url’s [path](https://url.spec.whatwg.org//#concept-url-path).

            3. Otherwise:

                1. [Validation error](https://url.spec.whatwg.org//#validation-error).

                2. Set url’s [path](https://url.spec.whatwg.org//#concept-url-path) to an empty list.

                This is a (platform-independent) Windows drive letter quirk.

            4. Set state to [path state](https://url.spec.whatwg.org//#path-state) and decrease pointer by 1.

    5. Otherwise, set state to [path state](https://url.spec.whatwg.org//#path-state), and decrease pointer by 1.

    file slash state

    1. If [c](https://url.spec.whatwg.org//#c) is U+002F (/) or U+005C (\), then:

        1. If [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. Set state to [file host state](https://url.spec.whatwg.org//#file-host-state).

    2. Otherwise:

        1. If base is non-null and base’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`", then:

            1. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to base’s [host](https://url.spec.whatwg.org//#concept-url-host).

            2. If the [code point substring](https://infra.spec.whatwg.org/#code-point-substring-to-the-end-of-the-string) from pointer to the end of input does not [start with a Windows drive letter](https://url.spec.whatwg.org//#start-with-a-windows-drive-letter) and base’s [path][https://url.spec.whatwg.org//#concept-url-path](0) is a [normalized Windows drive letter](https://url.spec.whatwg.org//#normalized-windows-drive-letter), then [append](https://infra.spec.whatwg.org/#list-append) base’s [path][https://url.spec.whatwg.org//#concept-url-path](0) to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

                This is a (platform-independent) Windows drive letter quirk.

        2. Set state to [path state](https://url.spec.whatwg.org//#path-state), and decrease pointer by 1.

    file host state

    1. If [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), U+002F (/), U+005C (\), U+003F (?), or U+0023 (#), then decrease pointer by 1 and then:

        1. If state override is not given and buffer is a [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter), [validation error](https://url.spec.whatwg.org//#validation-error), set state to [path state](https://url.spec.whatwg.org//#path-state).

            This is a (platform-independent) Windows drive letter quirk. buffer is not reset here and instead used in the [path state](https://url.spec.whatwg.org//#path-state).

        2. Otherwise, if buffer is the empty string, then:

            1. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to the empty string.

            2. If state override is given, then return.

            3. Set state to [path start state](https://url.spec.whatwg.org//#path-start-state).

        3. Otherwise, run these steps:

            1. Let host be the result of [host parsing](https://url.spec.whatwg.org//#concept-host-parser) buffer with url [is not special](https://url.spec.whatwg.org//#is-not-special).

            2. If host is failure, then return failure.

            3. If host is "`localhost`", then set host to the empty string.

            4. Set url’s [host](https://url.spec.whatwg.org//#concept-url-host) to host.

            5. If state override is given, then return.

            6. Set buffer to the empty string and state to [path start state](https://url.spec.whatwg.org//#path-start-state).

    2. Otherwise, append [c](https://url.spec.whatwg.org//#c) to buffer.

    path start state

    1. If url [is special](https://url.spec.whatwg.org//#is-special), then:

        1. If [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. Set state to [path state](https://url.spec.whatwg.org//#path-state).

        3. If [c](https://url.spec.whatwg.org//#c) is neither U+002F (/) nor U+005C (\), then decrease pointer by 1.

    2. Otherwise, if state override is not given and [c](https://url.spec.whatwg.org//#c) is U+003F (?), set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string and state to [query state](https://url.spec.whatwg.org//#query-state).

    3. Otherwise, if state override is not given and [c](https://url.spec.whatwg.org//#c) is U+0023 (#), set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

    4. Otherwise, if [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

        1. Set state to [path state](https://url.spec.whatwg.org//#path-state).

        2. If [c](https://url.spec.whatwg.org//#c) is not U+002F (/), then decrease pointer by 1.

    5. Otherwise, if state override is given and url’s [host](https://url.spec.whatwg.org//#concept-url-host) is null, [append](https://infra.spec.whatwg.org/#list-append) the empty string to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

    path state

    1. If one of the following is true:

        - [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point) or U+002F (/)

        - url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\)

        - state override is not given and [c](https://url.spec.whatwg.org//#c) is U+003F (?) or U+0023 (#)

        then:

        1. If url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. If buffer is a [double-dot path segment](https://url.spec.whatwg.org//#double-dot-path-segment), then:

            1. [Shorten](https://url.spec.whatwg.org//#shorten-a-urls-path) url’s [path](https://url.spec.whatwg.org//#concept-url-path).

            2. If neither [c](https://url.spec.whatwg.org//#c) is U+002F (/), nor url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\), [append](https://infra.spec.whatwg.org/#list-append) the empty string to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

                This means that for input `/usr/..` the result is `/` and not a lack of a path.

        3. Otherwise, if buffer is a [single-dot path segment](https://url.spec.whatwg.org//#single-dot-path-segment) and if neither [c](https://url.spec.whatwg.org//#c) is U+002F (/), nor url [is special](https://url.spec.whatwg.org//#is-special) and [c](https://url.spec.whatwg.org//#c) is U+005C (\), [append](https://infra.spec.whatwg.org/#list-append) the empty string to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

        4. Otherwise, if buffer is not a [single-dot path segment](https://url.spec.whatwg.org//#single-dot-path-segment), then:

            1. If url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`file`", url’s [path](https://url.spec.whatwg.org//#concept-url-path) [is empty](https://infra.spec.whatwg.org/#list-is-empty), and buffer is a [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter), then replace the second code point in buffer with U+003A (:).

                This is a (platform-independent) Windows drive letter quirk.

            2. [Append](https://infra.spec.whatwg.org/#list-append) buffer to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

        5. Set buffer to the empty string.

        6. If [c](https://url.spec.whatwg.org//#c) is U+003F (?), then set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string and state to [query state](https://url.spec.whatwg.org//#query-state).

        7. If [c](https://url.spec.whatwg.org//#c) is U+0023 (#), then set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

    2. Otherwise, run these steps:

        1. If [c](https://url.spec.whatwg.org//#c) is not a [URL code point](https://url.spec.whatwg.org//#url-code-points) and not U+0025 (%), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. If [c](https://url.spec.whatwg.org//#c) is U+0025 (%) and [remaining](https://url.spec.whatwg.org//#remaining) does not start with two [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit), [validation error](https://url.spec.whatwg.org//#validation-error).

        3. [UTF-8 percent-encode](https://url.spec.whatwg.org//#utf-8-percent-encode) [c](https://url.spec.whatwg.org//#c) using the [path percent-encode set](https://url.spec.whatwg.org//#path-percent-encode-set) and append the result to buffer.

    opaque path state

    1. If [c](https://url.spec.whatwg.org//#c) is U+003F (?), then set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string and state to [query state](https://url.spec.whatwg.org//#query-state).

    2. Otherwise, if [c](https://url.spec.whatwg.org//#c) is U+0023 (#), then set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

    3. Otherwise:

        1. If [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), not a [URL code point](https://url.spec.whatwg.org//#url-code-points), and not U+0025 (%), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. If [c](https://url.spec.whatwg.org//#c) is U+0025 (%) and [remaining](https://url.spec.whatwg.org//#remaining) does not start with two [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit), [validation error](https://url.spec.whatwg.org//#validation-error).

        3. If [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), [UTF-8 percent-encode](https://url.spec.whatwg.org//#utf-8-percent-encode) [c](https://url.spec.whatwg.org//#c) using the [C0 control percent-encode set](https://url.spec.whatwg.org//#c0-control-percent-encode-set) and append the result to url’s [path](https://url.spec.whatwg.org//#concept-url-path).

    query state

    1. If encoding is not [UTF-8](https://encoding.spec.whatwg.org/#utf-8) and one of the following is true:

        - url [is not special](https://url.spec.whatwg.org//#is-not-special)

        - url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) is "`ws`" or "`wss`"

        then set encoding to [UTF-8](https://encoding.spec.whatwg.org/#utf-8).

    2. If one of the following is true:

        - state override is not given and [c](https://url.spec.whatwg.org//#c) is U+0023 (#)

        - [c](https://url.spec.whatwg.org//#c) is the [EOF code point](https://url.spec.whatwg.org//#eof-code-point)

        then:

        1. Let queryPercentEncodeSet be the [special-query percent-encode set](https://url.spec.whatwg.org//#special-query-percent-encode-set) if url [is special](https://url.spec.whatwg.org//#is-special); otherwise the [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set).

        2. [Percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding), with encoding, buffer, and queryPercentEncodeSet, and append the result to url’s [query](https://url.spec.whatwg.org//#concept-url-query).

            This operation cannot be invoked code-point-for-code-point due to the stateful [ISO-2022-JP encoder](https://encoding.spec.whatwg.org/#iso-2022-jp-encoder).

        3. Set buffer to the empty string.

        4. If [c](https://url.spec.whatwg.org//#c) is U+0023 (#), then set url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string and state to [fragment state](https://url.spec.whatwg.org//#fragment-state).

    3. Otherwise, if [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point):

        1. If [c](https://url.spec.whatwg.org//#c) is not a [URL code point](https://url.spec.whatwg.org//#url-code-points) and not U+0025 (%), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. If [c](https://url.spec.whatwg.org//#c) is U+0025 (%) and [remaining](https://url.spec.whatwg.org//#remaining) does not start with two [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit), [validation error](https://url.spec.whatwg.org//#validation-error).

        3. Append [c](https://url.spec.whatwg.org//#c) to buffer.

    fragment state

    1. If [c](https://url.spec.whatwg.org//#c) is not the [EOF code point](https://url.spec.whatwg.org//#eof-code-point), then:

        1. If [c](https://url.spec.whatwg.org//#c) is not a [URL code point](https://url.spec.whatwg.org//#url-code-points) and not U+0025 (%), [validation error](https://url.spec.whatwg.org//#validation-error).

        2. If [c](https://url.spec.whatwg.org//#c) is U+0025 (%) and [remaining](https://url.spec.whatwg.org//#remaining) does not start with two [ASCII hex digits](https://infra.spec.whatwg.org/#ascii-hex-digit), [validation error](https://url.spec.whatwg.org//#validation-error).

        3. [UTF-8 percent-encode](https://url.spec.whatwg.org//#utf-8-percent-encode) [c](https://url.spec.whatwg.org//#c) using the [fragment percent-encode set](https://url.spec.whatwg.org//#fragment-percent-encode-set) and append the result to url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment).

10. Return url.

---

To set the username given a url and username, set url’s [username](https://url.spec.whatwg.org//#concept-url-username) to the result of running [UTF-8 percent-encode](https://url.spec.whatwg.org//#string-utf-8-percent-encode) on username using the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set).

To set the password given a url and password, set url’s [password](https://url.spec.whatwg.org//#concept-url-password) to the result of running [UTF-8 percent-encode](https://url.spec.whatwg.org//#string-utf-8-percent-encode) on password using the [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set).

### 4.5. URL serializing[](https://url.spec.whatwg.org//#url-serializing)

The URL serializer takes a [URL](https://url.spec.whatwg.org//#concept-url) url, with an optional boolean exclude fragment (default false), and then runs these steps. They return an [ASCII string](https://infra.spec.whatwg.org/#ascii-string).

1. Let output be url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme) and U+003A (:) concatenated.

2. If url’s [host](https://url.spec.whatwg.org//#concept-url-host) is non-null:

    1. Append "`//`" to output.

    2. If url [includes credentials](https://url.spec.whatwg.org//#include-credentials), then:

        1. Append url’s [username](https://url.spec.whatwg.org//#concept-url-username) to output.

        2. If url’s [password](https://url.spec.whatwg.org//#concept-url-password) is not the empty string, then append U+003A (:), followed by url’s [password](https://url.spec.whatwg.org//#concept-url-password), to output.

        3. Append U+0040 (@) to output.

    3. Append url’s [host](https://url.spec.whatwg.org//#concept-url-host), [serialized](https://url.spec.whatwg.org//#concept-host-serializer), to output.

    4. If url’s [port](https://url.spec.whatwg.org//#concept-url-port) is non-null, append U+003A (:) followed by url’s [port](https://url.spec.whatwg.org//#concept-url-port), [serialized](https://url.spec.whatwg.org//#serialize-an-integer), to output.

3. If url’s [host](https://url.spec.whatwg.org//#concept-url-host) is null, url does not have an [opaque path](https://url.spec.whatwg.org//#url-opaque-path), url’s [path](https://url.spec.whatwg.org//#concept-url-path)’s [size](https://infra.spec.whatwg.org/#list-size) is greater than 1, and url’s [path][https://url.spec.whatwg.org//#concept-url-path](0) is the empty string, then append U+002F (/) followed by U+002E (.) to output.

    This prevents `web+demo:/.//not-a-host/` or `web+demo:/path/..//not-a-host/`, when [parsed](https://url.spec.whatwg.org//#concept-url-parser) and then [serialized](https://url.spec.whatwg.org//#concept-url-serializer), from ending up as `web+demo://not-a-host/` (they end up as `web+demo:/.//not-a-host/`).

4. Append the result of [URL path serializing](https://url.spec.whatwg.org//#url-path-serializer) url to output.

5. If url’s [query](https://url.spec.whatwg.org//#concept-url-query) is non-null, append U+003F (?), followed by url’s [query](https://url.spec.whatwg.org//#concept-url-query), to output.

6. If exclude fragment is false and url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) is non-null, then append U+0023 (#), followed by url’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment), to output.

7. Return output.

The URL path serializer takes a [URL](https://url.spec.whatwg.org//#concept-url) url and then runs these steps. They return an [ASCII string](https://infra.spec.whatwg.org/#ascii-string).

- If url has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path), then return url’s [path](https://url.spec.whatwg.org//#concept-url-path).

- Let output be the empty string.

- [For each](https://infra.spec.whatwg.org/#list-iterate) segment of url’s [path](https://url.spec.whatwg.org//#concept-url-path): append U+002F (/) followed by segment to output.

- Return output.

### 4.6. URL equivalence[](https://url.spec.whatwg.org//#url-equivalence)

To determine whether a [URL](https://url.spec.whatwg.org//#concept-url) A equals [URL](https://url.spec.whatwg.org//#concept-url) B, with an optional boolean exclude fragments[](https://url.spec.whatwg.org//#url-equals-exclude-fragments) (default false), run these steps:

1. Let serializedA be the result of [serializing](https://url.spec.whatwg.org//#concept-url-serializer) A, with [*exclude fragment*](https://url.spec.whatwg.org//#url-serializer-exclude-fragment) set to exclude fragments.

2. Let serializedB be the result of [serializing](https://url.spec.whatwg.org//#concept-url-serializer) B, with [*exclude fragment*](https://url.spec.whatwg.org//#url-serializer-exclude-fragment) set to exclude fragments.

3. Return true if serializedA is serializedB; otherwise false.

### 4.7. Origin[](https://url.spec.whatwg.org//#origin)

See [origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin)’s definition in HTML for the necessary background information. [[HTML]](https://url.spec.whatwg.org//#biblio-html)

The origin of a [URL](https://url.spec.whatwg.org//#concept-url) url is the [origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin) returned by running these steps, switching on url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme):

"`blob`"

1. If url’s [blob URL entry](https://url.spec.whatwg.org//#concept-url-blob-entry) is non-null, then return url’s [blob URL entry](https://url.spec.whatwg.org//#concept-url-blob-entry)’s [environment](https://w3c.github.io/FileAPI/#blob-url-entry-environment)’s [origin](https://html.spec.whatwg.org/multipage/webappapis.html#concept-settings-object-origin).

2. Let pathURL be the result of [parsing](https://url.spec.whatwg.org//#concept-basic-url-parser) the result of [URL path serializing](https://url.spec.whatwg.org//#url-path-serializer) url.

3. If pathURL is failure, then return a new [opaque origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-opaque).

4. Return pathURL’s [origin](https://url.spec.whatwg.org//#concept-url-origin).

[](https://url.spec.whatwg.org//#example-43b5cea5)The [origin](https://url.spec.whatwg.org//#concept-url-origin) of `blob:https://whatwg.org/d0360e2f-caee-469f-9a2f-87d5b0456f6f` is the [tuple origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-tuple) ("`https`", "`whatwg.org`", null, null).

"`ftp`"

"`http`"

"`https`"

"`ws`"

"`wss`"

Return the [tuple origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-tuple) (url’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme), url’s [host](https://url.spec.whatwg.org//#concept-url-host), url’s [port](https://url.spec.whatwg.org//#concept-url-port), null).

"`file`"

Unfortunate as it is, this is left as an exercise to the reader. When in doubt, return a new [opaque origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-opaque).

Otherwise

Return a new [opaque origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-opaque).

This does indeed mean that these [URLs](https://url.spec.whatwg.org//#concept-url) cannot be [same origin](https://html.spec.whatwg.org/multipage/browsers.html#same-origin) with themselves.

### 4.8. URL rendering[](https://url.spec.whatwg.org//#url-rendering)

A [URL](https://url.spec.whatwg.org//#concept-url) should be rendered in its [serialized](https://url.spec.whatwg.org//#concept-url-serializer) form, with modifications described below, when the primary purpose of displaying a URL is to have the user make a security or trust decision. For example, users are expected to make trust decisions based on a URL rendered in the browser address bar.

#### 4.8.1. Simplify non-human-readable or irrelevant components[](https://url.spec.whatwg.org//#url-rendering-simplification)

Remove components that can provide opportunities for spoofing or distract from security-relevant information:

- Browsers may render only a URL’s [host](https://url.spec.whatwg.org//#concept-url-host) in places where it is important for users to distinguish between the host and other parts of the URL such as the [path](https://url.spec.whatwg.org//#concept-url-path). Browsers may consider simplifying the host further to draw attention to its [registrable domain](https://url.spec.whatwg.org//#host-registrable-domain). For example, browsers may omit a leading `www` or `m` domain label to simplify the host, or display its registrable domain only to remove spoofing opportunities posted by subdomains (e.g., `https://examplecorp.attacker.com/`).

- Browsers should not render a [URL](https://url.spec.whatwg.org//#concept-url)’s [username](https://url.spec.whatwg.org//#concept-url-username) and [password](https://url.spec.whatwg.org//#concept-url-password), as they can be mistaken for a [URL](https://url.spec.whatwg.org//#concept-url)’s [host](https://url.spec.whatwg.org//#concept-url-host) (e.g., `https://examplecorp.com@attacker.example/`).

- Browsers may render a URL without its [scheme](https://url.spec.whatwg.org//#concept-url-scheme) if the display surface only ever permits a single scheme (such as a browser feature that omits `https://` because it is only enabled for secure origins). Otherwise, the scheme may be replaced or supplemented with a human-readable string (e.g., "Not secure"), a security indicator icon, or both.

#### 4.8.2. Elision[](https://url.spec.whatwg.org//#url-rendering-elision)

In a space-constrained display, URLs should be elided carefully to avoid misleading the user when making a security decision:

- Browsers should ensure that at least the [registrable domain](https://url.spec.whatwg.org//#host-registrable-domain) can be shown when the URL is rendered (to avoid showing, e.g., `...examplecorp.com` when loading `https://not-really-examplecorp.com/`).

- When the full [host](https://url.spec.whatwg.org//#concept-url-host) cannot be rendered, browsers should elide domain labels starting from the lowest-level domain label. For example, `examplecorp.com.evil.com` should be elided as `...com.evil.com`, not `examplecorp.com...`. (Note that bidirectional text means that the lowest-level domain label may not appear on the left.)

#### 4.8.3. Internationalization and special characters[](https://url.spec.whatwg.org//#url-rendering-i18n)

Internationalized domain names (IDNs), special characters, and bidirectional text should be handled with care to prevent spoofing:

- Browsers should render a [URL](https://url.spec.whatwg.org//#concept-url)’s [host](https://url.spec.whatwg.org//#concept-url-host) using [domain to Unicode](https://url.spec.whatwg.org//#concept-domain-to-unicode).

    Various characters can be used in homograph spoofing attacks. Consider detecting confusable characters and warning when they are in use. [[IDNFAQ]](https://url.spec.whatwg.org//#biblio-idnfaq) [[UTS39]](https://url.spec.whatwg.org//#biblio-uts39)

- URLs are particularly prone to confusion between host and path when they contain bidirectional text, so in this case it is particularly advisable to only render a URL’s [host](https://url.spec.whatwg.org//#concept-url-host). For readability, other parts of the [URL](https://url.spec.whatwg.org//#concept-url), if rendered, should have their sequences of [percent-encoded bytes](https://url.spec.whatwg.org//#percent-encoded-byte) replaced with code points resulting from [percent-decoding](https://url.spec.whatwg.org//#string-percent-decode) those sequences converted to bytes, unless that renders those sequences invisible. Browsers may choose to not decode certain sequences that present spoofing risks (e.g., U+1F512 (🔒)).

- Browsers should render bidirectional text as if it were in a left-to-right embedding. [[BIDI]](https://url.spec.whatwg.org//#biblio-bidi)

    Unfortunately, as rendered [URLs](https://url.spec.whatwg.org//#concept-url) are strings and can appear anywhere, a specific bidirectional algorithm for rendered [URLs](https://url.spec.whatwg.org//#concept-url) would not see wide adoption. Bidirectional text interacts with the parts of a [URL](https://url.spec.whatwg.org//#concept-url) in ways that can cause the rendering to be different from the model. Users of bidirectional languages can come to expect this, particularly in plain text environments.

## 5. `application/x-www-form-urlencoded`[](https://url.spec.whatwg.org//#application/x-www-form-urlencoded)

The `application/x-www-form-urlencoded` format provides a way to encode name-value pairs.

The `application/x-www-form-urlencoded` format is in many ways an aberrant monstrosity, the result of many years of implementation accidents and compromises leading to a set of requirements necessary for interoperability, but in no way representing good design practices. In particular, readers are cautioned to pay close attention to the twisted details involving repeated (and in some cases nested) conversions between character encodings and byte sequences. Unfortunately the format is in widespread use due to the prevalence of HTML forms. [[HTML]](https://url.spec.whatwg.org//#biblio-html)

### 5.1. `application/x-www-form-urlencoded` parsing[](https://url.spec.whatwg.org//#urlencoded-parsing)

A legacy server-oriented implementation might have to support [encodings](https://encoding.spec.whatwg.org/#encoding) other than [UTF-8](https://encoding.spec.whatwg.org/#utf-8) as well as have special logic for tuples of which the name is ``_charset``. Such logic is not described here as only [UTF-8](https://encoding.spec.whatwg.org/#utf-8) is conforming.

The `application/x-www-form-urlencoded` parser takes a byte sequence input, and then runs these steps:

1. Let sequences be the result of splitting input on 0x26 (&).

2. Let output be an initially empty [list](https://infra.spec.whatwg.org/#list) of name-value tuples where both name and value hold a string.

3. [For each](https://infra.spec.whatwg.org/#list-iterate) byte sequence bytes in sequences:

    1. If bytes is the empty byte sequence, then [continue](https://infra.spec.whatwg.org/#iteration-continue).

    2. If bytes contains a 0x3D (=), then let name be the bytes from the start of bytes up to but excluding its first 0x3D (=), and let value be the bytes, if any, after the first 0x3D (=) up to the end of bytes. If 0x3D (=) is the first byte, then name will be the empty byte sequence. If it is the last, then value will be the empty byte sequence.

    3. Otherwise, let name have the value of bytes and let value be the empty byte sequence.

    4. Replace any 0x2B (+) in name and value with 0x20 (SP).

    5. Let nameString and valueString be the result of running [UTF-8 decode without BOM](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom) on the [percent-decoding](https://url.spec.whatwg.org//#percent-decode) of name and value, respectively.

    6. [Append](https://infra.spec.whatwg.org/#list-append) (nameString, valueString) to output.

4. Return output.

### 5.2. `application/x-www-form-urlencoded` serializing[](https://url.spec.whatwg.org//#urlencoded-serializing)

The `application/x-www-form-urlencoded` serializer takes a list of name-value tuples tuples, with an optional [encoding](https://encoding.spec.whatwg.org/#encoding) encoding (default [UTF-8](https://encoding.spec.whatwg.org/#utf-8)), and then runs these steps:

1. Set encoding to the result of [getting an output encoding](https://encoding.spec.whatwg.org/#get-an-output-encoding) from encoding.

2. Let output be the empty string.

3. [For each](https://infra.spec.whatwg.org/#list-iterate) tuple of tuples:

    1. Let name be the result of running [percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with encoding, tuple’s name, the [`application/x-www-form-urlencoded` percent-encode set](https://url.spec.whatwg.org//#application-x-www-form-urlencoded-percent-encode-set), and true.

    2. Let value be the result of running [percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding) with encoding, tuple’s value, the [`application/x-www-form-urlencoded` percent-encode set](https://url.spec.whatwg.org//#application-x-www-form-urlencoded-percent-encode-set), and true.

    3. If output is not the empty string, then append U+0026 (&) to output.

    4. Append name, followed by U+003D (=), followed by value, to output.
4. Return output.

### 5.3. Hooks[](https://url.spec.whatwg.org//#urlencoded-hooks)

The `application/x-www-form-urlencoded` string parser takes a string input, [UTF-8 encodes](https://encoding.spec.whatwg.org/#utf-8-encode) it, and then returns the result of [`application/x-www-form-urlencoded` parsing](https://url.spec.whatwg.org//#concept-urlencoded-parser) it.

## 6. API[](https://url.spec.whatwg.org//#api)

**✔**MDN

[URL](https://developer.mozilla.org/en-US/docs/Web/API/URL "The URL interface is used to parse, construct, normalize, and encode URLs. It works by providing properties which allow you to easily read and modify the components of a URL.")

In all current engines.

Firefox19+Safari7+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)12+IE10+

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView4.4+Samsung Internet?Opera Mobile?

---

Node.js10.0.0+

### 6.1. URL class[](https://url.spec.whatwg.org//#url-class)

**✔**MDN

[URL/toString](https://developer.mozilla.org/en-US/docs/Web/API/URL/toString "The URL.toString() stringifier method returns a string containing the whole URL. It is effectively a read-only version of URL.href.")

In all current engines.

Firefox54+Safari7+Chrome19+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet6.0+Opera Mobile?

---

Node.js7.0.0+

```
[Exposed=*,
 LegacyWindowAlias=webkitURL]
interface URL {
  constructor(USVString url, optional USVString base);

  stringifier attribute USVString href;
  readonly attribute USVString origin;
           attribute USVString protocol;
           attribute USVString username;
           attribute USVString password;
           attribute USVString host;
           attribute USVString hostname;
           attribute USVString port;
           attribute USVString pathname;
           attribute USVString search;
  [SameObject] readonly attribute URLSearchParams searchParams;
           attribute USVString hash;

  USVString toJSON();
};

```

A `[URL](https://url.spec.whatwg.org//#url)` object has an associated:

- URL: a [URL](https://url.spec.whatwg.org//#concept-url).
- query object: a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object.

---

**✔**MDN

[URL/URL](https://developer.mozilla.org/en-US/docs/Web/API/URL/URL "The URL() constructor returns a newly created URL object representing the URL defined by the parameters.")

In all current engines.

Firefox26+Safari14.1+Chrome19+

---

Opera?Edge79+

---

Edge (Legacy)12+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js10.0.0+

The `new URL(url, base)` constructor steps are:

1. Let parsedBase be null.

2. If base is given, then:

    1. Let parsedBase be the result of running the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser) on base.

    2. If parsedBase is failure, then [throw](https://webidl.spec.whatwg.org/#dfn-throw) a `[TypeError](https://webidl.spec.whatwg.org/#exceptiondef-typeerror)`.

3. Let parsedURL be the result of running the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser) on url with parsedBase.

4. If parsedURL is failure, then [throw](https://webidl.spec.whatwg.org/#dfn-throw) a `[TypeError](https://webidl.spec.whatwg.org/#exceptiondef-typeerror)`.

5. Let query be parsedURL’s [query](https://url.spec.whatwg.org//#concept-url-query), if that is non-null, and the empty string otherwise.

6. Set [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) to parsedURL.

7. Set [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object) to a new `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object.

8. [Initialize](https://url.spec.whatwg.org//#urlsearchparams-initialize) [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object) with query.

9. Set [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object)’s [URL object](https://url.spec.whatwg.org//#concept-urlsearchparams-url-object) to [this](https://webidl.spec.whatwg.org/#this).

[](https://url.spec.whatwg.org//#example-5434421b)

To [parse](https://url.spec.whatwg.org//#concept-basic-url-parser) a string into a [URL](https://url.spec.whatwg.org//#concept-url) without using a [base URL](https://url.spec.whatwg.org//#concept-base-url), invoke the `[URL](https://url.spec.whatwg.org//#url)` constructor with a single argument:

```
var input = "https://example.org/💩",
    url = new URL(input)
url.pathname // "/%F0%9F%92%A9"
```

This throws an exception if the input is not an [absolute-URL-with-fragment string](https://url.spec.whatwg.org//#absolute-url-with-fragment-string):

```
try {
  var url = new URL("/🍣🍺")
} catch(e) {
  // that happened
}
```

A [base URL](https://url.spec.whatwg.org//#concept-base-url) is necessary if the input is a [relative-URL string](https://url.spec.whatwg.org//#relative-url-string):

```
var input = "/🍣🍺",
    url = new URL(input, document.baseURI)
url.href // "https://url.spec.whatwg.org/%F0%9F%8D%A3%F0%9F%8D%BA"
```

A `[URL](https://url.spec.whatwg.org//#url)` object can be used as [base URL](https://url.spec.whatwg.org//#concept-base-url) (while IDL requires a string as argument, a `[URL](https://url.spec.whatwg.org//#url)` object stringifies to its `[href](https://url.spec.whatwg.org//#dom-url-href)` getter return value):

```
var url = new URL("🏳️🌈", new URL("https://pride.example/hello-world"))
url.pathname // "/%F0%9F%8F%B3%EF%B8%8F%E2%80%8D%F0%9F%8C%88"
```

---

**✔**MDN

[URL/href](https://developer.mozilla.org/en-US/docs/Web/API/URL/href "The href property of the URL interface is a string containing the whole URL.")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

[URL/toJSON](https://developer.mozilla.org/en-US/docs/Web/API/URL/toJSON "The toJSON() method of the URL interface returns a string containing a serialized version of the URL, although in practice it seems to have the same effect as URL.toString().")

In all current engines.

Firefox54+Safari11+Chrome71+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.7.0+

The `href` getter steps and the `toJSON()` method steps are to return the [serialization](https://url.spec.whatwg.org//#concept-url-serializer) of [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url).

The `[href](https://url.spec.whatwg.org//#dom-url-href)` setter steps are:

1. Let parsedURL be the result of running the [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser) on the given value.

2. If parsedURL is failure, then [throw](https://webidl.spec.whatwg.org/#dfn-throw) a `[TypeError](https://webidl.spec.whatwg.org/#exceptiondef-typeerror)`.

3. Set [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) to parsedURL.

4. Empty [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

5. Let query be [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [query](https://url.spec.whatwg.org//#concept-url-query).

6. If query is non-null, then set [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list) to the result of [parsing](https://url.spec.whatwg.org//#concept-urlencoded-string-parser) query.

**✔**MDN

[URL/origin](https://developer.mozilla.org/en-US/docs/Web/API/URL/origin "The origin read-only property of the URL interface returns a string containing the Unicode serialization of the origin of the represented URL.")

In all current engines.

Firefox26+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)12+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet6.0+Opera Mobile?

---

Node.js7.0.0+

The `origin` getter steps are to return the [serialization](https://html.spec.whatwg.org/multipage/browsers.html#ascii-serialisation-of-an-origin) of [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [origin](https://url.spec.whatwg.org//#concept-url-origin). [[HTML]](https://url.spec.whatwg.org//#biblio-html)

**✔**MDN

[URL/protocol](https://developer.mozilla.org/en-US/docs/Web/API/URL/protocol "The protocol property of the URL interface is a string representing the protocol scheme of the URL, including the final ':'.")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `protocol` getter steps are to return [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [scheme](https://url.spec.whatwg.org//#concept-url-scheme), followed by U+003A (:).

The `[protocol](https://url.spec.whatwg.org//#dom-url-protocol)` setter steps are to [basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) the given value, followed by U+003A (:), with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [scheme start state](https://url.spec.whatwg.org//#scheme-start-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

**✔**MDN

[URL/username](https://developer.mozilla.org/en-US/docs/Web/API/URL/username "The username property of the URL interface is a string containing the username specified before the domain name.")

In all current engines.

Firefox26+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)12+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet6.0+Opera Mobile?

---

Node.js7.0.0+

The `username` getter steps are to return [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [username](https://url.spec.whatwg.org//#concept-url-username).

The `[username](https://url.spec.whatwg.org//#dom-url-username)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) [cannot have a username/password/port](https://url.spec.whatwg.org//#cannot-have-a-username-password-port), then return.

2. [Set the username](https://url.spec.whatwg.org//#set-the-username) given [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) and the given value.

**✔**MDN

[URL/password](https://developer.mozilla.org/en-US/docs/Web/API/URL/password "The password property of the URL interface is a string containing the password specified before the domain name.")

In all current engines.

Firefox26+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)12+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet6.0+Opera Mobile?

---

Node.js7.0.0+

The `password` getter steps are to return [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [password](https://url.spec.whatwg.org//#concept-url-password).

The `[password](https://url.spec.whatwg.org//#dom-url-password)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) [cannot have a username/password/port](https://url.spec.whatwg.org//#cannot-have-a-username-password-port), then return.

2. [Set the password](https://url.spec.whatwg.org//#set-the-password) given [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) and the given value.

**✔**MDN

[URL/host](https://developer.mozilla.org/en-US/docs/Web/API/URL/host "The host property of the URL interface is a string containing the host, that is the hostname, and then, if the port of the URL is nonempty, a ':', followed by the port of the URL.")

In all current engines.

Firefox22+Safari7+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `host` getter steps are:

1. Let url be [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url).

2. If url’s [host](https://url.spec.whatwg.org//#concept-url-host) is null, then return the empty string.

3. If url’s [port](https://url.spec.whatwg.org//#concept-url-port) is null, return url’s [host](https://url.spec.whatwg.org//#concept-url-host), [serialized](https://url.spec.whatwg.org//#concept-host-serializer).

4. Return url’s [host](https://url.spec.whatwg.org//#concept-url-host), [serialized](https://url.spec.whatwg.org//#concept-host-serializer), followed by U+003A (:) and url’s [port](https://url.spec.whatwg.org//#concept-url-port), [serialized](https://url.spec.whatwg.org//#serialize-an-integer).

The `[host](https://url.spec.whatwg.org//#dom-url-host)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path), then return.

2. [Basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) the given value with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [host state](https://url.spec.whatwg.org//#host-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

If the given value for the `[host](https://url.spec.whatwg.org//#dom-url-host)` setter lacks a [port](https://url.spec.whatwg.org//#url-port-string), [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [port](https://url.spec.whatwg.org//#concept-url-port) will not change. This can be unexpected as `host` getter does return a [URL-port string](https://url.spec.whatwg.org//#url-port-string) so one might have assumed the setter to always "reset" both.

**✔**MDN

[URL/hostname](https://developer.mozilla.org/en-US/docs/Web/API/URL/hostname "The hostname property of the URL interface is a string containing the domain name of the URL.")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `hostname` getter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [host](https://url.spec.whatwg.org//#concept-url-host) is null, then return the empty string.

2. Return [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [host](https://url.spec.whatwg.org//#concept-url-host), [serialized](https://url.spec.whatwg.org//#concept-host-serializer).

The `[hostname](https://url.spec.whatwg.org//#dom-url-hostname)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path), then return.

2. [Basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) the given value with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [hostname state](https://url.spec.whatwg.org//#hostname-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

**✔**MDN

[URL/port](https://developer.mozilla.org/en-US/docs/Web/API/URL/port "The port property of the URL interface is a string containing the port number of the URL.")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `port` getter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [port](https://url.spec.whatwg.org//#concept-url-port) is null, then return the empty string.

2. Return [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [port](https://url.spec.whatwg.org//#concept-url-port), [serialized](https://url.spec.whatwg.org//#serialize-an-integer).

The `[port](https://url.spec.whatwg.org//#dom-url-port)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) [cannot have a username/password/port](https://url.spec.whatwg.org//#cannot-have-a-username-password-port), then return.

2. If the given value is the empty string, then set [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [port](https://url.spec.whatwg.org//#concept-url-port) to null.

3. Otherwise, [basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) the given value with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [port state](https://url.spec.whatwg.org//#port-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

**✔**MDN

[URL/pathname](https://developer.mozilla.org/en-US/docs/Web/API/URL/pathname "The pathname property of the URL interface is a string containing an initial / followed by the path of the URL, not including the query string or fragment (or the empty string if there is no path).")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `pathname` getter steps are to return the result of [URL path serializing](https://url.spec.whatwg.org//#url-path-serializer) [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url).

The `[pathname](https://url.spec.whatwg.org//#dom-url-pathname)` setter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) has an [opaque path](https://url.spec.whatwg.org//#url-opaque-path), then return.

2. [Empty](https://infra.spec.whatwg.org/#list-empty) [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [path](https://url.spec.whatwg.org//#concept-url-path).

3. [Basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) the given value with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [path start state](https://url.spec.whatwg.org//#path-start-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

**✔**MDN

[URL/search](https://developer.mozilla.org/en-US/docs/Web/API/URL/search "The search property of the URL interface is a search string, also called a query string, that is a string containing a '?' followed by the parameters of the URL.")

In all current engines.

Firefox22+Safari10+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `search` getter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [query](https://url.spec.whatwg.org//#concept-url-query) is either null or the empty string, then return the empty string.

2. Return U+003F (?), followed by [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [query](https://url.spec.whatwg.org//#concept-url-query).

The `[search](https://url.spec.whatwg.org//#dom-url-search)` setter steps are:

1. Let url be [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url).

2. If the given value is the empty string, set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to null, empty [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list), and then return.

3. Let input be the given value with a single leading U+003F (?) removed, if any.

4. Set url’s [query](https://url.spec.whatwg.org//#concept-url-query) to the empty string.

5. [Basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) input with url as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [query state](https://url.spec.whatwg.org//#query-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

6. Set [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list) to the result of [parsing](https://url.spec.whatwg.org//#concept-urlencoded-string-parser) input.

**✔**MDN

[URL/searchParams](https://developer.mozilla.org/en-US/docs/Web/API/URL/searchParams "The searchParams readonly property of the URL interface returns a URLSearchParams object allowing access to the GET decoded query arguments contained in the URL.")

In all current engines.

Firefox29+Safari10+Chrome51+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `searchParams` getter steps are to return [this](https://webidl.spec.whatwg.org/#this)’s [query object](https://url.spec.whatwg.org//#concept-url-query-object).

**✔**MDN

[URL/hash](https://developer.mozilla.org/en-US/docs/Web/API/URL/hash "The hash property of the URL interface is a string containing a '#' followed by the fragment identifier of the URL.")

In all current engines.

Firefox22+Safari7+Chrome32+

---

Opera?Edge79+

---

Edge (Legacy)13+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.0.0+

The `hash` getter steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) is either null or the empty string, then return the empty string.

2. Return U+0023 (#), followed by [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment).

The `[hash](https://url.spec.whatwg.org//#dom-url-hash)` setter steps are:

1. If the given value is the empty string, then set [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to null and return.

2. Let input be the given value with a single leading U+0023 (#) removed, if any.

3. Set [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [fragment](https://url.spec.whatwg.org//#concept-url-fragment) to the empty string.

4. [Basic URL parse](https://url.spec.whatwg.org//#concept-basic-url-parser) input with [this](https://webidl.spec.whatwg.org/#this)’s [URL](https://url.spec.whatwg.org//#concept-url-url) as [*url*](https://url.spec.whatwg.org//#basic-url-parser-url) and [fragment state](https://url.spec.whatwg.org//#fragment-state) as [*state override*](https://url.spec.whatwg.org//#basic-url-parser-state-override).

### 6.2. URLSearchParams class[](https://url.spec.whatwg.org//#interface-urlsearchparams)

**✔**MDN

[URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams "The URLSearchParams interface defines utility methods to work with the query string of a URL.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js10.0.0+

```
[Exposed=*]
interface URLSearchParams {
  constructor(optional (sequence<sequence<USVString>> or record<USVString, USVString> or USVString) init = "");

  undefined append(USVString name, USVString value);
  undefined delete(USVString name);
  USVString? get(USVString name);
  sequence<USVString> getAll(USVString name);
  boolean has(USVString name);
  undefined set(USVString name, USVString value);

  undefined sort();

  iterable<USVString, USVString>;
  stringifier;
};

```

[](https://url.spec.whatwg.org//#example-constructing-urlsearchparams)

Constructing and stringifying a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object is fairly straightforward:

```
let params = new URLSearchParams({key: "730d67"})
params.toString() // "key=730d67"
```

As a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object uses the [`application/x-www-form-urlencoded`](https://url.spec.whatwg.org//#concept-urlencoded) format underneath there are some difference with how it encodes certain code points compared to a `[URL](https://url.spec.whatwg.org//#url)` object (including `[href](https://url.spec.whatwg.org//#dom-url-href)` and `[search](https://url.spec.whatwg.org//#dom-url-search)`). This can be especially surprising when using `[searchParams](https://url.spec.whatwg.org//#dom-url-searchparams)` to operate on a [URL](https://url.spec.whatwg.org//#concept-url)’s [query](https://url.spec.whatwg.org//#concept-url-query).

```
const url = new URL('https://example.com/?a=b ~');
console.log(url.href);   // "https://example.com/?a=b%20~"
url.searchParams.sort();
console.log(url.href);   // "https://example.com/?a=b+%7E"
```

```
const url = new URL('https://example.com/?a=~&b=%7E');
console.log(url.search);                // "?a=~&b=%7E"
console.log(url.searchParams.get('a')); // "~"
console.log(url.searchParams.get('b')); // "~"
```

`[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` objects will percent-encode anything in the [`application/x-www-form-urlencoded` percent-encode set](https://url.spec.whatwg.org//#application-x-www-form-urlencoded-percent-encode-set), and will encode U+0020 SPACE as U+002B (+).

Ignoring encodings (use [UTF-8](https://encoding.spec.whatwg.org/#utf-8)), `[search](https://url.spec.whatwg.org//#dom-url-search)` will percent-encode anything in the [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set) or the [special-query percent-encode set](https://url.spec.whatwg.org//#special-query-percent-encode-set) (depending on whether or not the [URL](https://url.spec.whatwg.org//#concept-url) [is special](https://url.spec.whatwg.org//#is-special)).

A `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object has an associated:

- list: a [list](https://infra.spec.whatwg.org/#list) of name-value pairs, initially empty.
- URL object: null or a `[URL](https://url.spec.whatwg.org//#url)` object, initially null.

To initialize a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object query with init, run these steps:

1. If init is a [sequence](https://webidl.spec.whatwg.org/#idl-sequence), then [for each](https://infra.spec.whatwg.org/#list-iterate) pair in init:

    1. If pair does not contain exactly two items, then [throw](https://webidl.spec.whatwg.org/#dfn-throw) a `[TypeError](https://webidl.spec.whatwg.org/#exceptiondef-typeerror)`.

    2. Append a new name-value pair whose name is pair’s first item, and value is pair’s second item, to query’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

2. Otherwise, if init is a [record](https://webidl.spec.whatwg.org/#idl-record), then [for each](https://infra.spec.whatwg.org/#map-iterate) name → value of init, [append](https://infra.spec.whatwg.org/#list-append) a new name-value pair whose name is name and value is value, to query’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

3. Otherwise:

    1. Assert: init is a string.

    2. Set query’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list) to the result of [parsing](https://url.spec.whatwg.org//#concept-urlencoded-string-parser) init.

To update a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object query, run these steps:

1. If query’s [URL object](https://url.spec.whatwg.org//#concept-urlsearchparams-url-object) is null, then return.

2. Let serializedQuery be the [serialization](https://url.spec.whatwg.org//#concept-urlencoded-serializer) of query’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

3. If serializedQuery is the empty string, then set serializedQuery to null.

4. Set query’s [URL object](https://url.spec.whatwg.org//#concept-urlsearchparams-url-object)’s [URL](https://url.spec.whatwg.org//#concept-url-url)’s [query](https://url.spec.whatwg.org//#concept-url-query) to serializedQuery.

**✔**MDN

[URLSearchParams/URLSearchParams](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/URLSearchParams "The URLSearchParams() constructor creates and returns a new URLSearchParams object.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `new URLSearchParams(init)` constructor steps are:

1. If init is a string and starts with U+003F (?), then remove the first code point from init.

2. [Initialize](https://url.spec.whatwg.org//#urlsearchparams-initialize) [this](https://webidl.spec.whatwg.org/#this) with init.

**✔**MDN

[URLSearchParams/append](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/append "The append() method of the URLSearchParams interface appends a specified key/value pair as a new search parameter.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `append(name, value)` method steps are:

1. Append a new name-value pair whose name is name and value is value, to [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

2. [Update](https://url.spec.whatwg.org//#concept-urlsearchparams-update) [this](https://webidl.spec.whatwg.org/#this).

**✔**MDN

[URLSearchParams/delete](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/delete "The delete() method of the URLSearchParams interface deletes the given search parameter and all its associated values, from the list of all search parameters.")

In all current engines.

Firefox29+Safari14+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `delete(name)` method steps are:

1. Remove all name-value pairs whose name is name from [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

2. [Update](https://url.spec.whatwg.org//#concept-urlsearchparams-update) [this](https://webidl.spec.whatwg.org/#this).

**✔**MDN

[URLSearchParams/get](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/get "The get() method of the URLSearchParams interface returns the first value associated to the given search parameter.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `get(name)` method steps are to return the value of the first name-value pair whose name is name in [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list), if there is such a pair, and null otherwise.

**✔**MDN

[URLSearchParams/getAll](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/getAll "The getAll() method of the URLSearchParams interface returns all the values associated with a given search parameter as an array.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `getAll(name)` method steps are to return the values of all name-value pairs whose name is name, in [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list), in list order, and the empty sequence otherwise.

**✔**MDN

[URLSearchParams/has](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/has "The has() method of the URLSearchParams interface returns a boolean value that indicates whether a parameter with the specified name exists.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `has(name)` method steps are to return true if there is a name-value pair whose name is name in [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list), and false otherwise.

**✔**MDN

[URLSearchParams/set](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/set "The set() method of the URLSearchParams interface sets the value associated with a given search parameter to the given value. If there were several matching values, this method deletes the others. If the search parameter doesn't exist, this method creates it.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The `set(name, value)` method steps are:

1. If [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list) [contains](https://infra.spec.whatwg.org/#list-contain) any name-value pairs whose name is name, then set the value of the first such name-value pair to value and remove the others.

2. Otherwise, append a new name-value pair whose name is name and value is value, to [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

3. [Update](https://url.spec.whatwg.org//#concept-urlsearchparams-update) [this](https://webidl.spec.whatwg.org/#this).

---

[](https://url.spec.whatwg.org//#example-searchparams-sort)

It can be useful to sort the name-value pairs in a `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object, in particular to increase cache hits. This can be accomplished through invoking the `[sort()](https://url.spec.whatwg.org//#dom-urlsearchparams-sort)` method:

```
const url = new URL("https://example.org/?q=🏳️🌈&key=e1f7bc78");
url.searchParams.sort();
url.search; // "?key=e1f7bc78&q=%F0%9F%8F%B3%EF%B8%8F%E2%80%8D%F0%9F%8C%88"
```

To avoid altering the original input, e.g., for comparison purposes, construct a new `[URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams)` object:

```
const sorted = new URLSearchParams(url.search)
sorted.sort()
```

**✔**MDN

[URLSearchParams/sort](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/sort "The URLSearchParams.sort() method sorts all key/value pairs contained in this object in place and returns undefined. The sort order is according to unicode code points of the keys. This method uses a stable sorting algorithm (i.e. the relative order between key/value pairs with equal keys will be preserved).")

In all current engines.

Firefox54+Safari11+Chrome61+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.7.0+

The `sort()` method steps are:

1. Sort all name-value pairs, if any, by their names. Sorting must be done by comparison of code units. The relative order between name-value pairs with equal names must be preserved.

2. [Update](https://url.spec.whatwg.org//#concept-urlsearchparams-update) [this](https://webidl.spec.whatwg.org/#this).

---

The [value pairs to iterate over](https://webidl.spec.whatwg.org/#dfn-value-pairs-to-iterate-over) are [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list)’s name-value pairs with the key being the name and the value being the value.

**✔**MDN

[URLSearchParams/toString](https://developer.mozilla.org/en-US/docs/Web/API/URLSearchParams/toString "The toString() method of the URLSearchParams interface returns a query string suitable for use in a URL.")

In all current engines.

Firefox29+Safari10.1+Chrome49+

---

Opera?Edge79+

---

Edge (Legacy)17+IENone

---

Firefox for Android?iOS Safari?Chrome for Android?Android WebView?Samsung Internet?Opera Mobile?

---

Node.js7.5.0+

The stringification behavior steps are to return the [serialization](https://url.spec.whatwg.org//#concept-urlencoded-serializer) of [this](https://webidl.spec.whatwg.org/#this)’s [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list).

### 6.3. URL APIs elsewhere[](https://url.spec.whatwg.org//#url-apis-elsewhere)

A standard that exposes [URLs](https://url.spec.whatwg.org//#concept-url), should expose the [URL](https://url.spec.whatwg.org//#concept-url) as a string (by [serializing](https://url.spec.whatwg.org//#concept-url-serializer) an internal [URL](https://url.spec.whatwg.org//#concept-url)). A standard should not expose a [URL](https://url.spec.whatwg.org//#concept-url) using a `[URL](https://url.spec.whatwg.org//#url)` object. `[URL](https://url.spec.whatwg.org//#url)` objects are meant for [URL](https://url.spec.whatwg.org//#concept-url) manipulation. In IDL the USVString type should be used.

The higher-level notion here is that values are to be exposed as immutable data structures.

If a standard decides to use a variant of the name "URL" for a feature it defines, it should name such a feature "url" (i.e., lowercase and with an "l" at the end). Names such as "URL", "URI", and "IRI" should not be used. However, if the name is a compound, "URL" (i.e., uppercase) is preferred, e.g., "newURL" and "oldURL".

The `[EventSource](https://html.spec.whatwg.org/multipage/server-sent-events.html#eventsource)` and `[HashChangeEvent](https://html.spec.whatwg.org/multipage/nav-history-apis.html#hashchangeevent)` interfaces in HTML are examples of proper naming. [[HTML]](https://url.spec.whatwg.org//#biblio-html)

## Acknowledgments[](https://url.spec.whatwg.org//#acknowledgments)

There have been a lot of people that have helped make [URLs](https://url.spec.whatwg.org//#concept-url) more interoperable over the years and thereby furthered the goals of this standard. Likewise many people have helped making this standard what it is today.

With that, many thanks to 100の人, Adam Barth, Addison Phillips, Albert Wiersch, Alex Christensen, Alexandre Morgaut, Alexis Hunt, Alwin Blok, Andrew Sullivan, Arkadiusz Michalski, Behnam Esfahbod, Bobby Holley, Boris Zbarsky, Brad Hill, Brandon Ross, Chris Dumez, Chris Rebert, Corey Farwell, Dan Appelquist, Daniel Bratell, Daniel Stenberg, David Burns, David Håsäther, David Sheets, David Singer, David Walp, Domenic Denicola, Emily Schechter, Emily Stark, Eric Lawrence, Erik Arvidsson, Gavin Carothers, Geoff Richards, Glenn Maynard, Gordon P. Hemsley, Henri Sivonen, Ian Hickson, Ilya Grigorik, Italo A. Casas, Jakub Gieryluk, James Graham, James Manger, James Ross, Jeff Hodges, Jeffrey Posnick, Jeffrey Yasskin, Joe Duarte, Joshua Bell, Jxck, Karl Wagner, 田村健人 (Kent TAMURA), Kevin Grandon, Kornel Lesiński, Larry Masinter, Leif Halvard Silli, Mark Amery, Mark Davis, Marcos Cáceres, Marijn Kruisselbrink, Martin Dürst, Mathias Bynens, Matt Falkenhagen, Matt Giuca, Michael Peick, Michael™ Smith, Michal Bukovský, Michel Suignard, Mikaël Geljić, Noah Levitt, Peter Occil, Philip Jägenstedt, Philippe Ombredanne, Prayag Verma, Rimas Misevičius, Robert Kieffer, Rodney Rehm, Roy Fielding, Ryan Sleevi, Sam Ruby, Sam Sneddon, Santiago M. Mola, Sebastian Mayr, Simon Pieters, Simon Sapin, Steven Vachon, Stuart Cook, Sven Uhlig, Tab Atkins, 吉野剛史 (Takeshi Yoshino), Tantek Çelik, Tiancheng "Timothy" Gu, Tim Berners-Lee, 簡冠庭 (Tim Guan-tin Chien), Titi_Alone, Tomek Wytrębowicz, Trevor Rowbotham, Tristan Seligmann, Valentin Gosu, Vyacheslav Matva, Wei Wang, Wolf Lammen, 山岸和利 (Yamagishi Kazutoshi), Yongsheng Zhang, 成瀬ゆい (Yui Naruse), and zealousidealroll for being awesome!

This standard is written by [Anne van Kesteren](https://annevankesteren.nl/) ([Apple](https://www.apple.com/), [annevk@annevk.nl](mailto:annevk@annevk.nl)).

## Intellectual property rights[](https://url.spec.whatwg.org//#ipr)

Copyright © WHATWG (Apple, Google, Mozilla, Microsoft). This work is licensed under a [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/). To the extent portions of it are incorporated into source code, such portions in the source code are licensed under the [BSD 3-Clause License](https://opensource.org/licenses/BSD-3-Clause) instead.

This is the Living Standard. Those interested in the patent-review version should view the [Living Standard Review Draft](https://url.spec.whatwg.org/review-drafts/2022-08/).

"use strict"; if ("serviceWorker" in navigator) { navigator.serviceWorker.register("/service-worker.js"); }

## Index[](https://url.spec.whatwg.org//#index)

### Terms defined by this specification[](https://url.spec.whatwg.org//#index-defined-here)

- [absolute-URL string](https://url.spec.whatwg.org//#absolute-url-string), in § 4.3
- [absolute-URL-with-fragment string](https://url.spec.whatwg.org//#absolute-url-with-fragment-string), in § 4.3
- [append(name, value)](https://url.spec.whatwg.org//#dom-urlsearchparams-append), in § 6.2
- [application/x-www-form-urlencoded](https://url.spec.whatwg.org//#concept-urlencoded), in § 5
- [application/x-www-form-urlencoded percent-encode set](https://url.spec.whatwg.org//#application-x-www-form-urlencoded-percent-encode-set), in § 1.3
- [authority state](https://url.spec.whatwg.org//#authority-state), in § 4.4
- [base URL](https://url.spec.whatwg.org//#concept-base-url), in § 4.2
- [basic URL parser](https://url.spec.whatwg.org//#concept-basic-url-parser), in § 4.4
- [blob URL entry](https://url.spec.whatwg.org//#concept-url-blob-entry), in § 4.1
- [c](https://url.spec.whatwg.org//#c), in § 1.2
- [C0 control percent-encode set](https://url.spec.whatwg.org//#c0-control-percent-encode-set), in § 1.3
- [cannot have a username/password/port](https://url.spec.whatwg.org//#cannot-have-a-username-password-port), in § 4.2
- [component percent-encode set](https://url.spec.whatwg.org//#component-percent-encode-set), in § 1.3
- [constructor()](https://url.spec.whatwg.org//#dom-urlsearchparams-urlsearchparams), in § 6.2
- [constructor(init)](https://url.spec.whatwg.org//#dom-urlsearchparams-urlsearchparams), in § 6.2
- [constructor(url)](https://url.spec.whatwg.org//#dom-url-url), in § 6.1
- [constructor(url, base)](https://url.spec.whatwg.org//#dom-url-url), in § 6.1
- [default port](https://url.spec.whatwg.org//#default-port), in § 4.2
- [delete(name)](https://url.spec.whatwg.org//#dom-urlsearchparams-delete), in § 6.2
- [domain](https://url.spec.whatwg.org//#concept-domain), in § 3.1
- [domain to ASCII](https://url.spec.whatwg.org//#concept-domain-to-ascii), in § 3.3
- [domain to Unicode](https://url.spec.whatwg.org//#concept-domain-to-unicode), in § 3.3
- [double-dot path segment](https://url.spec.whatwg.org//#double-dot-path-segment), in § 4.3
- [empty host](https://url.spec.whatwg.org//#empty-host), in § 3.1
- [ends in a number checker](https://url.spec.whatwg.org//#ends-in-a-number-checker), in § 3.5
- [EOF code point](https://url.spec.whatwg.org//#eof-code-point), in § 1.2
- equal
  - [dfn for host](https://url.spec.whatwg.org//#concept-host-equals), in § 3.7
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-equals), in § 4.6
- [exclude fragment](https://url.spec.whatwg.org//#url-serializer-exclude-fragment), in § 4.5
- [exclude fragments](https://url.spec.whatwg.org//#url-equals-exclude-fragments), in § 4.6
- [file host state](https://url.spec.whatwg.org//#file-host-state), in § 4.4
- [file slash state](https://url.spec.whatwg.org//#file-slash-state), in § 4.4
- [file state](https://url.spec.whatwg.org//#file-state), in § 4.4
- [forbidden domain code point](https://url.spec.whatwg.org//#forbidden-domain-code-point), in § 3.2
- [forbidden host code point](https://url.spec.whatwg.org//#forbidden-host-code-point), in § 3.2
- [fragment](https://url.spec.whatwg.org//#concept-url-fragment), in § 4.1
- [fragment percent-encode set](https://url.spec.whatwg.org//#fragment-percent-encode-set), in § 1.3
- [fragment state](https://url.spec.whatwg.org//#fragment-state), in § 4.4
- [getAll(name)](https://url.spec.whatwg.org//#dom-urlsearchparams-getall), in § 6.2
- [get(name)](https://url.spec.whatwg.org//#dom-urlsearchparams-get), in § 6.2
- [hash](https://url.spec.whatwg.org//#dom-url-hash), in § 6.1
- [has(name)](https://url.spec.whatwg.org//#dom-urlsearchparams-has), in § 6.2
- host
  - [attribute for URL](https://url.spec.whatwg.org//#dom-url-host), in § 6.1
  - [definition of](https://url.spec.whatwg.org//#concept-host), in § 3.1
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-host), in § 4.1
- [hostname](https://url.spec.whatwg.org//#dom-url-hostname), in § 6.1
- [hostname state](https://url.spec.whatwg.org//#hostname-state), in § 4.4
- [host parser](https://url.spec.whatwg.org//#concept-host-parser), in § 3.5
- [host parsing](https://url.spec.whatwg.org//#concept-host-parser), in § 3.5
- [host serializer](https://url.spec.whatwg.org//#concept-host-serializer), in § 3.6
- [host state](https://url.spec.whatwg.org//#host-state), in § 4.4
- [href](https://url.spec.whatwg.org//#dom-url-href), in § 6.1
- [include credentials](https://url.spec.whatwg.org//#include-credentials), in § 4.2
- [includes credentials](https://url.spec.whatwg.org//#include-credentials), in § 4.2
- [initialize](https://url.spec.whatwg.org//#urlsearchparams-initialize), in § 6.2
- [IP address](https://url.spec.whatwg.org//#ip-address), in § 3.1
- [IPv4 address](https://url.spec.whatwg.org//#concept-ipv4), in § 3.1
- [IPv4 number parser](https://url.spec.whatwg.org//#ipv4-number-parser), in § 3.5
- [IPv4 parser](https://url.spec.whatwg.org//#concept-ipv4-parser), in § 3.5
- [IPv4 serializer](https://url.spec.whatwg.org//#concept-ipv4-serializer), in § 3.6
- [IPv6 address](https://url.spec.whatwg.org//#concept-ipv6), in § 3.1
- [IPv6 parser](https://url.spec.whatwg.org//#concept-ipv6-parser), in § 3.5
- [IPv6 piece](https://url.spec.whatwg.org//#concept-ipv6-piece), in § 3.1
- [IPv6 serializer](https://url.spec.whatwg.org//#concept-ipv6-serializer), in § 3.6
- [is not special](https://url.spec.whatwg.org//#is-not-special), in § 4.2
- [is special](https://url.spec.whatwg.org//#is-special), in § 4.2
- [list](https://url.spec.whatwg.org//#concept-urlsearchparams-list), in § 6.2
- [normalized Windows drive letter](https://url.spec.whatwg.org//#normalized-windows-drive-letter), in § 4.2
- [no scheme state](https://url.spec.whatwg.org//#no-scheme-state), in § 4.4
- [opaque host](https://url.spec.whatwg.org//#opaque-host), in § 3.1
- [opaque-host-and-port string](https://url.spec.whatwg.org//#opaque-host-and-port-string), in § 4.3
- [opaque-host parser](https://url.spec.whatwg.org//#concept-opaque-host-parser), in § 3.5
- [opaque path](https://url.spec.whatwg.org//#url-opaque-path), in § 4.2
- [opaque path state](https://url.spec.whatwg.org//#cannot-be-a-base-url-path-state), in § 4.4
- origin
  - [attribute for URL](https://url.spec.whatwg.org//#dom-url-origin), in § 6.1
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-origin), in § 4.7
- password
  - [attribute for URL](https://url.spec.whatwg.org//#dom-url-password), in § 6.1
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-password), in § 4.1
- [path](https://url.spec.whatwg.org//#concept-url-path), in § 4.1
- [path-absolute-non-Windows-file-URL string](https://url.spec.whatwg.org//#path-absolute-non-windows-file-url-string), in § 4.3
- [path-absolute-URL string](https://url.spec.whatwg.org//#path-absolute-url-string), in § 4.3
- [pathname](https://url.spec.whatwg.org//#dom-url-pathname), in § 6.1
- [path or authority state](https://url.spec.whatwg.org//#path-or-authority-state), in § 4.4
- [path percent-encode set](https://url.spec.whatwg.org//#path-percent-encode-set), in § 1.3
- [path-relative-scheme-less-URL string](https://url.spec.whatwg.org//#path-relative-scheme-less-url-string), in § 4.3
- [path-relative-URL string](https://url.spec.whatwg.org//#path-relative-url-string), in § 4.3
- [path start state](https://url.spec.whatwg.org//#path-start-state), in § 4.4
- [path state](https://url.spec.whatwg.org//#path-state), in § 4.4
- percent-decode
  - [dfn for byte sequence](https://url.spec.whatwg.org//#percent-decode), in § 1.3
  - [dfn for string](https://url.spec.whatwg.org//#string-percent-decode), in § 1.3
- [percent-encode](https://url.spec.whatwg.org//#percent-encode), in § 1.3
- [percent-encode after encoding](https://url.spec.whatwg.org//#string-percent-encode-after-encoding), in § 1.3
- [percent-encoded byte](https://url.spec.whatwg.org//#percent-encoded-byte), in § 1.3
- [pointer](https://url.spec.whatwg.org//#pointer), in § 1.2
- port
  - [attribute for URL](https://url.spec.whatwg.org//#dom-url-port), in § 6.1
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-port), in § 4.1
- [port state](https://url.spec.whatwg.org//#port-state), in § 4.4
- [protocol](https://url.spec.whatwg.org//#dom-url-protocol), in § 6.1
- [public suffix](https://url.spec.whatwg.org//#host-public-suffix), in § 3.2
- [query](https://url.spec.whatwg.org//#concept-url-query), in § 4.1
- [query object](https://url.spec.whatwg.org//#concept-url-query-object), in § 6.1
- [query percent-encode set](https://url.spec.whatwg.org//#query-percent-encode-set), in § 1.3
- [query state](https://url.spec.whatwg.org//#query-state), in § 4.4
- [registrable domain](https://url.spec.whatwg.org//#host-registrable-domain), in § 3.2
- [relative slash state](https://url.spec.whatwg.org//#relative-slash-state), in § 4.4
- [relative state](https://url.spec.whatwg.org//#relative-state), in § 4.4
- [relative-URL string](https://url.spec.whatwg.org//#relative-url-string), in § 4.3
- [relative-URL-with-fragment string](https://url.spec.whatwg.org//#relative-url-with-fragment-string), in § 4.3
- [remaining](https://url.spec.whatwg.org//#remaining), in § 1.2
- [scheme](https://url.spec.whatwg.org//#concept-url-scheme), in § 4.1
- [scheme-relative-file-URL string](https://url.spec.whatwg.org//#scheme-relative-file-url-string), in § 4.3
- [scheme-relative-special-URL string](https://url.spec.whatwg.org//#scheme-relative-special-url-string), in § 4.3
- [scheme-relative-URL string](https://url.spec.whatwg.org//#scheme-relative-url-string), in § 4.3
- [scheme start state](https://url.spec.whatwg.org//#scheme-start-state), in § 4.4
- [scheme state](https://url.spec.whatwg.org//#scheme-state), in § 4.4
- [search](https://url.spec.whatwg.org//#dom-url-search), in § 6.1
- [searchParams](https://url.spec.whatwg.org//#dom-url-searchparams), in § 6.1
- [serialize an integer](https://url.spec.whatwg.org//#serialize-an-integer), in § 1
- [set(name, value)](https://url.spec.whatwg.org//#dom-urlsearchparams-set), in § 6.2
- [set the password](https://url.spec.whatwg.org//#set-the-password), in § 4.4
- [set the username](https://url.spec.whatwg.org//#set-the-username), in § 4.4
- [shorten](https://url.spec.whatwg.org//#shorten-a-urls-path), in § 4.2
- [shorten a url’s path](https://url.spec.whatwg.org//#shorten-a-urls-path), in § 4.2
- [single-dot path segment](https://url.spec.whatwg.org//#single-dot-path-segment), in § 4.3
- [sort()](https://url.spec.whatwg.org//#dom-urlsearchparams-sort), in § 6.2
- [special authority ignore slashes state](https://url.spec.whatwg.org//#special-authority-ignore-slashes-state), in § 4.4
- [special authority slashes state](https://url.spec.whatwg.org//#special-authority-slashes-state), in § 4.4
- [special-query percent-encode set](https://url.spec.whatwg.org//#special-query-percent-encode-set), in § 1.3
- [special relative or authority state](https://url.spec.whatwg.org//#special-relative-or-authority-state), in § 4.4
- [special scheme](https://url.spec.whatwg.org//#special-scheme), in § 4.2
- [starts with a Windows drive letter](https://url.spec.whatwg.org//#start-with-a-windows-drive-letter), in § 4.2
- [start with a Windows drive letter](https://url.spec.whatwg.org//#start-with-a-windows-drive-letter), in § 4.2
- [state override](https://url.spec.whatwg.org//#basic-url-parser-state-override), in § 4.4
- [stringification behavior](https://url.spec.whatwg.org//#URL-stringification-behavior), in § 6.1
- [stringificationbehavior](https://url.spec.whatwg.org//#urlsearchparams-stringification-behavior), in § 6.2
- [toJSON()](https://url.spec.whatwg.org//#dom-url-tojson), in § 6.1
- [update](https://url.spec.whatwg.org//#concept-urlsearchparams-update), in § 6.2
- URL
  - [(interface)](https://url.spec.whatwg.org//#url), in § 6.1
  - [definition of](https://url.spec.whatwg.org//#concept-url), in § 4.1
  - [dfn for URL](https://url.spec.whatwg.org//#concept-url-url), in § 6.1
- [url](https://url.spec.whatwg.org//#basic-url-parser-url), in § 4.4
- [URL code point](https://url.spec.whatwg.org//#url-code-points), in § 4.3
- [urlencoded parser](https://url.spec.whatwg.org//#concept-urlencoded-parser), in § 5.1
- [urlencoded serializer](https://url.spec.whatwg.org//#concept-urlencoded-serializer), in § 5.2
- [urlencoded string parser](https://url.spec.whatwg.org//#concept-urlencoded-string-parser), in § 5.3
- [URL-fragment string](https://url.spec.whatwg.org//#url-fragment-string), in § 4.3
- [URL object](https://url.spec.whatwg.org//#concept-urlsearchparams-url-object), in § 6.2
- [URL parser](https://url.spec.whatwg.org//#concept-url-parser), in § 4.4
- [URL-path-segment string](https://url.spec.whatwg.org//#url-path-segment-string), in § 4.3
- [URL path serializer](https://url.spec.whatwg.org//#url-path-serializer), in § 4.5
- [URL path serializing](https://url.spec.whatwg.org//#url-path-serializer), in § 4.5
- [URL-port string](https://url.spec.whatwg.org//#url-port-string), in § 4.3
- [URL-query string](https://url.spec.whatwg.org//#url-query-string), in § 4.3
- [URL record](https://url.spec.whatwg.org//#concept-url), in § 4.1
- [URL-scheme string](https://url.spec.whatwg.org//#url-scheme-string), in § 4.3
- [URLSearchParams](https://url.spec.whatwg.org//#urlsearchparams), in § 6.2
- [URLSearchParams()](https://url.spec.whatwg.org//#dom-urlsearchparams-urlsearchparams), in § 6.2
- [URLSearchParams(init)](https://url.spec.whatwg.org//#dom-urlsearchparams-urlsearchparams), in § 6.2
- [URL serializer](https://url.spec.whatwg.org//#concept-url-serializer), in § 4.5
- [URL units](https://url.spec.whatwg.org//#url-units), in § 4.3
- [URL(url)](https://url.spec.whatwg.org//#dom-url-url), in § 6.1
- [URL(url, base)](https://url.spec.whatwg.org//#dom-url-url), in § 6.1
- [userinfo percent-encode set](https://url.spec.whatwg.org//#userinfo-percent-encode-set), in § 1.3
- username
  - [attribute for URL](https://url.spec.whatwg.org//#dom-url-username), in § 6.1
  - [dfn for url](https://url.spec.whatwg.org//#concept-url-username), in § 4.1
- UTF-8 percent-encode
  - [dfn for code point](https://url.spec.whatwg.org//#utf-8-percent-encode), in § 1.3
  - [dfn for string](https://url.spec.whatwg.org//#string-utf-8-percent-encode), in § 1.3
- [validation error](https://url.spec.whatwg.org//#validation-error), in § 1.1
- [valid domain](https://url.spec.whatwg.org//#valid-domain), in § 3.4
- [valid domain string](https://url.spec.whatwg.org//#valid-domain-string), in § 3.4
- [valid host string](https://url.spec.whatwg.org//#valid-host-string), in § 3.4
- [valid IPv4-address string](https://url.spec.whatwg.org//#valid-ipv4-address-string), in § 3.4
- [valid IPv6-address string](https://url.spec.whatwg.org//#valid-ipv6-address-string), in § 3.4
- [valid opaque-host string](https://url.spec.whatwg.org//#valid-opaque-host-string), in § 3.4
- [valid URL string](https://url.spec.whatwg.org//#valid-url-string), in § 4.3
- [webkitURL](https://url.spec.whatwg.org//#webkiturl), in § 6.1
- [Windows drive letter](https://url.spec.whatwg.org//#windows-drive-letter), in § 4.2

[https://tc39.es/ecma262/#sec-encodeuricomponent-uricomponent](https://tc39.es/ecma262/#sec-encodeuricomponent-uricomponent)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-sec-encodeuricomponent-uricomponent)

[https://encoding.spec.whatwg.org/#encode-or-fail](https://encoding.spec.whatwg.org/#encode-or-fail)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-encode-or-fail)

[https://encoding.spec.whatwg.org/#encoding](https://encoding.spec.whatwg.org/#encoding)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-encoding)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-encoding①) [(2)](https://url.spec.whatwg.org//#ref-for-encoding②)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-encoding③)
- [5.2. application/x-www-form-urlencoded serializing](https://url.spec.whatwg.org//#ref-for-encoding④)

[https://encoding.spec.whatwg.org/#get-an-output-encoding](https://encoding.spec.whatwg.org/#get-an-output-encoding)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-get-an-output-encoding)
- [5.2. application/x-www-form-urlencoded serializing](https://url.spec.whatwg.org//#ref-for-get-an-output-encoding①)

[https://encoding.spec.whatwg.org/#get-an-encoder](https://encoding.spec.whatwg.org/#get-an-encoder)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-get-an-encoder)

[https://encoding.spec.whatwg.org/#concept-stream](https://encoding.spec.whatwg.org/#concept-stream)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-concept-stream) [(2)](https://url.spec.whatwg.org//#ref-for-concept-stream①)

[https://encoding.spec.whatwg.org/#iso-2022-jp](https://encoding.spec.whatwg.org/#iso-2022-jp)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-iso-2022-jp)

[https://encoding.spec.whatwg.org/#iso-2022-jp-encoder](https://encoding.spec.whatwg.org/#iso-2022-jp-encoder)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-iso-2022-jp-encoder)

[https://encoding.spec.whatwg.org/#shift_jis](https://encoding.spec.whatwg.org/#shift_jis)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-shift_jis) [(2)](https://url.spec.whatwg.org//#ref-for-shift_jis①)

[https://encoding.spec.whatwg.org/#utf-8](https://encoding.spec.whatwg.org/#utf-8)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-utf-8) [(2)](https://url.spec.whatwg.org//#ref-for-utf-8①) [(3)](https://url.spec.whatwg.org//#ref-for-utf-8②)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-utf-8③)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-utf-8④) [(2)](https://url.spec.whatwg.org//#ref-for-utf-8⑤) [(3)](https://url.spec.whatwg.org//#ref-for-utf-8⑥) [(4)](https://url.spec.whatwg.org//#ref-for-utf-8⑦)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-utf-8⑧) [(2)](https://url.spec.whatwg.org//#ref-for-utf-8⑨)
- [5.2. application/x-www-form-urlencoded serializing](https://url.spec.whatwg.org//#ref-for-utf-8①⓪)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-utf-8①①)

[https://encoding.spec.whatwg.org/#utf-8-decode-without-bom](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-utf-8-decode-without-bom)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-utf-8-decode-without-bom①)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-utf-8-decode-without-bom②)

[https://encoding.spec.whatwg.org/#utf-8-decode-without-bom-or-fail](https://encoding.spec.whatwg.org/#utf-8-decode-without-bom-or-fail)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-utf-8-decode-without-bom-or-fail)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-utf-8-decode-without-bom-or-fail①)

[https://encoding.spec.whatwg.org/#utf-8-encode](https://encoding.spec.whatwg.org/#utf-8-encode)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-utf-8-encode)
- [5.3. Hooks](https://url.spec.whatwg.org//#ref-for-utf-8-encode①)

[https://w3c.github.io/FileAPI/#blob-url-entry](https://w3c.github.io/FileAPI/#blob-url-entry)**Referenced in:**

- [4.1. URL representation](https://url.spec.whatwg.org//#ref-for-blob-url-entry)

[https://w3c.github.io/FileAPI/#BlobURLStore](https://w3c.github.io/FileAPI/#BlobURLStore)**Referenced in:**

- [4.1. URL representation](https://url.spec.whatwg.org//#ref-for-BlobURLStore)

[https://w3c.github.io/FileAPI/#blob-url-entry-environment](https://w3c.github.io/FileAPI/#blob-url-entry-environment)**Referenced in:**

- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-blob-url-entry-environment)

[https://w3c.github.io/FileAPI/#blob-url-resolve](https://w3c.github.io/FileAPI/#blob-url-resolve)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-blob-url-resolve)

[https://html.spec.whatwg.org/multipage/server-sent-events.html#eventsource](https://html.spec.whatwg.org/multipage/server-sent-events.html#eventsource)**Referenced in:**

- [6.3. URL APIs elsewhere](https://url.spec.whatwg.org//#ref-for-eventsource)

[https://html.spec.whatwg.org/multipage/nav-history-apis.html#hashchangeevent](https://html.spec.whatwg.org/multipage/nav-history-apis.html#hashchangeevent)**Referenced in:**

- [6.3. URL APIs elsewhere](https://url.spec.whatwg.org//#ref-for-hashchangeevent)

[https://html.spec.whatwg.org/multipage/nav-history-apis.html#location](https://html.spec.whatwg.org/multipage/nav-history-apis.html#location)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-location) [(2)](https://url.spec.whatwg.org//#ref-for-location①)

[https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-opaque](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-opaque)**Referenced in:**

- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-concept-origin-opaque) [(2)](https://url.spec.whatwg.org//#ref-for-concept-origin-opaque①) [(3)](https://url.spec.whatwg.org//#ref-for-concept-origin-opaque②)

[https://html.spec.whatwg.org/multipage/browsers.html#concept-origin](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin)**Referenced in:**

- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-concept-origin)
- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-concept-origin①) [(2)](https://url.spec.whatwg.org//#ref-for-concept-origin②)

[https://html.spec.whatwg.org/multipage/webappapis.html#concept-settings-object-origin](https://html.spec.whatwg.org/multipage/webappapis.html#concept-settings-object-origin)**Referenced in:**

- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-concept-settings-object-origin)

[https://html.spec.whatwg.org/multipage/nav-history-apis.html#dom-location-protocol](https://html.spec.whatwg.org/multipage/nav-history-apis.html#dom-location-protocol)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-dom-location-protocol) [(2)](https://url.spec.whatwg.org//#ref-for-dom-location-protocol①)

[https://html.spec.whatwg.org/multipage/system-state.html#dom-navigator-registerprotocolhandler](https://html.spec.whatwg.org/multipage/system-state.html#dom-navigator-registerprotocolhandler)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-dom-navigator-registerprotocolhandler)

[https://html.spec.whatwg.org/multipage/browsers.html#same-origin](https://html.spec.whatwg.org/multipage/browsers.html#same-origin)**Referenced in:**

- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-same-origin)

[https://html.spec.whatwg.org/multipage/browsers.html#same-site](https://html.spec.whatwg.org/multipage/browsers.html#same-site)**Referenced in:**

- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-same-site)

[https://html.spec.whatwg.org/multipage/browsers.html#schemelessly-same-site](https://html.spec.whatwg.org/multipage/browsers.html#schemelessly-same-site)**Referenced in:**

- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-schemelessly-same-site)

[https://html.spec.whatwg.org/multipage/browsers.html#ascii-serialisation-of-an-origin](https://html.spec.whatwg.org/multipage/browsers.html#ascii-serialisation-of-an-origin)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-ascii-serialisation-of-an-origin)

[https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-tuple](https://html.spec.whatwg.org/multipage/browsers.html#concept-origin-tuple)**Referenced in:**

- [4.7. Origin](https://url.spec.whatwg.org//#ref-for-concept-origin-tuple) [(2)](https://url.spec.whatwg.org//#ref-for-concept-origin-tuple①)

[https://infra.spec.whatwg.org/#list-append](https://infra.spec.whatwg.org/#list-append)**Referenced in:**

- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list-append)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-list-append①) [(2)](https://url.spec.whatwg.org//#ref-for-list-append②) [(3)](https://url.spec.whatwg.org//#ref-for-list-append③) [(4)](https://url.spec.whatwg.org//#ref-for-list-append④) [(5)](https://url.spec.whatwg.org//#ref-for-list-append⑤)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-list-append⑥)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-list-append⑦)

[https://infra.spec.whatwg.org/#ascii-alpha](https://infra.spec.whatwg.org/#ascii-alpha)**Referenced in:**

- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-ascii-alpha)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-ascii-alpha①)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-alpha②)

[https://infra.spec.whatwg.org/#ascii-alphanumeric](https://infra.spec.whatwg.org/#ascii-alphanumeric)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-alphanumeric)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-ascii-alphanumeric①) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-alphanumeric②)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-alphanumeric③)

[https://infra.spec.whatwg.org/#ascii-byte](https://infra.spec.whatwg.org/#ascii-byte)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-byte)

[https://infra.spec.whatwg.org/#ascii-case-insensitive](https://infra.spec.whatwg.org/#ascii-case-insensitive)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive①) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive②) [(3)](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive③) [(4)](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive④) [(5)](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive⑤) [(6)](https://url.spec.whatwg.org//#ref-for-ascii-case-insensitive⑥)

[https://infra.spec.whatwg.org/#ascii-code-point](https://infra.spec.whatwg.org/#ascii-code-point)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-code-point)

[https://infra.spec.whatwg.org/#ascii-digit](https://infra.spec.whatwg.org/#ascii-digit)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-digit)
- [3.4. Host writing](https://url.spec.whatwg.org//#ref-for-ascii-digit①)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-ascii-digit②) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-digit③) [(3)](https://url.spec.whatwg.org//#ref-for-ascii-digit④)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-ascii-digit⑤)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-digit⑥) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-digit⑦)

[https://infra.spec.whatwg.org/#ascii-hex-digit](https://infra.spec.whatwg.org/#ascii-hex-digit)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit①) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit②) [(3)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit③) [(4)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit④)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit⑤) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit⑥) [(3)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit⑦) [(4)](https://url.spec.whatwg.org//#ref-for-ascii-hex-digit⑧)

[https://infra.spec.whatwg.org/#ascii-lowercase](https://infra.spec.whatwg.org/#ascii-lowercase)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-ascii-lowercase)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-lowercase①) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-lowercase②)

[https://infra.spec.whatwg.org/#ascii-string](https://infra.spec.whatwg.org/#ascii-string)**Referenced in:**

- [3.1. Host representation](https://url.spec.whatwg.org//#ref-for-ascii-string) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-string①)
- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-ascii-string②) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-string③)
- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-ascii-string④)
- [4. URLs](https://url.spec.whatwg.org//#ref-for-ascii-string⑤)
- [4.1. URL representation](https://url.spec.whatwg.org//#ref-for-ascii-string⑥) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-string⑦) [(3)](https://url.spec.whatwg.org//#ref-for-ascii-string⑧) [(4)](https://url.spec.whatwg.org//#ref-for-ascii-string⑨) [(5)](https://url.spec.whatwg.org//#ref-for-ascii-string①⓪) [(6)](https://url.spec.whatwg.org//#ref-for-ascii-string①①) [(7)](https://url.spec.whatwg.org//#ref-for-ascii-string①②)
- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-ascii-string①③) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-string①④)
- [4.5. URL serializing](https://url.spec.whatwg.org//#ref-for-ascii-string①⑤) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-string①⑥)

[https://infra.spec.whatwg.org/#ascii-tab-or-newline](https://infra.spec.whatwg.org/#ascii-tab-or-newline)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-ascii-tab-or-newline) [(2)](https://url.spec.whatwg.org//#ref-for-ascii-tab-or-newline①)

[https://infra.spec.whatwg.org/#ascii-upper-hex-digit](https://infra.spec.whatwg.org/#ascii-upper-hex-digit)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-ascii-upper-hex-digit)

[https://infra.spec.whatwg.org/#assert](https://infra.spec.whatwg.org/#assert)**Referenced in:**

- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-assert)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-assert①)

[https://infra.spec.whatwg.org/#iteration-break](https://infra.spec.whatwg.org/#iteration-break)**Referenced in:**

- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-iteration-break)

[https://infra.spec.whatwg.org/#byte](https://infra.spec.whatwg.org/#byte)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-byte)

[https://infra.spec.whatwg.org/#byte-sequence](https://infra.spec.whatwg.org/#byte-sequence)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-byte-sequence) [(2)](https://url.spec.whatwg.org//#ref-for-byte-sequence①)

[https://infra.spec.whatwg.org/#c0-control](https://infra.spec.whatwg.org/#c0-control)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-c0-control)
- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-c0-control①)

[https://infra.spec.whatwg.org/#c0-control-or-space](https://infra.spec.whatwg.org/#c0-control-or-space)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-c0-control-or-space) [(2)](https://url.spec.whatwg.org//#ref-for-c0-control-or-space①)

[https://infra.spec.whatwg.org/#list-clone](https://infra.spec.whatwg.org/#list-clone)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-list-clone) [(2)](https://url.spec.whatwg.org//#ref-for-list-clone①)

[https://infra.spec.whatwg.org/#code-point](https://infra.spec.whatwg.org/#code-point)**Referenced in:**

- [1.2. Parsers](https://url.spec.whatwg.org//#ref-for-code-point) [(2)](https://url.spec.whatwg.org//#ref-for-code-point①)
- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-code-point②) [(2)](https://url.spec.whatwg.org//#ref-for-code-point③) [(3)](https://url.spec.whatwg.org//#ref-for-code-point④)
- [2. Security considerations](https://url.spec.whatwg.org//#ref-for-code-point⑤)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-code-point⑥) [(2)](https://url.spec.whatwg.org//#ref-for-code-point⑦)
- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-code-point⑧)

[https://infra.spec.whatwg.org/#string-code-point-length](https://infra.spec.whatwg.org/#string-code-point-length)**Referenced in:**

- [1.2. Parsers](https://url.spec.whatwg.org//#ref-for-string-code-point-length)

[https://infra.spec.whatwg.org/#code-point-substring-to-the-end-of-the-string](https://infra.spec.whatwg.org/#code-point-substring-to-the-end-of-the-string)**Referenced in:**

- [1.2. Parsers](https://url.spec.whatwg.org//#ref-for-code-point-substring-to-the-end-of-the-string)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-code-point-substring-to-the-end-of-the-string①) [(2)](https://url.spec.whatwg.org//#ref-for-code-point-substring-to-the-end-of-the-string②)

[https://infra.spec.whatwg.org/#list-contain](https://infra.spec.whatwg.org/#list-contain)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-list-contain)

[https://infra.spec.whatwg.org/#iteration-continue](https://infra.spec.whatwg.org/#iteration-continue)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-iteration-continue)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-iteration-continue①)
- [3.6. Host serializing](https://url.spec.whatwg.org//#ref-for-iteration-continue②) [(2)](https://url.spec.whatwg.org//#ref-for-iteration-continue③)
- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-iteration-continue④)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-iteration-continue⑤)

[https://infra.spec.whatwg.org/#list-empty](https://infra.spec.whatwg.org/#list-empty)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-list-empty)

[https://infra.spec.whatwg.org/#string-ends-with](https://infra.spec.whatwg.org/#string-ends-with)**Referenced in:**

- [3.2. Host miscellaneous](https://url.spec.whatwg.org//#ref-for-string-ends-with) [(2)](https://url.spec.whatwg.org//#ref-for-string-ends-with①) [(3)](https://url.spec.whatwg.org//#ref-for-string-ends-with②) [(4)](https://url.spec.whatwg.org//#ref-for-string-ends-with③)

[https://infra.spec.whatwg.org/#list-iterate](https://infra.spec.whatwg.org/#list-iterate)**Referenced in:**

- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list-iterate) [(2)](https://url.spec.whatwg.org//#ref-for-list-iterate①)
- [3.6. Host serializing](https://url.spec.whatwg.org//#ref-for-list-iterate②) [(2)](https://url.spec.whatwg.org//#ref-for-list-iterate③)
- [4.5. URL serializing](https://url.spec.whatwg.org//#ref-for-list-iterate④)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-list-iterate⑤)
- [5.2. application/x-www-form-urlencoded serializing](https://url.spec.whatwg.org//#ref-for-list-iterate⑥)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-list-iterate⑦)

[https://infra.spec.whatwg.org/#map-iterate](https://infra.spec.whatwg.org/#map-iterate)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-map-iterate)

[https://infra.spec.whatwg.org/#list-is-empty](https://infra.spec.whatwg.org/#list-is-empty)**Referenced in:**

- [4.4. URL parsing](https://url.spec.whatwg.org//#ref-for-list-is-empty)

[https://infra.spec.whatwg.org/#isomorphic-decode](https://infra.spec.whatwg.org/#isomorphic-decode)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-isomorphic-decode)

[https://infra.spec.whatwg.org/#list-item](https://infra.spec.whatwg.org/#list-item)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-list-item)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list-item①) [(2)](https://url.spec.whatwg.org//#ref-for-list-item②) [(3)](https://url.spec.whatwg.org//#ref-for-list-item③) [(4)](https://url.spec.whatwg.org//#ref-for-list-item④) [(5)](https://url.spec.whatwg.org//#ref-for-list-item⑤) [(6)](https://url.spec.whatwg.org//#ref-for-list-item⑥) [(7)](https://url.spec.whatwg.org//#ref-for-list-item⑦) [(8)](https://url.spec.whatwg.org//#ref-for-list-item⑧) [(9)](https://url.spec.whatwg.org//#ref-for-list-item⑨)

[https://infra.spec.whatwg.org/#string-length](https://infra.spec.whatwg.org/#string-length)**Referenced in:**

- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-string-length) [(2)](https://url.spec.whatwg.org//#ref-for-string-length①)

[https://infra.spec.whatwg.org/#list](https://infra.spec.whatwg.org/#list)**Referenced in:**

- [3.1. Host representation](https://url.spec.whatwg.org//#ref-for-list)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list①)
- [4.1. URL representation](https://url.spec.whatwg.org//#ref-for-list②) [(2)](https://url.spec.whatwg.org//#ref-for-list③)
- [5.1. application/x-www-form-urlencoded parsing](https://url.spec.whatwg.org//#ref-for-list④)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-list⑤)

[https://infra.spec.whatwg.org/#noncharacter](https://infra.spec.whatwg.org/#noncharacter)**Referenced in:**

- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-noncharacter)

[https://infra.spec.whatwg.org/#list-remove](https://infra.spec.whatwg.org/#list-remove)**Referenced in:**

- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list-remove) [(2)](https://url.spec.whatwg.org//#ref-for-list-remove①) [(3)](https://url.spec.whatwg.org//#ref-for-list-remove②)
- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-list-remove③)

[https://infra.spec.whatwg.org/#list-size](https://infra.spec.whatwg.org/#list-size)**Referenced in:**

- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-list-size) [(2)](https://url.spec.whatwg.org//#ref-for-list-size①) [(3)](https://url.spec.whatwg.org//#ref-for-list-size②) [(4)](https://url.spec.whatwg.org//#ref-for-list-size③)
- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-list-size④)
- [4.5. URL serializing](https://url.spec.whatwg.org//#ref-for-list-size⑤)

[https://infra.spec.whatwg.org/#string-starts-with](https://infra.spec.whatwg.org/#string-starts-with)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-string-starts-with)

[https://infra.spec.whatwg.org/#strictly-split](https://infra.spec.whatwg.org/#strictly-split)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-strictly-split)
- [3.5. Host parsing](https://url.spec.whatwg.org//#ref-for-strictly-split①) [(2)](https://url.spec.whatwg.org//#ref-for-strictly-split②)

[https://infra.spec.whatwg.org/#string](https://infra.spec.whatwg.org/#string)**Referenced in:**

- [1.2. Parsers](https://url.spec.whatwg.org//#ref-for-string) [(2)](https://url.spec.whatwg.org//#ref-for-string①)
- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-string②) [(2)](https://url.spec.whatwg.org//#ref-for-string③) [(3)](https://url.spec.whatwg.org//#ref-for-string④) [(4)](https://url.spec.whatwg.org//#ref-for-string⑤) [(5)](https://url.spec.whatwg.org//#ref-for-string⑥)
- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-string⑦)
- [4.2. URL miscellaneous](https://url.spec.whatwg.org//#ref-for-string⑧)

[https://infra.spec.whatwg.org/#struct](https://infra.spec.whatwg.org/#struct)**Referenced in:**

- [4.1. URL representation](https://url.spec.whatwg.org//#ref-for-struct)

[https://infra.spec.whatwg.org/#surrogate](https://infra.spec.whatwg.org/#surrogate)**Referenced in:**

- [4.3. URL writing](https://url.spec.whatwg.org//#ref-for-surrogate)

[https://infra.spec.whatwg.org/#byte-value](https://infra.spec.whatwg.org/#byte-value)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-byte-value)

[https://infra.spec.whatwg.org/#code-point-value](https://infra.spec.whatwg.org/#code-point-value)**Referenced in:**

- [1.3. Percent-encoded bytes](https://url.spec.whatwg.org//#ref-for-code-point-value)

[https://www.unicode.org/reports/tr46/#ToASCII](https://www.unicode.org/reports/tr46/#ToASCII)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-ToASCII)

[https://www.unicode.org/reports/tr46/#ToUnicode](https://www.unicode.org/reports/tr46/#ToUnicode)**Referenced in:**

- [3.3. IDNA](https://url.spec.whatwg.org//#ref-for-ToUnicode)
- [3.4. Host writing](https://url.spec.whatwg.org//#ref-for-ToUnicode①)

[https://webidl.spec.whatwg.org/#LegacyWindowAlias](https://webidl.spec.whatwg.org/#LegacyWindowAlias)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-LegacyWindowAlias)

[https://webidl.spec.whatwg.org/#SameObject](https://webidl.spec.whatwg.org/#SameObject)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-SameObject)

[https://webidl.spec.whatwg.org/#exceptiondef-typeerror](https://webidl.spec.whatwg.org/#exceptiondef-typeerror)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-exceptiondef-typeerror) [(2)](https://url.spec.whatwg.org//#ref-for-exceptiondef-typeerror①) [(3)](https://url.spec.whatwg.org//#ref-for-exceptiondef-typeerror②)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-exceptiondef-typeerror③)

[https://webidl.spec.whatwg.org/#idl-USVString](https://webidl.spec.whatwg.org/#idl-USVString)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-idl-USVString) [(2)](https://url.spec.whatwg.org//#ref-for-idl-USVString①) [(3)](https://url.spec.whatwg.org//#ref-for-idl-USVString②) [(4)](https://url.spec.whatwg.org//#ref-for-idl-USVString③) [(5)](https://url.spec.whatwg.org//#ref-for-idl-USVString④) [(6)](https://url.spec.whatwg.org//#ref-for-idl-USVString⑤) [(7)](https://url.spec.whatwg.org//#ref-for-idl-USVString⑥) [(8)](https://url.spec.whatwg.org//#ref-for-idl-USVString⑦) [(9)](https://url.spec.whatwg.org//#ref-for-idl-USVString⑧) [(10)](https://url.spec.whatwg.org//#ref-for-idl-USVString⑨) [(11)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⓪) [(12)](https://url.spec.whatwg.org//#ref-for-idl-USVString①①) [(13)](https://url.spec.whatwg.org//#ref-for-idl-USVString①②) [(14)](https://url.spec.whatwg.org//#ref-for-idl-USVString①③)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-idl-USVString①④) [(2)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⑤) [(3)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⑥) [(4)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⑦) [(5)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⑧) [(6)](https://url.spec.whatwg.org//#ref-for-idl-USVString①⑨) [(7)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⓪) [(8)](https://url.spec.whatwg.org//#ref-for-idl-USVString②①) [(9)](https://url.spec.whatwg.org//#ref-for-idl-USVString②②) [(10)](https://url.spec.whatwg.org//#ref-for-idl-USVString②③) [(11)](https://url.spec.whatwg.org//#ref-for-idl-USVString②④) [(12)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⑤) [(13)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⑥) [(14)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⑦) [(15)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⑧) [(16)](https://url.spec.whatwg.org//#ref-for-idl-USVString②⑨)

[https://webidl.spec.whatwg.org/#idl-boolean](https://webidl.spec.whatwg.org/#idl-boolean)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-idl-boolean)

[https://webidl.spec.whatwg.org/#idl-record](https://webidl.spec.whatwg.org/#idl-record)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-idl-record) [(2)](https://url.spec.whatwg.org//#ref-for-idl-record①)

[https://webidl.spec.whatwg.org/#idl-sequence](https://webidl.spec.whatwg.org/#idl-sequence)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-idl-sequence) [(2)](https://url.spec.whatwg.org//#ref-for-idl-sequence①) [(3)](https://url.spec.whatwg.org//#ref-for-idl-sequence②) [(4)](https://url.spec.whatwg.org//#ref-for-idl-sequence③)

[https://webidl.spec.whatwg.org/#this](https://webidl.spec.whatwg.org/#this)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-this) [(2)](https://url.spec.whatwg.org//#ref-for-this①) [(3)](https://url.spec.whatwg.org//#ref-for-this②) [(4)](https://url.spec.whatwg.org//#ref-for-this③) [(5)](https://url.spec.whatwg.org//#ref-for-this④) [(6)](https://url.spec.whatwg.org//#ref-for-this⑤) [(7)](https://url.spec.whatwg.org//#ref-for-this⑥) [(8)](https://url.spec.whatwg.org//#ref-for-this⑦) [(9)](https://url.spec.whatwg.org//#ref-for-this⑧) [(10)](https://url.spec.whatwg.org//#ref-for-this⑨) [(11)](https://url.spec.whatwg.org//#ref-for-this①⓪) [(12)](https://url.spec.whatwg.org//#ref-for-this①①) [(13)](https://url.spec.whatwg.org//#ref-for-this①②) [(14)](https://url.spec.whatwg.org//#ref-for-this①③) [(15)](https://url.spec.whatwg.org//#ref-for-this①④) [(16)](https://url.spec.whatwg.org//#ref-for-this①⑤) [(17)](https://url.spec.whatwg.org//#ref-for-this①⑥) [(18)](https://url.spec.whatwg.org//#ref-for-this①⑦) [(19)](https://url.spec.whatwg.org//#ref-for-this①⑧) [(20)](https://url.spec.whatwg.org//#ref-for-this①⑨) [(21)](https://url.spec.whatwg.org//#ref-for-this②⓪) [(22)](https://url.spec.whatwg.org//#ref-for-this②①) [(23)](https://url.spec.whatwg.org//#ref-for-this②②) [(24)](https://url.spec.whatwg.org//#ref-for-this②③) [(25)](https://url.spec.whatwg.org//#ref-for-this②④) [(26)](https://url.spec.whatwg.org//#ref-for-this②⑤) [(27)](https://url.spec.whatwg.org//#ref-for-this②⑥) [(28)](https://url.spec.whatwg.org//#ref-for-this②⑦) [(29)](https://url.spec.whatwg.org//#ref-for-this②⑧) [(30)](https://url.spec.whatwg.org//#ref-for-this②⑨) [(31)](https://url.spec.whatwg.org//#ref-for-this③⓪) [(32)](https://url.spec.whatwg.org//#ref-for-this③①) [(33)](https://url.spec.whatwg.org//#ref-for-this③②) [(34)](https://url.spec.whatwg.org//#ref-for-this③③) [(35)](https://url.spec.whatwg.org//#ref-for-this③④) [(36)](https://url.spec.whatwg.org//#ref-for-this③⑤) [(37)](https://url.spec.whatwg.org//#ref-for-this③⑥) [(38)](https://url.spec.whatwg.org//#ref-for-this③⑦) [(39)](https://url.spec.whatwg.org//#ref-for-this③⑧) [(40)](https://url.spec.whatwg.org//#ref-for-this③⑨) [(41)](https://url.spec.whatwg.org//#ref-for-this④⓪) [(42)](https://url.spec.whatwg.org//#ref-for-this④①) [(43)](https://url.spec.whatwg.org//#ref-for-this④②) [(44)](https://url.spec.whatwg.org//#ref-for-this④③) [(45)](https://url.spec.whatwg.org//#ref-for-this④④) [(46)](https://url.spec.whatwg.org//#ref-for-this④⑤) [(47)](https://url.spec.whatwg.org//#ref-for-this④⑥)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-this④⑦) [(2)](https://url.spec.whatwg.org//#ref-for-this④⑧) [(3)](https://url.spec.whatwg.org//#ref-for-this④⑨) [(4)](https://url.spec.whatwg.org//#ref-for-this⑤⓪) [(5)](https://url.spec.whatwg.org//#ref-for-this⑤①) [(6)](https://url.spec.whatwg.org//#ref-for-this⑤②) [(7)](https://url.spec.whatwg.org//#ref-for-this⑤③) [(8)](https://url.spec.whatwg.org//#ref-for-this⑤④) [(9)](https://url.spec.whatwg.org//#ref-for-this⑤⑤) [(10)](https://url.spec.whatwg.org//#ref-for-this⑤⑥) [(11)](https://url.spec.whatwg.org//#ref-for-this⑤⑦) [(12)](https://url.spec.whatwg.org//#ref-for-this⑤⑧)

[https://webidl.spec.whatwg.org/#dfn-throw](https://webidl.spec.whatwg.org/#dfn-throw)**Referenced in:**

- [6.1. URL class](https://url.spec.whatwg.org//#ref-for-dfn-throw) [(2)](https://url.spec.whatwg.org//#ref-for-dfn-throw①) [(3)](https://url.spec.whatwg.org//#ref-for-dfn-throw②)
- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-dfn-throw③)

[https://webidl.spec.whatwg.org/#idl-undefined](https://webidl.spec.whatwg.org/#idl-undefined)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-idl-undefined) [(2)](https://url.spec.whatwg.org//#ref-for-idl-undefined①) [(3)](https://url.spec.whatwg.org//#ref-for-idl-undefined②) [(4)](https://url.spec.whatwg.org//#ref-for-idl-undefined③)

[https://webidl.spec.whatwg.org/#dfn-value-pairs-to-iterate-over](https://webidl.spec.whatwg.org/#dfn-value-pairs-to-iterate-over)**Referenced in:**

- [6.2. URLSearchParams class](https://url.spec.whatwg.org//#ref-for-dfn-value-pairs-to-iterate-over)

### Terms defined by reference[](https://url.spec.whatwg.org//#index-defined-elsewhere)

- [ECMA-262] defines the following terms:
  - "encodeURIComponent() [sic]"
- [ENCODING] defines the following terms:
  - encode or fail
  - encoding
  - get an output encoding
  - getting an encoder
  - i/o queue
  - iso-2022-jp
  - iso-2022-jp encoder
  - shift_jis
  - utf-8
  - utf-8 decode without bom
  - utf-8 decode without bom or fail
  - utf-8 encode
- [FILEAPI] defines the following terms:
  - blob url entry
  - blob url store
  - environment
  - resolve
- [HTML] defines the following terms:
  - EventSource
  - HashChangeEvent
  - Location
  - opaque origin
  - origin
  - origin (for environment settings object)
  - protocol
  - registerProtocolHandler(scheme, url)
  - same origin
  - same site
  - schemelessly same site
  - serialization of an origin
  - tuple origin
- [INFRA] defines the following terms:
  - append
  - ascii alpha
  - ascii alphanumeric
  - ascii byte
  - ascii case-insensitive
  - ascii code point
  - ascii digit
  - ascii hex digit
  - ascii lowercase
  - ascii string
  - ascii tab or newline
  - ascii upper hex digit
  - assert
  - break
  - byte
  - byte sequence
  - c0 control
  - c0 control or space
  - clone
  - code point
  - code point length
  - code point substring to the end of the string
  - contain
  - continue
  - empty
  - ends with
  - for each (for list)
  - for each (for map)
  - is empty
  - isomorphic decode
  - item
  - length
  - list
  - noncharacter
  - remove
  - size
  - starts with
  - strictly split
  - string
  - struct
  - surrogate
  - value (for byte)
  - value (for code point)
- [UTS46] defines the following terms:
  - ToASCII
  - ToUnicode
- [WEBIDL] defines the following terms:
  - LegacyWindowAlias
  - SameObject
  - TypeError
  - USVString
  - boolean
  - record
  - sequence
  - this
  - throw
  - undefined
  - value pairs to iterate over

## References[](https://url.spec.whatwg.org//#references)

### Normative References[](https://url.spec.whatwg.org//#normative)

[BIDI]

Mark Davis; Ken Whistler. [Unicode Bidirectional Algorithm](https://www.unicode.org/reports/tr9/tr9-46.html). 16 August 2022. Unicode Standard Annex #9. URL: [https://www.unicode.org/reports/tr9/tr9-46.html](https://www.unicode.org/reports/tr9/tr9-46.html)

[DOM]

Anne van Kesteren. [DOM Standard](https://dom.spec.whatwg.org/). Living Standard. URL: [https://dom.spec.whatwg.org/](https://dom.spec.whatwg.org/)

[ENCODING]

Anne van Kesteren. [Encoding Standard](https://encoding.spec.whatwg.org/). Living Standard. URL: [https://encoding.spec.whatwg.org/](https://encoding.spec.whatwg.org/)

[FILEAPI]

Marijn Kruisselbrink. [File API](https://w3c.github.io/FileAPI/). URL: [https://w3c.github.io/FileAPI/](https://w3c.github.io/FileAPI/)

[HTML]

Anne van Kesteren; et al. [HTML Standard](https://html.spec.whatwg.org/multipage/). Living Standard. URL: [https://html.spec.whatwg.org/multipage/](https://html.spec.whatwg.org/multipage/)

[IANA-URI-SCHEMES]

[Uniform Resource Identifier (URI) Schemes](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml). URL: [https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml](https://www.iana.org/assignments/uri-schemes/uri-schemes.xhtml)

[INFRA]

Anne van Kesteren; Domenic Denicola. [Infra Standard](https://infra.spec.whatwg.org/). Living Standard. URL: [https://infra.spec.whatwg.org/](https://infra.spec.whatwg.org/)

[MEDIA-SOURCE]

Matthew Wolenetz; et al. [Media Source Extensions™](https://w3c.github.io/media-source/). URL: [https://w3c.github.io/media-source/](https://w3c.github.io/media-source/)

[PSL]

[Public Suffix List](https://publicsuffix.org/). Mozilla Foundation.

[RFC4291]

R. Hinden; S. Deering. [IP Version 6 Addressing Architecture](https://www.rfc-editor.org/rfc/rfc4291). February 2006. Draft Standard. URL: [https://www.rfc-editor.org/rfc/rfc4291](https://www.rfc-editor.org/rfc/rfc4291)

[UTS46]

Mark Davis; Michel Suignard. [Unicode IDNA Compatibility Processing](https://www.unicode.org/reports/tr46/tr46-29.html). 26 August 2022. Unicode Technical Standard #46. URL: [https://www.unicode.org/reports/tr46/tr46-29.html](https://www.unicode.org/reports/tr46/tr46-29.html)

[WEBIDL]

Edgar Chen; Timothy Gu. [Web IDL Standard](https://webidl.spec.whatwg.org/). Living Standard. URL: [https://webidl.spec.whatwg.org/](https://webidl.spec.whatwg.org/)

### Informative References[](https://url.spec.whatwg.org//#informative)

[ECMA-262]

[ECMAScript Language Specification](https://tc39.es/ecma262/multipage/). URL: [https://tc39.es/ecma262/multipage/](https://tc39.es/ecma262/multipage/)

[IDNFAQ]

[Internationalized Domain Names (IDN) FAQ](https://unicode.org/faq/idn.html). URL: [https://unicode.org/faq/idn.html](https://unicode.org/faq/idn.html)

[RFC1034]

P. Mockapetris. [Domain names - concepts and facilities](https://www.rfc-editor.org/rfc/rfc1034). November 1987. Internet Standard. URL: [https://www.rfc-editor.org/rfc/rfc1034](https://www.rfc-editor.org/rfc/rfc1034)

[RFC3986]

T. Berners-Lee; R. Fielding; L. Masinter. [Uniform Resource Identifier (URI): Generic Syntax](https://www.rfc-editor.org/rfc/rfc3986). January 2005. Internet Standard. URL: [https://www.rfc-editor.org/rfc/rfc3986](https://www.rfc-editor.org/rfc/rfc3986)

[RFC3987]

M. Duerst; M. Suignard. [Internationalized Resource Identifiers (IRIs)](https://www.rfc-editor.org/rfc/rfc3987). January 2005. Proposed Standard. URL: [https://www.rfc-editor.org/rfc/rfc3987](https://www.rfc-editor.org/rfc/rfc3987)

[RFC5952]

S. Kawamura; M. Kawashima. [A Recommendation for IPv6 Address Text Representation](https://www.rfc-editor.org/rfc/rfc5952). August 2010. Proposed Standard. URL: [https://www.rfc-editor.org/rfc/rfc5952](https://www.rfc-editor.org/rfc/rfc5952)

[RFC6454]

A. Barth. [The Web Origin Concept](https://www.rfc-editor.org/rfc/rfc6454). December 2011. Proposed Standard. URL: [https://www.rfc-editor.org/rfc/rfc6454](https://www.rfc-editor.org/rfc/rfc6454)

[RFC7595]

D. Thaler, Ed.; T. Hansen; T. Hardie. [Guidelines and Registration Procedures for URI Schemes](https://www.rfc-editor.org/rfc/rfc7595). June 2015. Best Current Practice. URL: [https://www.rfc-editor.org/rfc/rfc7595](https://www.rfc-editor.org/rfc/rfc7595)

[RFC791]

J. Postel. [Internet Protocol](https://www.rfc-editor.org/rfc/rfc791). September 1981. Internet Standard. URL: [https://www.rfc-editor.org/rfc/rfc791](https://www.rfc-editor.org/rfc/rfc791)

[UTR36]

Mark Davis; Michel Suignard. [Unicode Security Considerations](https://www.unicode.org/reports/tr36/tr36-15.html). 19 September 2014. Unicode Technical Report #36. URL: [https://www.unicode.org/reports/tr36/tr36-15.html](https://www.unicode.org/reports/tr36/tr36-15.html)

[UTS39]

Mark Davis; Michel Suignard. [Unicode Security Mechanisms](https://www.unicode.org/reports/tr39/tr39-26.html). 26 August 2022. Unicode Technical Standard #39. URL: [https://www.unicode.org/reports/tr39/tr39-26.html](https://www.unicode.org/reports/tr39/tr39-26.html)

## IDL Index[](https://url.spec.whatwg.org//#idl-index)

```
[Exposed=*,
 LegacyWindowAlias=webkitURL]
interface URL {
  constructor(USVString url, optional USVString base);

  stringifier attribute USVString href;
  readonly attribute USVString origin;
           attribute USVString protocol;
           attribute USVString username;
           attribute USVString password;
           attribute USVString host;
           attribute USVString hostname;
           attribute USVString port;
           attribute USVString pathname;
           attribute USVString search;
  [SameObject] readonly attribute URLSearchParams searchParams;
           attribute USVString hash;

  USVString toJSON();
};

[Exposed=*]
interface URLSearchParams {
  constructor(optional (sequence<sequence<USVString>> or record<USVString, USVString> or USVString) init = "");

  undefined append(USVString name, USVString value);
  undefined delete(USVString name);
  USVString? get(USVString name);
  sequence<USVString> getAll(USVString name);
  boolean has(USVString name);
  undefined set(USVString name, USVString value);

  undefined sort();

  iterable<USVString, USVString>;
  stringifier;
};

```
