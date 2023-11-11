# Grep Cheatsheet

---

The **grep** utility searches any given input files, selecting lines that match one or more patterns. By default, a pattern matches an input line if the regular expression (RE) in the pattern matches the input line without its trailing new line. An empty expression matches every line. Each input line that matches at least one of the patterns are written to the standard output.

**grep** is used for simple patterns and basic regular expressions (BREs). Below are the frequent use cases which will be handy for developers in their day to day activity.

## Index

-   [Case insensitive Search](https://vishnuch.tech/grep-cheatsheet#case-insensitive-search)
-   [Get Context](https://vishnuch.tech/grep-cheatsheet#get-context)
-   [Invert Match](https://vishnuch.tech/grep-cheatsheet#invert-match)
-   [Show Filenames](https://vishnuch.tech/grep-cheatsheet#show-filenames)
-   [Recursive Search](https://vishnuch.tech/grep-cheatsheet#recursive-search)
-   [Print Matching Part](https://vishnuch.tech/grep-cheatsheet#print-matching-part)
-   [Regular Expressions](https://vishnuch.tech/grep-cheatsheet#regular-expressions)
-   [Search Binaries](https://vishnuch.tech/grep-cheatsheet#search-binaries)

---

# Case Insensitive Search

**grep -i** : Output of both commands below will be same as **\-i** option does the case insensitive search.

```
grep -i hello file.txt
```

```
grep -i HELLO file.txt
```

# Get Context

To get the context of your search use the below commands.

**grep -A** :

```
grep -A 3 hello file.txt
```

This will show 3 lines of context after your match i.e *"hello"* word in this case.

**grep -B** :

```
grep -B 3 hello file.txt
```

This will show 3 lines of context before your match i.e *"hello"* word in this case.

**grep -C** :

```
grep -C 3 hello file.txt
```

This will show 3 lines of context before and after your match i.e *"hello"* word in this case.

# Invert Match

**grep -v** : Find all lines that don't match the given pattern.

```
grep -v hello file.txt
```

# Show Filenames

**grep -l** : Show only the filenames of the files that matched

```
grep -l hello *.txt
```

Above command lists all *.txt* files which has *"hello"* word in the current directory.

# Recursive Search

**grep -r** : Search all the files in a directory

```
grep -r hello */*.txt
```

Above command lists all *.txt* files inside nested directory which has *"hello"* word in it.

# Print Matching Part

```
grep -o hello file.txt
```

Above command prints only matching part of the line (not the complete line).

# Regular Expressions

**grep -E** : This option is used for matching Regular Expressions.

```
grep -E 'hel*' file.txt
```

Above command searches for all the lines which have words starting with **hel**.

```
grep -E 'hel*|wo*' file.txt
```

Above command searches for all the lines which have words starting with **hel OR wo**

# Search Binaries

**grep -a** : Treat binary data like its text instead of ignoring it.

Treat all files as ASCII text. Normally grep will simply print \`\`Binary file … matches'' if files contain binary characters. Use of this option forces **grep** to output lines matching the specified pattern.

```
grep -a <pattern> <binary file>
```

---

# Thank You for Reading

## If You like what You Read and want to See More about System Design, Microservices and other Technology-related stuff… You Can Follow Me on [Twitter here](https://twitter.com/vishnuchi)

[![Buy Me A Coffee](https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png)](https://www.buymeacoffee.com/vishnuchi)
