# Computing from the Command Line

## [Preface](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#preface)

This book aims to teach Linux command line tools and Shell Scripting for beginner to intermediate level users. The focus is towards managing your files and performing text processing tasks. Topics like system administration and networking won't be discussed, but some details might get covered in future versions of this book.

## [Prerequisites](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#prerequisites)

You should be familiar with basic computer usage, know fundamental terms like files and directories, how to install programs and so on. You should also be already comfortable with programming basics like variables, loops and functions.

In terms of software, you should have access to the `GNU bash` shell and commonly used Linux command line tools. This could be as part of a Linux distribution or via other means such as a Virtual Machine, WSL (Windows Subsystem for Linux) and so on. More details about the working environment will be discussed in the introductory chapters.

You are also expected to get comfortable with reading manuals, searching online, visiting external links provided for further reading, tinkering with illustrated examples, asking for help when you are stuck and so on. In other words, be proactive and curious instead of just consuming the content passively.

See my curated list on [Linux CLI and Shell Scripting](https://learnbyexample.github.io/curated_resources/linux_cli_scripting.html) for more learning resources.

## [Conventions](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#conventions)

-   Code snippets shown are copy pasted from the `bash` shell (version **5.0.17**) and modified for presentation purposes. Some commands are preceded by comments to provide context and explanations, blank lines have been added to improve readability and so on.
-   External links are provided throughout the book for you to explore certain topics in more depth.
-   The [cli-computing repo](https://github.com/learnbyexample/cli-computing) has all the [example files and scripts](https://github.com/learnbyexample/cli-computing/tree/master/example_files) used in the book. The repo also includes all the [exercises](https://github.com/learnbyexample/cli-computing/blob/master/exercises/exercises.md) as a single file, along with a separate [solutions](https://github.com/learnbyexample/cli-computing/blob/master/exercises/exercise-solutions.md) file. If you are not familiar with `git` command, click the **Code** button on the webpage to get the files.
-   See the [Setup](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/introduction-setup.html#setup) section for instructions to create a working environment for following along the contents presented in this book.

## [Acknowledgements](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#acknowledgements)

-   [GNU Manuals](https://www.gnu.org/manual/manual.html) — documentation for command line tools and the `bash` shell
-   [stackoverflow](https://stackoverflow.com/) and [unix.stackexchange](https://unix.stackexchange.com/) — for getting answers on pertinent questions related to CLI tools
-   [tex.stackexchange](https://tex.stackexchange.com/) — for help on [pandoc](https://github.com/jgm/pandoc/) and `tex` related questions
-   [/r/commandline/](https://old.reddit.com/r/commandline), [/r/linux4noobs/](https://old.reddit.com/r/linux4noobs/), [/r/linuxquestions/](https://old.reddit.com/r/linuxquestions/) and [/r/linux/](https://old.reddit.com/r/linux/) — helpful forums
-   [canva](https://www.canva.com/) — cover image
-   [Warning](https://commons.wikimedia.org/wiki/File:Warning_icon.svg) and [Info](https://commons.wikimedia.org/wiki/File:Info_icon_002.svg) icons by [Amada44](https://commons.wikimedia.org/wiki/User:Amada44) under public domain
-   [carbon](https://carbon.now.sh/) — creating terminal screenshots with highlighted text
-   [oxipng](https://github.com/shssoichiro/oxipng), [pngquant](https://pngquant.org/) and [svgcleaner](https://github.com/RazrFalcon/svgcleaner) — optimizing images
-   [Inkscape](https://inkscape.org/) — favicon
-   [mdBook](https://github.com/rust-lang/mdBook) — for web version of the book that you are currently reading
    -   [mdBook-pagetoc](https://github.com/JorelAli/mdBook-pagetoc) — for adding table of contents for each page
    -   [minify-html](https://github.com/wilsonzlin/minify-html) — for minifying html files

## [Feedback and Errata](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#feedback-and-errata)

I would highly appreciate if you'd let me know how you felt about this book. It could be anything from a simple thank you, pointing out a typo, mistakes in code snippets, which aspects of the book worked for you (or didn't!) and so on. Reader feedback is essential and especially so for self-published authors.

You can reach me via:

-   Issue Manager: [https://github.com/learnbyexample/cli-computing/issues](https://github.com/learnbyexample/cli-computing/issues)
-   E-mail: learnbyexample.net@gmail.com
-   Twitter: [https://twitter.com/learn\_byexample](https://twitter.com/learn_byexample)

## [Author info](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#author-info)

Sundeep Agarwal is a lazy being who prefers to work just enough to support his modest lifestyle. He accumulated vast wealth working as a Design Engineer at Analog Devices and retired from the corporate world at the ripe age of twenty-eight. Unfortunately, he squandered his savings within a few years and had to scramble trying to earn a living. Against all odds, selling programming ebooks saved his lazy self from having to look for a job again. He can now afford all the fantasy ebooks he wants to read and spends unhealthy amount of time browsing the internet.

When the creative muse strikes, he can be found working on yet another programming ebook (which invariably ends up having at least one example with regular expressions). Researching materials for his ebooks and everyday social media usage drowned his bookmarks, so he maintains curated resource lists for sanity sake. He is thankful for free learning resources and open source tools. His own contributions can be found at [https://github.com/learnbyexample](https://github.com/learnbyexample).

**List of books:** [https://learnbyexample.github.io/books/](https://learnbyexample.github.io/books/)

## [License](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#license)

This work is licensed under a [Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License](https://creativecommons.org/licenses/by-nc-sa/4.0/)

Code snippets are available under [MIT License](https://github.com/learnbyexample/cli-computing/blob/master/LICENSE)

Resources mentioned in the Acknowledgements section above are available under original licenses.

## [Book version](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/_generated_background_page.html#book-version)

1.0

See [Version\_changes.md](https://github.com/learnbyexample/cli-computing/blob/master/Version_changes.md) to track changes across book versions.

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/buy.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/introduction-setup.html "Next chapter")

[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/buy.html "Previous chapter")[](chrome-extension://pcmpcfapbekmbjjkdalcgopdkipoggdi/introduction-setup.html "Next chapter")
