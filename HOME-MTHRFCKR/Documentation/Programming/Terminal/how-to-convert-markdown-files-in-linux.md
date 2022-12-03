This article will cover a guide on various command line applications that can be used to convert “Markdown” files to different file formats. Markdown is a markup language that provides simplified syntax and shorthands that can be used to write rich text content with formatting. Markdown is most commonly used to write stylized content that can be later exported to HTML documents. Many tools and applications exist that can convert a “.md” Markdown document to a HTML or PDF file.

## Markdown

Markdown is a free and open source command line application that can convert Markdown files to HTML files. It is a command line utility developed by creators of the Markdown syntax itself. To install it in Ubuntu, use the command below:

$ sudo apt install markdown

You can install Markdown command line tool in other Linux distributions from the package manager. You can also compile it from its source code available [here](https://daringfireball.net/projects/markdown/).

To convert a “.md” file to “.html” file, run a command in the following format:

$ markdown file.md \> file.html

The first argument is the input “.md” file that you want to convert to a “.html” file. The second argument is the name of the “.html” output file. Replace these names as needed.

For more information on the “markdown” command, run the command below:

## Pandoc

Pandoc is a free and open source document conversion utility that can convert documents written in markup languages into a number of different file formats. It supports conversion into numerous file formats, more than any other command line tool that is capable of doing document conversion. Besides converting to “.html” format, it can convert files to “.odt”, “.docx”, “.pdf”, and “.csv” formats as well. It can even convert Markdown files to “.epub” file format allowing you to read content on ereaders.

To install Pandoc in Ubuntu, use the command below:

$ sudo apt install pandoc

You can install Pandoc in other Linux distributions from the package manager. More packages and installation instructions are available [here](https://pandoc.org/installing.html#linux).

To convert a “.md” file to a “.html” file using Pandoc, run a command in the following format:

$ pandoc file.md \-f markdown \-t html \-s \-o file.html

Replace “file.md” with the name of the input file. The “-f” switch is used to specify the format of the input file. The “-t” switch can be used to specify the format of the output file. The “-s” is required to properly construct the output file. The “-o” switch can be used to provide a name for the output file.

To convert a “.md” file to a “.docx” file, run a command in the following format:

$ pandoc file.md \-f markdown \-t docx \-s \-o file.docx

For more information on Pandoc, run the following two commands:

$ pandoc \--help  
$ man pandoc

## Kramdown

Kramdown is a free and open source Markdown converter written in Ruby programming language. It is mainly designed to convert Markdown files to HTML files. However, you can use it to convert Markdown files to kramdown, LaTeX and PDF file formats as well.

You can install Kramdown in Ubuntu using the command specified below:

$ sudo apt install kramdown

You can install Kramdown in other Linux distributions from the package manager. Further installation instructions are available [here](https://kramdown.gettalong.org/installation.html).

To convert a “.md” file to a “.html” file using Kramdown, run a command in the following format:

$ kramdown file.md \-i markdown \-o html \> file.html

Replace “file.md” to change input file name. The “-i” switch takes a name for input file format while the “-o” switch can be used to specify the format for the converted output. Replace “file.html” with your desired name for the output file.

For more information on Kramdown, run the following two commands:

$ kramdown \--help  
$ man kramdown

## Cmark

Cmark or CommonMark is a free and open source Markdown parser and converter written in C programming language. It claims to be much faster than other Markdown parsing apps available on the Web. It also provides a modified version of Markdown syntax, aimed to make it easier to write rich text content.

You can install Cmark in Ubuntu using the command specified below:

You can install Cmark in other Linux distributions from the package manager. Further installation instructions are available [here](https://github.com/commonmark/cmark#installing).

To convert a “.md” file to a “.html” file using Cmark, run a command in the following format:

$ cmark file.md \-t html \> file.html

Replace “file.md” to change input file name. The “-t” switch is used to specify the output file format. Replace “file.html” with your desired name for the output file. You can convert “.md” files to xml, html, commonmark, latex, and man (manpage) formats using Cmark.

For more information on Cmark, run the following two command:

$ man cmark  
$ cmark \--help

## Grip

Grip is a free and open source Markdown file renderer and previewer written in Python. It is mainly designed to preview GitHub compatible “README.md” files. But you can use it to convert other Markdown files to HTML file format as well.

You can install Grip in Ubuntu using the command specified below:

You can install Grip in other Linux distributions from the package manager. Further installation instructions are available [here](https://github.com/joeyespo/grip#installation).

To convert a “.md” file to a “.html” file using Grip, run a command in the following format:

$ grip file.md \--export file.html

Replace “file.md” to change input file name. Replace “file.html” with your desired name for the output file. Make sure that the output file name ends with “.html” extension to convert the file properly without errors.

For more information on Grip, run the following two commands:

## Conclusion

These are some of the best command line applications that can be used to convert Markdown files to a variety of useful file formats. These tools are especially useful for those users who write content using Markdown syntax but publish it in a different markup language or in a different file format.

### About the author

![](https://linuxhint.com/wp-content/uploads/2019/11/Cartoon-Man-Avatar-2-150x150.png)

I am a freelancer software developer and content writer who loves Linux, open source software and the free software community.