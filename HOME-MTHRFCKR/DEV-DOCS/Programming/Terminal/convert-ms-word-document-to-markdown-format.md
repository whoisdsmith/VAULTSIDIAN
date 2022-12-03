There are many ways to convert MS Word documents to the markdown format (.md) file.

1.  Manual conversion
2.  Using Online Conversion Tool
3.  Using Pandoc

## Manual Conversion

You can convert the MS Word file (.docx or .doc) to markdown format easily. Markdown is an easy syntax that you can apply on a word file manually if it is not a long file. Learn the basic syntax of markdown from [here](https://www.markdownguide.org/basic-syntax).

1.  Open [Notepad++](https://notepad-plus-plus.org/) or any other editor that can save file in any format.
2.  Create a new blank file.
3.  Copy word file content to Notepad++ file.
4.  Apply the markdown format manually e.g., write # before h1 heading, ## for h2 heading, etc.
5.  Now, click on the Save toolbar or from File -> Save menu.
6.  In the Save As dialog, give a file name with `.md` extension e.g., `myarticle.md`.

[![](https://www.tutorialsteacher.com/Content/images/articles/productivity/notepad-markdown.png)](https://www.tutorialsteacher.com/Content/images/articles/productivity/notepad-markdown.png)

7.  Select All Types (\*.\*) from the Save as type dropdown and click on the Save button.

This will save the new file in markdown format with the .md extension.

There are many online websites such as [word2md.com](https://word2md.com/) that convert your MS Word to a markdown file.

## Pandoc

Pandoc is a universal document converter that converts one markup into another. It supports many formats such as HTML, MS Word, Wiki markup, slide show, data formats, etc.

Download and install Pandoc from [here](https://pandoc.org/installing.html).

After installing, open your command prompt or terminal, navigate to the folder where you have saved your MS Word file, and enter the following command.

C:\\pathToFile> pandoc myarticle.docx -o myarticle.md

As you can see, first, write `pandoc` to execute any pandoc command, and then write the file name of a file with extension which you want to convert to a markdown file. The `-o` stands for output file name and provide name of the file with extension to which it should be converted. So, the above command will convert `myarticle.docx` file to `myarticle.md` file in the same folder.

If your Word file contains some images, then use `--extract-media=DIR` flag to save the images to a specified folder. Use `./` for the current folder. The following command will create a `myarticle.md` file and save all the images included in a `myarticle.docx` file to the `images` folder in the current folder.

C:\\pathToFile> pandoc myarticle.docx -o myarticle.md --extract-media=./images/

Visit [Pandoc User's Guide](https://pandoc.org/MANUAL.html) for more information.

It is recommended to use Pandoc for safer and faster conversion from Word doc to markdown file.

___