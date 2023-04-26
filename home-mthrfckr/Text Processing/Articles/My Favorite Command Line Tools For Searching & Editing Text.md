# My Favorite Command Line Tools for Searching & Editing Text

---

I spend more time working with text than anything else. The multi-monitor, high-resolution graphics revolution hasn’t brought me graphics, just dozens of windows full of text. If you’re a software developer, chances are you are swimming in text too. Source code, documentation, configuration files, templates, logs–they are all searchable text. For special purpose tasks, like searching Java classes, I rely on my IDE, but for many things I run a command in a terminal.

In this post I’ll show you the most powerful command line tools I’ve found for searching and editing text.

## Regex: Grep, Ack, & Silver Searcher

The 1973 Unix search command, grep, is still a popular and powerful tool for searching text. It uses regular expressions (also called regex) to find lines that match a pattern. Once you get good with grep, that experience will carry over to many other tools and text editors. This simple command searches all the files in the current directory:

```
grep -r 'PATTERN' .

```

Grep is starting to show its age, however. Most implementations have not been updated with modern [Perl-like regular expressions](http://perldoc.perl.org/perlre.html). Grep’s recursive file search is also difficult to control and often searches files, e.g. binary files, that aren’t interesting. [Ack](http://beyondgrep.com/) solves those two problems and adds more attractive output. It’s an even simpler command than grep:

```
ack 'PATTERN'

```

[Silver Searcher](https://github.com/ggreer/the_silver_searcher) is a very fast Ack clone. It can be more difficult to install, but the speed-up is surprisingly nice–I never thought Ack was slow until I tried Silver Searcher.

```
ag 'PATTERN'

```

All three commands support a few options I use all the time:

- `-i` ignore case
- `-w` match whole words only
- `-C4` show 4 lines on boths sides of the match
- `-A4` show 4 lines after the match
- `-B4` show 4 lines before the match
- `-l` only show the filenames containing a match
- `-v` invert the match–show lines not matching

## Perl & Ruby

Occasionally, a regex search doesn’t work well because the search is too complex or requires more than simple matching. Awk and Perl are both useful for these searches. Here’s an example of Perl searching text for numbers greater than 100:

```
perl -n -e '/(\d{3,})/ && $1 > 100 && print' *

```

I’ll show Perl for editing files later; I find more uses for it than Awk. If you’d rather not touch Perl even for command line stuff, similar searches can be performed with Ruby:

```
ruby -n -e 'puts $_ if ($_ =~ /(\d{3,})/ && $1.to_i > 100)' *

```

# Finding Changes In Text

Often when I’m searching text, I’m not looking at the text—I’m looking at the changes. That requires history. The original Unix diff command figures out changes by comparing an old file and new file. Unlike grep, I rarely use diff because I rarely have an old copy of a file—version control has replaced all the manual backups that I used to do. Learning diff is still useful though, because it introduced the unified output format that is still popular today:

```
diff -r -u OLD-DIRECTORY NEW-DIRECTORY

```

The diff command that I normally use is the git diff subcommand. Most often I use it to look at working copy changes:

```
git diff .

```

Both diff commands support options I use all the time:

- `-w` ignore whitespace changes
- `-U4` show 4 lines of context on both sides of a change

Searching the output of diff sounds kind of bizarre, but it’s useful because diff can generate a lot of output. I often just search the diff output in my terminal (command-K, run diff, command-F to search), but piping diff into grep works too:

```
git diff -U10 . | grep -C10 'PATTERN'

```

# Finding Files

Our file organization systems haven’t changed much, and the original Unix find command is still really useful. It will find all files with a given name or attribute in a directory:

```
find . -name '*.java'

# files modified less than an hour ago
find . -type f -mtime -1h

# Java files modified less than an hour ago
find . -name '*.java' -mtime -1h

```

It simply displays the list of matching files that we will see and is incredibly useful for controlling other tools.

Both Ack and Silver Searcher support the “`-l`” option to only show the file names containing match, instead of the matching text. This also works well with the file type options of both commands.

```
ack -l 'PATTERN'

ag -l 'PATTERN'

# files named either *.html or *.htm
ag --html -l

# files named *.java and containing the enum keyword
ag --java -l -w 'enum'

```

Once you have a list of files that you want to work on, you can use xargs to run another COMMAND on every file:

```
find . -name 'FILE' -print0 | xargs -0 COMMAND

# display the files I changed today that contain the word foo
find . -type f -mtime -8h -print0 | xargs -0 grep -l -w foo

```

The “`-print0`” and “`-0`” options ensure that files with special characters (mainly spaces) work properly. I’ve gotten in the habit of avoiding command line backticks and “`$(find . -name 'FILE')`” because those don’t handle files with spaces correctly.

Ack and Silver Searcher also support safe handling of files with spaces:

```
ack -l --print0 'PATTERN' | xargs -0 COMMAND

ag -l -0 'PATTERN' | xargs -0 COMMAND

```

# Changing Text with Batch Edits

Software is usually well-factored and easy to change by hand—some people get by with Notepad after all. Eventually though we all run into a big tedious change. Naming convention changes in particular can be impossible for an IDE and mind-numbing for a human. Learning how to write editor macros can help; learning a batch editor can help even more. Sed and Awk are the classic Unix batch editors, but in my experience Perl has more powerful one-liners: its reputation as a swiss army chainsaw is well deserved.

Perl normally batch edits a file one line at a time. This regex search and replace can’t cross line boundaries or use multi-line context:

```
perl -p -i -e 's/PATTERN/REPLACEMENT/g' FILES ...

```

The option “`-0777`” forces Perl to read entire files into memory so multi-line regex matches work. Perl’s regex implementation is actually more powerful than traditional regular expressions, so you can do things like recursively match text or perform computations on matches.

```
perl -0777 -p -i -e 's/PATTERN/REPLACEMENT/mg' FILES ...

```

Here’s an example that adds a correctly indented `@Timed` annotation to any method that already has a `@UnitOfWork` annotation, but only if the `@Timed` annotation isn’t already there:

```
perl -0777 -p -i \
  -e 's/(^(\s*)\@UnitOfWork.*\n)(?!\s*\@Timed)/\1\2\@Timed\n/mg' \
  *.java

```

If you want to make that change to every Java file in a directory tree, Perl combines well with find:

```
find . -name '*.java' -print0 | xargs -0 \
  perl -0777 -p -i \
    -e 's/(^(\s*)\@UnitOfWork.*\n)(?!\s*\@Timed)/\1\2\@Timed\n/mg'

```

# Making Changes Quickly and Safely

The Perl commands for editing multiple files, especially when combined with a find command, can make huge changes very quickly. When you make a mistake, that mistake can easily wipe out your entire project. To protect yourself against that, you absolutely must use version control.

If you aren’t already working under version control (why not?!) or aren’t using git, create a temporary git repo to easily undo bad changes:

```
git init
git add .
git commit -m originals

```

Here’s the approach I use when making batch edits. It’s fast partly because it’s so safe I don’t mind experimenting with the text trying to get the changes I want:

1. Run a batch edit command
2. Examine changes with “`git diff .`”
3. Undo bad changes with “`git checkout -- .`”
4. If more work is needed “`git add .`” and go back to step 1
5. Otherwise when the changes are complete, commit or delete the temporary git repo
