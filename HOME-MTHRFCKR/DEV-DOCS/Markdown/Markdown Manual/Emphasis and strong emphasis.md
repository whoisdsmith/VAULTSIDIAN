{{($page.frontmatter.start = 360) ? null : null}}
### Emphasis and strong emphasis

John Gruber’s original [Markdown syntax description](http://daringfireball.net/projects/markdown/syntax#em) says:  

> Markdown treats asterisks (`*`) and underscores (`_`) as indicators of emphasis. Text wrapped with one `*` or `_` will be wrapped with an HTML `<em>` tag; double `*`’s or `_`’s will be wrapped with an HTML `<strong>` tag.

This is enough for most users, but these rules leave much undecided, especially when it comes to nested emphasis. The original `Markdown.pl` test suite makes it clear that triple `***` and `___` delimiters can be used for strong emphasis, and most implementations have also allowed the following patterns:  

    ***strong emph***
    ***strong** in emph*
    ***emph* in strong**
    **in strong *emph***
    *in emph **strong***

The following patterns are less widely supported, but the intent is clear and they are useful (especially in contexts like bibliography entries):  

    *emph *with emph* in it*
    **strong **with strong** in it**

Many implementations have also restricted intraword emphasis to the `*` forms, to avoid unwanted emphasis in words containing internal underscores. (It is best practice to put these in code spans, but users often do not.)  

    internal emphasis: foo*bar*baz
    no emphasis: foo_bar_baz

The rules given below capture all of these patterns, while allowing for efficient parsing strategies that do not backtrack.  
First, some definitions. A [delimiter run](https://github.github.com/gfm/#delimiter-run) is either a sequence of one or more `*` characters that is not preceded or followed by a non-backslash-escaped `*` character, or a sequence of one or more `_` characters that is not preceded or followed by a non-backslash-escaped `_` character.  
A [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) is a [delimiter run](https://github.github.com/gfm/#delimiter-run) that is (1) not followed by [Unicode whitespace](https://github.github.com/gfm/#unicode-whitespace), and either (2a) not followed by a [punctuation character](https://github.github.com/gfm/#punctuation-character),or (2b) followed by a punctuation character and preceded by [Unicode whitespace](https://github.github.com/gfm/#unicode-whitespace) or a [punctuation character](https://github.github.com/gfm/#punctuation-character). For purposes of this definition, the beginning and the end of the line count as Unicode whitespace.  
A [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) is a [delimiter run](https://github.github.com/gfm/#delimiter-run) that is (1) not preceded by [Unicode whitespace](https://github.github.com/gfm/#unicode-whitespace), and either (2a) not preceded by a punctuation character,or (2b) preceded by a punctuation character  and followed by [Unicode whitespace](https://github.github.com/gfm/#unicode-whitespace) or a [punctuation character](https://github.github.com/gfm/#punctuation-character). For purposes of this definition, the beginning and the end of the line count as Unicode whitespace.  
Here are some examples of delimiter runs.  

*   left-flanking but not right-flanking:  
    
        ***abc
          _abc
        **"abc"
         _"abc"
    
*   right-flanking but not left-flanking:  
    
         abc***
         abc_
        "abc"**
        "abc"_
    
*   Both left and right-flanking:  
    
         abc***def
        "abc"_"def"
    
*   Neither left nor right-flanking:  
    
        abc *** def
        a _ b
    

(The idea of distinguishing left-flanking and right-flanking delimiter runs based on the character before and the character after comes from Roopesh Chander’s [vfmd](http://www.vfmd.org/vfmd-spec/specification/#procedure-for-identifying-emphasis-tags). vfmd uses the terminology “emphasis indicator string” instead of “delimiter run,” and its rules for distinguishing left- and right-flanking runs are a bit more complex than the ones given here.)  
The following rules define emphasis and strong emphasis:  

1.  A single `*` character [can open emphasis](https://github.github.com/gfm/#can-open-emphasis) iff (if and only if) it is part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run).
2.  A single `_` character [can open emphasis](https://github.github.com/gfm/#can-open-emphasis) iff it is part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) and either (a) not part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) or (b) part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) preceded by punctuation.
3.  A single `*` character [can close emphasis](https://github.github.com/gfm/#can-close-emphasis) iff it is part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run).
4.  A single `_` character [can close emphasis](https://github.github.com/gfm/#can-close-emphasis) iff it is part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) and either (a) not part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) or (b) part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) followed by punctuation.
5.  A double `**` [can open strong emphasis](https://github.github.com/gfm/#can-open-strong-emphasis) iff it is part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run).
6.  A double `__` [can open strong emphasis](https://github.github.com/gfm/#can-open-strong-emphasis) iff it is part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) and either (a) not part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) or (b) part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) preceded by punctuation.
7.  A double `**` [can close strong emphasis](https://github.github.com/gfm/#can-close-strong-emphasis) iff it is part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run).
8.  A double `__` [can close strong emphasis](https://github.github.com/gfm/#can-close-strong-emphasis) iff it is part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run) and either (a) not part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) or (b) part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run) followed by punctuation.
9.  Emphasis begins with a delimiter that [can open emphasis](https://github.github.com/gfm/#can-open-emphasis) and ends with a delimiter that [can close emphasis](https://github.github.com/gfm/#can-close-emphasis), and that uses the same character (`_` or `*`) as the opening delimiter. The opening and closing delimiters must belong to separate [delimiter runs](https://github.github.com/gfm/#delimiter-run). If one of the delimiters can both open and close emphasis, then the sum of the lengths of the delimiter runs containing the opening and closing delimiters must not be a multiple of 3 unless both lengths are multiples of 3.
10.  Strong emphasis begins with a delimiter that [can open strong emphasis](https://github.github.com/gfm/#can-open-strong-emphasis) and ends with a delimiter that[can close strong emphasis](https://github.github.com/gfm/#can-close-strong-emphasis), and that uses the same character (`_` or `*`) as the opening delimiter. The opening and closing delimiters must belong to separate [delimiter runs](https://github.github.com/gfm/#delimiter-run). If one of the delimiters can both open and close strong emphasis, then the sum of the lengths of the delimiter runs containing the opening and closing delimiters must not be a multiple of 3 unless both lengths are multiples of 3.
11.  A literal `*` character cannot occur at the beginning or end of `*`\-delimited emphasis or `**`\-delimited strong emphasis, unless it is backslash-escaped.
12.  A literal `_` character cannot occur at the beginning or end of `_`\-delimited emphasis or `__`\-delimited strong emphasis, unless it is backslash-escaped.

Where rules 1–12 above are compatible with multiple parsings, the following principles resolve ambiguity:  

13.  The number of nestings should be minimized. Thus, for example, an interpretation `<strong>...</strong>` is always preferred to `<em><em>...</em></em>`.
14.  An interpretation `<em><strong>...</strong></em>` is always preferred to `<strong><em>...</em></strong>`.
15.  When two potential emphasis or strong emphasis spans overlap, so that the second begins before the first ends and ends after the first ends, the first takes precedence. Thus, for example, `*foo _bar* baz_` is parsed as `<em>foo _bar</em> baz_` rather than `*foo <em>bar* baz</em>`.
16.  When there are two potential emphasis or strong emphasis spans with the same closing delimiter, the shorter one (the one that opens later) takes precedence. Thus, for example, `**foo **bar baz**` is parsed as `**foo <strong>bar baz</strong>` rather than `<strong>foo **bar baz</strong>`.
17.  Inline code spans, links, images, and HTML tags group more tightly than emphasis. So, when there is a choice between an interpretation that contains one of these elements and one that does not, the former always wins. Thus, for example, `*[foo*](bar)` is parsed as `*<a href="bar">foo*</a>` rather than as `<em>[foo</em>](bar)`.

These rules can be illustrated through a series of examples.  
Rule 1:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the opening `*` is followed by whitespace, and hence not part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run):  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the opening `*` is preceded by an alphanumeric and followed by punctuation, and hence not part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run):  
<Example :index="$page.frontmatter.start++"/>

Unicode nonbreaking spaces count as whitespace, too:  
<Example :index="$page.frontmatter.start++"/>

Intraword emphasis with `*` is permitted:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 2:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the opening `_` is followed by whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the opening `_` is preceded by an alphanumeric and followed by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Emphasis with `_` is not allowed inside words:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Here `_` does not generate emphasis, because the first delimiter run is right-flanking and the second left-flanking:  
<Example :index="$page.frontmatter.start++"/>

This is emphasis, even though the opening delimiter is both left- and right-flanking, because it is preceded by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Rule 3:  
This is not emphasis, because the closing delimiter does not match the opening delimiter:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the closing `*` is preceded by whitespace:  
<Example :index="$page.frontmatter.start++"/>

A newline also counts as whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the second `*` is preceded by punctuation and followed by an alphanumeric (hence it is not part of a [right-flanking delimiter run](https://github.github.com/gfm/#right-flanking-delimiter-run):  
<Example :index="$page.frontmatter.start++"/>

The point of this restriction is more easily appreciated with this example:  
<Example :index="$page.frontmatter.start++"/>

Intraword emphasis with `*` is allowed:  
<Example :index="$page.frontmatter.start++"/>

Rule 4:  
This is not emphasis, because the closing `_` is preceded by whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not emphasis, because the second `_` is preceded by punctuation and followed by an alphanumeric:  
<Example :index="$page.frontmatter.start++"/>

This is emphasis within emphasis:  
<Example :index="$page.frontmatter.start++"/>

Intraword emphasis is disallowed for `_`:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is emphasis, even though the closing delimiter is both left- and right-flanking, because it is followed by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Rule 5:  
<Example :index="$page.frontmatter.start++"/>

This is not strong emphasis, because the opening delimiter is followed by whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not strong emphasis, because the opening `**` is preceded by an alphanumeric and followed by punctuation, and hence not part of a [left-flanking delimiter run](https://github.github.com/gfm/#left-flanking-delimiter-run):  
<Example :index="$page.frontmatter.start++"/>

Intraword strong emphasis with `**` is permitted:  
<Example :index="$page.frontmatter.start++"/>

Rule 6:  
<Example :index="$page.frontmatter.start++"/>

This is not strong emphasis, because the opening delimiter is followed by whitespace:  
<Example :index="$page.frontmatter.start++"/>

A newline counts as whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not strong emphasis, because the opening `__` is preceded by an alphanumeric and followed by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Intraword strong emphasis is forbidden with `__`:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is strong emphasis, even though the opening delimiter is both left- and right-flanking, because it is preceded by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Rule 7:  
This is not strong emphasis, because the closing delimiter is preceded by whitespace:  
<Example :index="$page.frontmatter.start++"/>

(Nor can it be interpreted as an emphasized `*foo bar *`, because of Rule 11.)  
This is not strong emphasis, because the second `**` is preceded by punctuation and followed by an alphanumeric:  
<Example :index="$page.frontmatter.start++"/>

The point of this restriction is more easily appreciated with these examples:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Intraword emphasis:  
<Example :index="$page.frontmatter.start++"/>

Rule 8:  
This is not strong emphasis, because the closing delimiter is preceded by whitespace:  
<Example :index="$page.frontmatter.start++"/>

This is not strong emphasis, because the second `__` is preceded by punctuation and followed by an alphanumeric:  
<Example :index="$page.frontmatter.start++"/>

The point of this restriction is more easily appreciated with this example:  
<Example :index="$page.frontmatter.start++"/>

Intraword strong emphasis is forbidden with `__`:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

This is strong emphasis, even though the closing delimiter is both left- and right-flanking, because it is followed by punctuation:  
<Example :index="$page.frontmatter.start++"/>

Rule 9:  
Any nonempty sequence of inline elements can be the contents of an emphasized span.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

In particular, emphasis and strong emphasis can be nested inside emphasis:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that in the preceding case, the interpretation  

    <p><em>foo</em><em>bar<em></em>baz</em></p>

is precluded by the condition that a delimiter that can both open and close (like the `*` after `foo`) cannot form emphasis if the sum of the lengths of the delimiter runs containing the opening and closing delimiters is a multiple of 3 unless both lengths are multiples of 3.

For the same reason, we don’t get two consecutive emphasis sections in this example:  
<Example :index="$page.frontmatter.start++"/>

The same condition ensures that the following cases are all strong emphasis nested inside emphasis, even when the interior spaces are omitted:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

When the lengths of the interior closing and opening delimiter runs are *both* multiples of 3, though, they can match to create emphasis:    
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Indefinite levels of nesting are possible:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

There can be no empty emphasis or strong emphasis:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 10:  
Any nonempty sequence of inline elements can be the contents of an strongly emphasized span.  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

In particular, emphasis and strong emphasis can be nested inside strong emphasis:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Indefinite levels of nesting are possible:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

There can be no empty emphasis or strong emphasis:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 11:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that when delimiters do not match evenly, Rule 11 determines that the excess literal `*` characters will appear outside of the emphasis, rather than inside it:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 12:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Note that when delimiters do not match evenly, Rule 12 determines that the excess literal `_` characters will appear outside of the emphasis, rather than inside it:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 13 implies that if you want emphasis nested directly inside emphasis, you must use different delimiters:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

However, strong emphasis within strong emphasis is possible without switching delimiters:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 13 can be applied to arbitrarily long sequences of delimiters:  
<Example :index="$page.frontmatter.start++"/>

Rule 14:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 15:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 16:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

Rule 17:  
<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>

<Example :index="$page.frontmatter.start++"/>
