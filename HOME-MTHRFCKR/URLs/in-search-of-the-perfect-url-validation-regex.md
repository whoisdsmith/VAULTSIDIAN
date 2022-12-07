To clarify, I’m looking for a decent regular expression to validate URLs that were entered as user input with. I have no interest in parsing a list of URLs from a given string of text (even though some of the regexes on this page are capable of doing that). I also don’t want to allow every possible technically valid URL — quite the opposite.

See [the URL Standard](http://url.spec.whatwg.org/#parsing) if you’re looking to parse URLs in the same way that browsers do.

Assume that this regex will be used for a public URL shortener written in PHP, so URLs like `http://localhost/`, `//foo.bar/`, `://foo.bar/`, `data:text/plain;charset=utf-8,OHAI` and `tel:+1234567890` shouldn’t pass (even though they’re technically valid). Also, in this case I only want to allow the HTTP, HTTPS and FTP protocols.

Also, single weird leading and/or trailing characters aren’t tested for. Just imagine you’re doing this before testing `$url` with the regex:

```
$url = trim($url, '!"#$%&\'()*+,-./@:;<=>[\\]^_`{|}~');
```

Note that I’ve added [the `S` modifier](http://php.net/manual/en/reference.pcre.pattern.modifiers.php) to all the regexes to speed up the tests. In real-world usage, this modifier can be omitted.

[Here’s a plain text list of all the URLs used in the test.](data:text/plain;charset=utf-8,SHOULD%20MATCH%3A%0D%0A%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_blah%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_blah%2F%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_blah_%28wikipedia%29%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_blah_%28wikipedia%29_%28again%29%0D%0Ahttp%3A%2F%2Fwww.example.com%2Fwpstyle%2F%3Fp%3D364%0D%0Ahttps%3A%2F%2Fwww.example.com%2Ffoo%2F%3Fbar%3Dbaz%26inga%3D42%26quux%0D%0Ahttp%3A%2F%2F%E2%9C%AAdf.ws%2F123%0D%0Ahttp%3A%2F%2Fuserid%3Apassword%40example.com%3A8080%0D%0Ahttp%3A%2F%2Fuserid%3Apassword%40example.com%3A8080%2F%0D%0Ahttp%3A%2F%2Fuserid%40example.com%0D%0Ahttp%3A%2F%2Fuserid%40example.com%2F%0D%0Ahttp%3A%2F%2Fuserid%40example.com%3A8080%0D%0Ahttp%3A%2F%2Fuserid%40example.com%3A8080%2F%0D%0Ahttp%3A%2F%2Fuserid%3Apassword%40example.com%0D%0Ahttp%3A%2F%2Fuserid%3Apassword%40example.com%2F%0D%0Ahttp%3A%2F%2F142.42.1.1%2F%0D%0Ahttp%3A%2F%2F142.42.1.1%3A8080%2F%0D%0Ahttp%3A%2F%2F%E2%9E%A1.ws%2F%E4%A8%B9%0D%0Ahttp%3A%2F%2F%E2%8C%98.ws%0D%0Ahttp%3A%2F%2F%E2%8C%98.ws%2F%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_%28wikipedia%29%23cite-1%0D%0Ahttp%3A%2F%2Ffoo.com%2Fblah_%28wikipedia%29_blah%23cite-1%0D%0Ahttp%3A%2F%2Ffoo.com%2Funicode_%28%E2%9C%AA%29_in_parens%0D%0Ahttp%3A%2F%2Ffoo.com%2F%28something%29%3Fafter%3Dparens%0D%0Ahttp%3A%2F%2F%E2%98%BA.damowmow.com%2F%0D%0Ahttp%3A%2F%2Fcode.google.com%2Fevents%2F%23%26product%3Dbrowser%0D%0Ahttp%3A%2F%2Fj.mp%0D%0Aftp%3A%2F%2Ffoo.bar%2Fbaz%0D%0Ahttp%3A%2F%2Ffoo.bar%2F%3Fq%3DTest%2520URL-encoded%2520stuff%0D%0Ahttp%3A%2F%2F%D9%85%D8%AB%D8%A7%D9%84.%D8%A5%D8%AE%D8%AA%D8%A8%D8%A7%D8%B1%0D%0Ahttp%3A%2F%2F%E4%BE%8B%E5%AD%90.%E6%B5%8B%E8%AF%95%0D%0Ahttp%3A%2F%2F%E0%A4%89%E0%A4%A6%E0%A4%BE%E0%A4%B9%E0%A4%B0%E0%A4%A3.%E0%A4%AA%E0%A4%B0%E0%A5%80%E0%A4%95%E0%A5%8D%E0%A4%B7%E0%A4%BE%0D%0Ahttp%3A%2F%2F-.~_%21%24%26%27%28%29%2A%2B%2C%3B%3D%3A%2540%3A80%252f%3A%3A%3A%3A%3A%3A%40example.com%0D%0Ahttp%3A%2F%2F1337.net%0D%0Ahttp%3A%2F%2Fa.b-c.de%0D%0Ahttp%3A%2F%2F223.255.255.254%0D%0A%0D%0ASHOULD%20NOT%20MATCH%3A%0D%0A%0D%0Ahttp%3A%2F%2F%0D%0Ahttp%3A%2F%2F.%0D%0Ahttp%3A%2F%2F..%0D%0Ahttp%3A%2F%2F..%2F%0D%0Ahttp%3A%2F%2F%3F%0D%0Ahttp%3A%2F%2F%3F%3F%0D%0Ahttp%3A%2F%2F%3F%3F%2F%0D%0Ahttp%3A%2F%2F%23%0D%0Ahttp%3A%2F%2F%23%23%0D%0Ahttp%3A%2F%2F%23%23%2F%0D%0Ahttp%3A%2F%2Ffoo.bar%3Fq%3DSpaces%20should%20be%20encoded%0D%0A%2F%2F%0D%0A%2F%2Fa%0D%0A%2F%2F%2Fa%0D%0A%2F%2F%2F%0D%0Ahttp%3A%2F%2F%2Fa%0D%0Afoo.com%0D%0Ardar%3A%2F%2F1234%0D%0Ah%3A%2F%2Ftest%0D%0Ahttp%3A%2F%2F%20shouldfail.com%0D%0A%3A%2F%2F%20should%20fail%0D%0Ahttp%3A%2F%2Ffoo.bar%2Ffoo%28bar%29baz%20quux%0D%0Aftps%3A%2F%2Ffoo.bar%2F%0D%0Ahttp%3A%2F%2F-error-.invalid%2F%0D%0Ahttp%3A%2F%2Fa.b--c.de%2F%0D%0Ahttp%3A%2F%2F-a.b.co%0D%0Ahttp%3A%2F%2Fa.b-.co%0D%0Ahttp%3A%2F%2F0.0.0.0%0D%0Ahttp%3A%2F%2F10.1.1.0%0D%0Ahttp%3A%2F%2F10.1.1.255%0D%0Ahttp%3A%2F%2F224.1.1.1%0D%0Ahttp%3A%2F%2F1.1.1.1.1%0D%0Ahttp%3A%2F%2F123.123.123%0D%0Ahttp%3A%2F%2F3628126748%0D%0Ahttp%3A%2F%2F.www.foo.bar%2F%0D%0Ahttp%3A%2F%2Fwww.foo.bar.%2F%0D%0Ahttp%3A%2F%2F.www.foo.bar.%2F%0D%0Ahttp%3A%2F%2F10.1.1.1)

Diego Perini [posted his version as a gist](https://gist.github.com/729294).

| URL | Spoon Library | @krijnhoetmer | @gruber | @gruber v2 | @cowboy | Jeffrey Friedl | @mattfarina | @stephenhay | @scottgonzales | @rodneyrehm | @imme_emosol | @diegoperini | Using `filter_var()` |
| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| These URLs should match (`1` → correct) |
| `http://foo.com/blah_blah` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://foo.com/blah_blah/` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://foo.com/blah_blah_(wikipedia)` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` |
| `http://foo.com/blah_blah_(wikipedia)_(again)` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` |
| `http://www.example.com/wpstyle/?p=364` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `https://www.example.com/foo/?bar=baz&inga=42&quux` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://✪df.ws/123` | `0` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| `http://userid:password@example.com:8080` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid:password@example.com:8080/` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid@example.com` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid@example.com/` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid@example.com:8080` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid@example.com:8080/` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid:password@example.com` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://userid:password@example.com/` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://142.42.1.1/` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://142.42.1.1:8080/` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://➡.ws/䨹` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `1` | `0` |
| `http://⌘.ws` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| `http://⌘.ws/` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| `http://foo.com/blah_(wikipedia)#cite-1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://foo.com/blah_(wikipedia)_blah#cite-1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://foo.com/unicode_(✪)_in_parens` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| `http://foo.com/(something)?after=parens` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://☺.damowmow.com/` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| `http://code.google.com/events/#&product=browser` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://j.mp` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `ftp://foo.bar/baz` | `0` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://foo.bar/?q=Test%20URL-encoded%20stuff` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://مثال.إختبار` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `1` | `0` |
| `http://例子.测试` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `1` | `0` |
| `http://उदाहरण.परीक्षा` | `0` | `0` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `1` | `1` | `0` |
| `http://-.~_!$&'()*+,;=:%40:80%2f::::::@example.com` | `0` | `1` | `0` | `1` | `1` | `0` | `0` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://1337.net` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://a.b-c.de` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` |
| `http://223.255.255.254` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `https://foo_bar.example.com/` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `0` |
| These URLs should fail (`0` → correct) |
| `http://` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `0` |
| `http://.` | `0` | `0` | `0` | `0` | `1` | `0` | `1` | `0` | `1` | `0` | `0` | `0` | `0` |
| `http://..` | `0` | `0` | `0` | `0` | `1` | `0` | `1` | `0` | `1` | `0` | `0` | `0` | `0` |
| `http://../` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://?` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `0` |
| `http://??` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `0` |
| `http://??/` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://#` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://##` | `0` | `1` | `0` | `1` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://##/` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://foo.bar?q=Spaces should be encoded` | `0` | `1` | `1` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `//` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `//a` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `///a` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `///` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `http:///a` | `0` | `1` | `1` | `1` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `foo.com` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `rdar://1234` | `0` | `0` | `1` | `1` | `1` | `0` | `1` | `0` | `1` | `0` | `0` | `0` | `1` |
| `h://test` | `0` | `0` | `1` | `0` | `1` | `0` | `1` | `0` | `1` | `0` | `0` | `0` | `1` |
| `http:// shouldfail.com` | `0` | `0` | `0` | `0` | `1` | `0` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `:// should fail` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` | `0` |
| `http://foo.bar/foo(bar)baz quux` | `0` | `1` | `1` | `1` | `1` | `1` | `0` | `0` | `1` | `1` | `0` | `0` | `0` |
| `ftps://foo.bar/` | `0` | `0` | `1` | `1` | `1` | `0` | `1` | `0` | `1` | `0` | `0` | `0` | `1` |
| `http://-error-.invalid/` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `0` | `0` |
| `http://a.b--c.de/` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` | `1` |
| `http://-a.b.co` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `0` | `0` |
| `http://a.b-.co` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `0` | `0` |
| `http://0.0.0.0` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://10.1.1.0` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://10.1.1.255` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://224.1.1.1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://1.1.1.1.1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://123.123.123` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://3628126748` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://.www.foo.bar/` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://www.foo.bar./` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` |
| `http://.www.foo.bar./` | `0` | `1` | `1` | `1` | `1` | `0` | `1` | `0` | `1` | `1` | `0` | `0` | `0` |
| `http://10.1.1.1` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |
| `http://10.1.1.254` | `0` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `1` | `0` | `1` |

## Spoon Library (979 chars)

```
/(((http|ftp|https):\/{2})+(([0-9a-z_-]+\.)+(aero|asia|biz|cat|com|coop|edu|gov|info|int|jobs|mil|mobi|museum|name|net|org|pro|tel|travel|ac|ad|ae|af|ag|ai|al|am|an|ao|aq|ar|as|at|au|aw|ax|az|ba|bb|bd|be|bf|bg|bh|bi|bj|bm|bn|bo|br|bs|bt|bv|bw|by|bz|ca|cc|cd|cf|cg|ch|ci|ck|cl|cm|cn|co|cr|cu|cv|cx|cy|cz|cz|de|dj|dk|dm|do|dz|ec|ee|eg|er|es|et|eu|fi|fj|fk|fm|fo|fr|ga|gb|gd|ge|gf|gg|gh|gi|gl|gm|gn|gp|gq|gr|gs|gt|gu|gw|gy|hk|hm|hn|hr|ht|hu|id|ie|il|im|in|io|iq|ir|is|it|je|jm|jo|jp|ke|kg|kh|ki|km|kn|kp|kr|kw|ky|kz|la|lb|lc|li|lk|lr|ls|lt|lu|lv|ly|ma|mc|md|me|mg|mh|mk|ml|mn|mn|mo|mp|mr|ms|mt|mu|mv|mw|mx|my|mz|na|nc|ne|nf|ng|ni|nl|no|np|nr|nu|nz|nom|pa|pe|pf|pg|ph|pk|pl|pm|pn|pr|ps|pt|pw|py|qa|re|ra|rs|ru|rw|sa|sb|sc|sd|se|sg|sh|si|sj|sj|sk|sl|sm|sn|so|sr|st|su|sv|sy|sz|tc|td|tf|tg|th|tj|tk|tl|tm|tn|to|tp|tr|tt|tv|tw|tz|ua|ug|uk|us|uy|uz|va|vc|ve|vg|vi|vn|vu|wf|ws|ye|yt|yu|za|zm|zw|arpa)(:[0-9]+)?((\/([~0-9a-zA-Z\#\+\%@\.\/_-]+))?(\?[0-9a-zA-Z\+\%@\/&\[\];=_-]+)?)?))\b/imuS
```

## @krijnhoetmer (115 chars)

```
_(^|[\s.:;?\-\]<\(])(https?://[-\w;/?:@&=+$\|\_.!~*\|'()\[\]%#,☺]+[\w/#](\(\))?)(?=$|[\s',\|\(\).:;?\-\[\]>\)])_i
```

## @gruber (71 chars)

```
#\b(([\w-]+://?|www[.])[^\s()<>]+(?:\([\w\d]+\)|([^[:punct:]\s]|/)))#iS
```

## @gruber v2 (218 chars)

```
#(?i)\b((?:[a-z][\w-]+:(?:/{1,3}|[a-z0-9%])|www\d{0,3}[.]|[a-z0-9.\-]+[.][a-z]{2,4}/)(?:[^\s()<>]+|\(([^\s()<>]+|(\([^\s()<>]+\)))*\))+(?:\(([^\s()<>]+|(\([^\s()<>]+\)))*\)|[^\s`!()\[\]{};:'".,<>?«»“”‘’]))#iS
```

## @cowboy (1241 chars)

```
~(?:\b[a-z\d.-]+://[^<>\s]+|\b(?:(?:(?:[^\s!@#$%^&*()_=+[\]{}\|;:'",.<>/?]+)\.)+(?:ac|ad|aero|ae|af|ag|ai|al|am|an|ao|aq|arpa|ar|asia|as|at|au|aw|ax|az|ba|bb|bd|be|bf|bg|bh|biz|bi|bj|bm|bn|bo|br|bs|bt|bv|bw|by|bz|cat|ca|cc|cd|cf|cg|ch|ci|ck|cl|cm|cn|coop|com|co|cr|cu|cv|cx|cy|cz|de|dj|dk|dm|do|dz|ec|edu|ee|eg|er|es|et|eu|fi|fj|fk|fm|fo|fr|ga|gb|gd|ge|gf|gg|gh|gi|gl|gm|gn|gov|gp|gq|gr|gs|gt|gu|gw|gy|hk|hm|hn|hr|ht|hu|id|ie|il|im|info|int|in|io|iq|ir|is|it|je|jm|jobs|jo|jp|ke|kg|kh|ki|km|kn|kp|kr|kw|ky|kz|la|lb|lc|li|lk|lr|ls|lt|lu|lv|ly|ma|mc|md|me|mg|mh|mil|mk|ml|mm|mn|mobi|mo|mp|mq|mr|ms|mt|museum|mu|mv|mw|mx|my|mz|name|na|nc|net|ne|nf|ng|ni|nl|no|np|nr|nu|nz|om|org|pa|pe|pf|pg|ph|pk|pl|pm|pn|pro|pr|ps|pt|pw|py|qa|re|ro|rs|ru|rw|sa|sb|sc|sd|se|sg|sh|si|sj|sk|sl|sm|sn|so|sr|st|su|sv|sy|sz|tc|td|tel|tf|tg|th|tj|tk|tl|tm|tn|to|tp|travel|tr|tt|tv|tw|tz|ua|ug|uk|um|us|uy|uz|va|vc|ve|vg|vi|vn|vu|wf|ws|xn--0zwm56d|xn--11b5bs3a9aj6g|xn--80akhbyknj4f|xn--9t4b11yi5a|xn--deba0ad|xn--g6w251d|xn--hgbk6aj7f53bba|xn--hlcj6aya9esc7a|xn--jxalpdlp|xn--kgbechtv|xn--zckzah|ye|yt|yu|za|zm|zw)|(?:(?:[0-9]|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5])\.){3}(?:[0-9]|[1-9]\d|1\d{2}|2[0-4]\d|25[0-5]))(?:[;/][^#?<>\s]*)?(?:\?[^#<>\s]*)?(?:#[^<>\s]*)?(?!\w))~iS
```

## Jeffrey Friedl (241 chars)

```
@\b((ftp|https?)://[-\w]+(\.\w[-\w]*)+|(?:[a-z0-9](?:[-a-z0-9]*[a-z0-9])?\.)+(?: com\b|edu\b|biz\b|gov\b|in(?:t|fo)\b|mil\b|net\b|org\b|[a-z][a-z]\b))(\:\d+)?(/[^.!,?;"'<>()\[\]{}\s\x7F-\xFF]*(?:[.!,?]+[^.!,?;"'<>()\[\]{}\s\x7F-\xFF]+)*)?@iS
```

## @mattfarina (287 chars)

```
/^([a-z][a-z0-9\*\-\.]*):\/\/(?:(?:(?:[\w\.\-\+!$&'\(\)*\+,;=]|%[0-9a-f]{2})+:)*(?:[\w\.\-\+%!$&'\(\)*\+,;=]|%[0-9a-f]{2})+@)?(?:(?:[a-z0-9\-\.]|%[0-9a-f]{2})+|(?:\[(?:[0-9a-f]{0,4}:)*(?:[0-9a-f]{0,4})\]))(?::[0-9]+)?(?:[\/|\?](?:[\w#!:\.\?\+=&@!$'~*,;\/\(\)\[\]\-]|%[0-9a-f]{2})*)?$/xiS
```

## @stephenhay (38 chars)

```
@^(https?|ftp)://[^\s/$.?#].[^\s]*$@iS
```

## @scottgonzales (1347 chars)

```
#([a-z]([a-z]|\d|\+|-|\.)*):(\/\/(((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:)*@)?((\[(|(v[\da-f]{1,}\.(([a-z]|\d|-|\.|_|~)|[!\$&'\(\)\*\+,;=]|:)+))\])|((\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.(\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.(\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5])\.(\d|[1-9]\d|1\d\d|2[0-4]\d|25[0-5]))|(([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=])*)(:\d*)?)(\/(([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)*)*|(\/((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)+(\/(([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)*)*)?)|((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)+(\/(([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)*)*)|((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)){0})(\?((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)|[\xE000-\xF8FF]|\/|\?)*)?(\#((([a-z]|\d|-|\.|_|~|[\x00A0-\xD7FF\xF900-\xFDCF\xFDF0-\xFFEF])|(%[\da-f]{2})|[!\$&'\(\)\*\+,;=]|:|@)|\/|\?)*)?#iS
```

## @rodneyrehm (109 chars)

```
#((https?://|ftp://|www\.|[^\s:=]+@www\.).*?[a-z_\/0-9\-\#=&])(?=(\.|,|;|\?|\!)?("|'|«|»|\[|\s|\r|\n|$))#iS
```

## @imme_emosol (54 chars)

```
@(https?|ftp)://(-\.)?([^\s/?\.#-]+\.?)+(/[^\s]*)?$@iS
```

## @diegoperini (443 chars)

```
%^(?:(?:(?:https?|ftp):)?\/\/)(?:\S+(?::\S*)?@)?(?:(?!(?:10|127)(?:\.\d{1,3}){3})(?!(?:169\.254|192\.168)(?:\.\d{1,3}){2})(?!172\.(?:1[6-9]|2\d|3[0-1])(?:\.\d{1,3}){2})(?:[1-9]\d?|1\d\d|2[01]\d|22[0-3])(?:\.(?:1?\d{1,2}|2[0-4]\d|25[0-5])){2}(?:\.(?:[1-9]\d?|1\d\d|2[0-4]\d|25[0-4]))|(?:(?:[a-z0-9\x{00a1}-\x{ffff}][a-z0-9\x{00a1}-\x{ffff}_-]{0,62})?[a-z0-9\x{00a1}-\x{ffff}]\.)+(?:[a-z\x{00a1}-\x{ffff}]{2,}\.?))(?::\d{2,5})?(?:[/?#]\S*)?$%iuS
```

— [Mathias](https://mathiasbynens.be/)
