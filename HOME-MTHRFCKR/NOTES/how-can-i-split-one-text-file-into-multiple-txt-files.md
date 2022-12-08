# linux - How can I split one text file into multiple *.txt files? - Stack Overflow

> ## Excerpt
> I got a text file file.txt (12 MB) containing:
something1
something2
something3
something4
(...)

Is there a way to split file.txt into 12 *.txt files, let’s say file2.txt, file3.txt, file4.txt, etc.?

---
I got a text file `file.txt` (12 MB) containing:

```
something1
something2
something3
something4
(...)
```

Is there a way to split `file.txt` into 12 \*.txt files, let’s say `file2.txt`, `file3.txt`, `file4.txt`, etc.?

[

![](https://i.stack.imgur.com/RIZKi.png?s=64&g=1)

](https://stackoverflow.com/users/63550/peter-mortensen)

asked Sep 26 '13 at 14:34

[

![](https://www.gravatar.com/avatar/67976c35019342bba1856a9825cc2962?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/2643234/kris)

You can use the Linux Bash core utility `split`:

```
split -b 1M -d  file.txt file
```

Note that `M` or `MB` both are OK but size is different. MB is 1000 \* 1000, M is 1024^2

If you want to separate by lines you can use `-l` parameter.

**UPDATE**

```
a=(`wc -l yourfile`) ; lines=`echo $(($a/12)) | bc -l` ; split -l $lines -d  file.txt file
```

Another solution as suggested by [Kirill](https://stackoverflow.com/users/3115669/kirill), you can do something like the following

```
split -n l/12 file.txt
```

Note that is `l` not `one`, `split -n` has a few options, like `N`, `k/N`, `l/k/N`, `r/N`, `r/k/N`.

[

![](https://i.stack.imgur.com/RIZKi.png?s=64&g=1)

](https://stackoverflow.com/users/63550/peter-mortensen)

answered Sep 26 '13 at 14:37

[

![](https://www.gravatar.com/avatar/fee10843adffc656f32cdfa67aa425c5?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/1153165/cs-pei)

[CS Pei](https://stackoverflow.com/users/1153165/cs-pei)CS Pei

10.4k1 gold badge24 silver badges44 bronze badges

7

```
$ split -l 100 input_file output_file
```

where `-l` is the number of lines in each files. This will create:

-   output\_fileaa
-   output\_fileab
-   output\_fileac
-   output\_filead
-   ....

[

![](https://i.stack.imgur.com/6fMZI.png?s=64&g=1)

](https://stackoverflow.com/users/33204/slm)

[slm](https://stackoverflow.com/users/33204/slm)

13.5k12 gold badges92 silver badges111 bronze badges

answered Sep 18 '14 at 11:08

[

![](https://www.gravatar.com/avatar/753b868e020c9afa0f587738c40931b6?s=64&d=identicon&r=PG&f=1)

](https://stackoverflow.com/users/4054170/amruta-takawale)

5

CS Pei's answer won't produce .txt files as the OP wants. Use:

```
split -b=1M -d  file.txt file --additional-suffix=.txt
```

answered May 19 '16 at 9:52

[

![](https://www.gravatar.com/avatar/6f0349bd99a58e30ae88b11111696144?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/1773592/schoon)

[schoon](https://stackoverflow.com/users/1773592/schoon)schoon

2,1923 gold badges32 silver badges59 bronze badges

4

Using [Bash](https://www.gnu.org/software/bash/manual/bash.html#What-is-Bash_003f):

```
readarray -t lines < file.txt
count=${#lines[@]}

for i in "${!lines[@]}"; do
    index=$(( (i * 12 - 1) / count + 1 ))
    echo "${lines[i]}" >> "file${index}.txt"
done
```

Using [AWK](https://en.wikipedia.org/wiki/AWK):

```
awk '{
    a[NR] = $0
}
END {
    for (i = 1; i in a; ++i) {
        x = (i * 12 - 1) / NR + 1
        sub(/\..*$/, "", x)
        print a[i] > "file" x ".txt"
    }
}' file.txt
```

Unlike `split`, this one makes sure that the number of lines are most even.

answered Sep 26 '13 at 15:03

[

![](https://www.gravatar.com/avatar/6bcf75dbf1e66fc9cf453393db706d2d?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/445221/konsolebox)

[konsolebox](https://stackoverflow.com/users/445221/konsolebox)konsolebox

65k11 gold badges92 silver badges100 bronze badges

3

Regardless to what was said in previous answers, on my [Ubuntu 16.04](https://en.wikipedia.org/wiki/Ubuntu_version_history#Ubuntu_16.04_LTS_.28Xenial_Xerus.29) (Xenial Xerus) I had to do:

```
split -b 10M -d  system.log system_split.log
```

Please note the _space_ between `-b` and the value.

[

![](https://i.stack.imgur.com/RIZKi.png?s=64&g=1)

](https://stackoverflow.com/users/63550/peter-mortensen)

answered Jan 26 '17 at 12:04

[

![](https://lh4.googleusercontent.com/-7ZhsocyZNmU/AAAAAAAAAAI/AAAAAAAAAlc/1h_xkkHnlXg/photo.jpg?sz=64)

](https://stackoverflow.com/users/5134452/nicolas-d)

[Nicolas D](https://stackoverflow.com/users/5134452/nicolas-d)Nicolas D

1,10214 silver badges39 bronze badges

2

On my Linux system (Red Hat Enterprise 6.9), the `split` command does not have the command-line options for either `-n` or `--additional-suffix`.

Instead, I've used this:

```
split -d -l NUM_LINES really_big_file.txt split_files.txt.
```

where `-d` is to add a numeric suffix to the end of the `split_files.txt.` and `-l` specifies the number of lines per file.

For example, suppose I have a really big file like this:

```
$ ls -laF
total 1391952
drwxr-xr-x 2 user.name group         40 Sep 14 15:43 ./
drwxr-xr-x 3 user.name group       4096 Sep 14 15:39 ../
-rw-r--r-- 1 user.name group 1425352817 Sep 14 14:01 really_big_file.txt
```

This file has 100,000 lines, and I want to split it into files with at most 30,000 lines. This command will run the split and append an integer at the end of the output file pattern `split_files.txt.`.

```
$ split -d -l 30000 really_big_file.txt split_files.txt.
```

The resulting files are split correctly with at most 30,000 lines per file.

```
$ ls -laF
total 2783904
drwxr-xr-x 2 user.name group        156 Sep 14 15:43 ./
drwxr-xr-x 3 user.name group       4096 Sep 14 15:39 ../
-rw-r--r-- 1 user.name group 1425352817 Sep 14 14:01 really_big_file.txt
-rw-r--r-- 1 user.name group  428604626 Sep 14 15:43 split_files.txt.00
-rw-r--r-- 1 user.name group  427152423 Sep 14 15:43 split_files.txt.01
-rw-r--r-- 1 user.name group  427141443 Sep 14 15:43 split_files.txt.02
-rw-r--r-- 1 user.name group  142454325 Sep 14 15:43 split_files.txt.03


$ wc -l *.txt*
    100000 really_big_file.txt
     30000 split_files.txt.00
     30000 split_files.txt.01
     30000 split_files.txt.02
     10000 split_files.txt.03
    200000 total
```

answered Sep 14 '18 at 22:49

[

![](https://www.gravatar.com/avatar/6ad3771ba6e8e823dbcae710c1cde4da?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/4561314/stackoverflowuser2010)

I agree with @CS Pei, however this didn't work for me:

`split -b=1M -d file.txt file`

...as the `=` after `-b` threw it off. Instead, I simply deleted it and left no space between it and the variable, and used lowercase "m":

`split -b1m -d file.txt file`

And to append ".txt", we use what @schoon said:

`split -b=1m -d file.txt file --additional-suffix=.txt`

I had a 188.5MB txt file and I used this command \[but with `-b5m` for 5.2MB files\], and it returned 35 split files all of which were txt files and 5.2MB except the last which was 5.0MB. Now, since I wanted my lines to stay whole, I wanted to split the main file every 1 million lines, but the `split` command didn't allow me to even do `-100000` let alone "`-1000000`, so large numbers of lines to split will not work.

answered Sep 29 '17 at 18:56

[

![](https://www.gravatar.com/avatar/882430e16a40a14f83c418c74a184825?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/8697029/ryan)

1

If each part has the same number of lines, for example 22, here is my solution:

```
split --numeric-suffixes=2 --additional-suffix=.txt -l 22 file.txt file
```

And you obtain _file2.txt_ with the first 22 lines, _file3.txt_ the 22 next line, etc.

Thank @hamruta-takawale, @dror-s and @stackoverflowuser2010

[

![](https://i.stack.imgur.com/RIZKi.png?s=64&g=1)

](https://stackoverflow.com/users/63550/peter-mortensen)

answered Apr 23 '20 at 16:47

[

![](https://i.stack.imgur.com/I4eFO.jpg?s=64&g=1)

](https://stackoverflow.com/users/6614155/bcag2)

[bcag2](https://stackoverflow.com/users/6614155/bcag2)bcag2

1,4961 gold badge11 silver badges25 bronze badges

Try something like this:

```
awk -vc=1 'NR%1000000==0{++c}{print $0 > c".txt"}' Datafile.txt

for filename in *.txt; do mv "$filename" "Prefix_$filename"; done;
```

[

![](https://i.stack.imgur.com/STtQt.jpg?s=64&g=1)

](https://stackoverflow.com/users/6498018/pheeleeppoo)

[pheeleeppoo](https://stackoverflow.com/users/6498018/pheeleeppoo)

1,3815 gold badges22 silver badges26 bronze badges

answered Apr 3 '17 at 14:33

[

![](https://www.gravatar.com/avatar/97cb6091958a719e1647b8342317d4aa?s=64&d=identicon&r=PG)

](https://stackoverflow.com/users/7809190/morgan32)

## Your Answer

-   Links
-   Images
-   Styling/Headers
-   Lists
-   Blockquotes
-   Code
-   HTML
-   Tables
-   [Advanced help](https://stackoverflow.com/editing-help)

In most cases, a plain URL will be recognized as such and automatically linked:

Visit https://area51.stackexchange.com/ regularly!
Use angle brackets to force linking: Have you seen <https://superuser.com>?

To create fancier links, use Markdown:

Here's \[a link\](https://www.example.com/)! And a reference-style link to \[a panda\]\[1\].
References don't have to be \[numbers\]\[question\].

 \[1\]: https://notfound.stackexchange.com/
 \[question\]: https://english.stackexchange.com/questions/11481

You can add tooltips to links:

Click \[here\](https://diy.stackexchange.com "this text appears when you mouse over")!
This works with \[reference links\]\[blog\] as well.

 \[blog\]: https://stackoverflow.blog/ "click here for updates"

Images are exactly like links, but they have an exclamation point in front of them:

!\[a busy cat\](https://cdn.sstatic.net/Sites/stackoverflow/Img/error-lolcat-problemz.jpg)
!\[two muppets\]\[1\]

 \[1\]: https://i.imgur.com/I5DFV.jpg "tooltip"

The word in square brackets is the alt text, which gets displayed if the browser can't show the image. Be sure to include meaningful alt text for screen-reading software.

Be sure to use text styling sparingly; only where it helps readability.

\*This is italicized\*, and so
is \_this\_.

\*\*This is bold\*\*, just like \_\_this\_\_.

You can \*\*\*combine\*\*\* them
if you \_\_\_really have to\_\_\_.

To break your text into sections, you can use headers:

A Large Header
==============

Smaller Subheader
-----------------

Use hash marks if you need several levels of headers:

\# Header 1 #
## Header 2 ##
### Header 3 ###

Both bulleted and numbered lists are possible:

\- Use a minus sign for a bullet
+ Or plus sign
\* Or an asterisk

1. Numbered lists are easy
2. Markdown keeps track of
   the numbers for you
7. So this will be item 3.

1. Lists in a list item:
 \- Indented four spaces.
 \* indented eight spaces.
 \- Four spaces again.
2. You can have multiple
 paragraphs in a list items.
 
 Just be sure to indent.

\> Create a blockquote by
> prepending “>” to each line.
>
> Other formatting also works here, e.g.
>
> 1. Lists or
> 2. Headings:
>
> ## Quoted Heading ##

You can even put blockquotes in blockquotes:

\> A standard blockquote is indented
> > A nested blockquote is indented more
> > > > You can nest to any depth.

To create code blocks or other preformatted text, indent by four spaces or surround with groups of backticks:

 This will be displayed in a monospaced font. The first four spaces
 will be stripped off, but all other whitespace will be preserved.

\`\`\`
Markdown and HTML are turned off in code blocks:
<i>This is not italic</i>, and \[this is not a link\](https://example.com)
\`\`\`

To create not a block, but an inline code span, use backticks:

The \`$\` character is just a shortcut for \`window.jQuery\`.

If you want to have a preformatted block within a list, indent by eight spaces:

1\. This is normal text.
2. So is this, but now follows a code block:
 
 Skip a line and indent eight spaces.
 That's four spaces for the list
 and four to trigger the code block.

If you need to do something that Markdown can't handle, use HTML. Note that [we only support a very strict subset of HTML!](https://meta.stackexchange.com/questions/1777/what-html-tags-are-allowed)

Strikethrough humor is <strike>funny</strike>.

Markdown is smart enough not to mangle your span-level HTML:

<b>Markdown works \*fine\* in here.</b>

Block-level HTML elements have a few restrictions:

1.  They must be separated from surrounding text by blank lines.
2.  The begin and end tags of the outermost block element must not be indented.
3.  Markdown can't be used within HTML blocks.

  

<pre>
    You can <em>not</em> use Markdown in here.
</pre>

You can create tables using the [GitHub-flavored markdown format](https://github.github.com/gfm/#tables-extension-).

| A header | Another header |
| -------- | -------------- |
| First    | row            |
| Second   | row            |

-   A header row is required and must be followed by a separator row with the same number of cells
-   Cells are separated by a pipe (`|`) symbol

Set the **alignment** of a table column by placing a `:` on the left, right, or both sides of a separator in the separator line.

| left | center | right |
|:---- |:------:| -----:|
| One  | Two    | Three |

## Not the answer you're looking for? Browse other questions tagged [linux](https://stackoverflow.com/questions/tagged/linux "show questions tagged 'linux'") [bash](https://stackoverflow.com/questions/tagged/bash "show questions tagged 'bash'") or [ask your own question](https://stackoverflow.com/questions/ask).
