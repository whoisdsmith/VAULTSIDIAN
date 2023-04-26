# Grep Regex: A Complete Guide 

---

Introduction

The **`grep`** command (short for **G**lobal **R**egular **E**xpressions **P**rint) is a powerful text processing tool for searching through files and directories.

When **`grep`** is combined with **regex** (**reg**ular **ex**pressions), advanced searching and output filtering become simple. System administrators, developers, and regular users benefit from mastering regex with the **`grep`** command.

**This guide teaches you how to `grep` with regex through examples.**

![grep regex a complete guide](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-regex-a-complete-guide.png)

Prerequisites

-   Access to the terminal/command line.
-   A [text file](https://phoenixnap.com/kb/how-to-create-a-file-in-linux) to search through. The examples use the [.bashrc](https://phoenixnap.com/kb/bashrc) file.
-   Basic [grep command](https://phoenixnap.com/kb/grep-command-linux-unix-examples) usage.

## Grep Regular Expression

The syntax for the **`grep`** command includes regular expressions in the following format:

```
grep [regex] [file]
```

Regular expressions are simple statements that help filter data and files. [Many Linux commands](https://phoenixnap.com/kb/linux-commands), such as the [awk command](https://phoenixnap.com/kb/awk-command-in-linux) or the [sed command](https://phoenixnap.com/kb/linux-sed), also use regular expressions to find and manipulate information.

Two general character types make up a regex statement:

-   **Literals**, which are standard text characters.
-   **Special** characters or **metacharacters** have special meaning unless escaped with a backslash (**`\`**).

**Note:** Encase regex expressions in single quotes and escape characters to avoid shell interpretation.

The **`grep`** command offers three regex syntax options:

1\. Basic Regular Expression (**BRE**)

2\. Extended Regular Expressions (**ERE**)

3\. Pearl Compatible Regular Expressions (**PCRE**)

By default, **`grep`** uses the **BRE** syntax.

## Grep Regex Example

Run the following command to test how grep regex works:

```
grep if .bashrc
```

![grep if .bashrc regex example terminal](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-if-.bashrc-regex-example-terminal.png)

The regex searches for the character string. The result shows all instances where the letter **`i`** appears followed by an **`f`** in the *.bashrc* file. Therefore, the output highlights the following results:

-   **if**
-   el**if**
-   not**if**y
-   ident**if**ying

The command returns only those lines where there is a match.

## How to Use Regex With Grep

Regex offers many possibilities to refine searches with **`grep`**. Below are some common examples explaining the basic syntax and logic. Combine matches to create complex regex statements.

### Literal Matches

Literal matches do an exact match for the specified character string. The previous example expression for **`if`** demonstrates a literal match.

The search is case-sensitive. The following command returns different results from the previous example:

```
grep If .bashrc
```

![grep case sensitive regex terminal](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-case-sensitive-regex-terminal.png)

**Note:** Add the `**-i**` or `**--ignore-case**` option to match all possible case combinations.

To search for multiple words, add quotation marks:

```
grep "if the" .bashrc
```

![grep if the .bashrc terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-if-the-.bashrc-terminal-output.png)

Omitting quotation marks treats the second word as a file or location.

### Anchor Matches

Anchor matches specify the line location in the search. There are two anchor types:

-   The caret sign (**`^`**) searches for match lines starting with the provided expression.
-   The dollar sign (**`$`**) searches for match lines ending with the provided literal.

For example, to match lines starting with the word **`alias`** in the *.bashrc* file, use:

```
grep ^alias .bashrc
```

![grep alias beginning regex terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-alias-beginning-regex-terminal-output.png)

The search does not display lines with tabs or spaces before the word.

To match lines ending with the word **`then`** in the *.bashrc* file, run:

```
grep then$ .bashrc
```

![grep then$ regex terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-then-regex-terminal-output.png)

Use both anchors to create a regex statement that searches for a single word or statement in a line:

```
grep ^esac$ .bashrc
```

![grep esac single line terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-esac-single-line-terminal-output.png)

Use only anchors to find empty lines in a file. Add the **`-n`** option to [show line numbers](https://phoenixnap.com/kb/vim-show-line-numbers) in the output:

```
grep -n ^$ .bashrc
```

![grep empty lines terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-empty-lines-terminal-output.png)

Without the **`-n`** option, the output is blank.

### Match Any Character

The period (**`.`**) regex metacharacter matches any character in place of the sign. For example:

```
grep r.o .bashrc
```

![grep any character match terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-any-character-match-terminal-output.png)

The output shows all instances of the letter **`r`**, followed by any character, followed by **`o`**. The period can be any character, such as a letter, number, sign, or space.

Add multiple periods to indicate multiple character placeholders:

```
grep r..t .bashrc
```

![grep multi character match terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-multi-character-match-terminal-output.png)

Combine with anchor matching to create a complex regex statement. For example:

```
grep ..t$ .bashrc
```

![grep multi character end match terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-multi-character-end-match-terminal-output.png)

The statement finds all lines with any two characters followed by the letter **`t`** at the end.

### Bracket Expressions

Bracket expressions allow matching multiple characters or a character range at a position. For example, to match all lines that contain **`and`** or **`end`** in the *.bashrc* file, use the following pattern:

```
grep [ae]nd .bashrc
```

![grep bracket end or and pattern terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-bracket-end-or-and-pattern-terminal-output.png)

Bracket expressions allow excluding characters by adding the caret (**`^`**) sign. For example, to match everything except for **`and`** or **`end`**, use:

```
grep [^ae]nd .bashrc
```

![grep exclude bracket expression terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-exclude-bracket-expression-terminal-output.png)

Use bracket expressions to specify a character range by adding a hyphen (**`-`**) between the first and final letter. For example, search for all instances of capital letters:

```
grep [A-Z] .bashrc
```

![grep uppercase letters terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-uppercase-letters-terminal-output.png)

Combine bracket expressions with anchor matching to find all words starting with capital letters:

```
grep ^[A-Z] .bashrc
```

![grep line beginning capital terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-line-beginning-capital-terminal-output.png)

Bracket expressions allow multiple ranges. For example, match all non-letter characters with:

```
grep [^a-zA-Z] .bashrc
```

![grep characters terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-characters-terminal-output.png)

The output highlights numbers and characters, ignoring all letters.

### Character Classes

Grep offers standard character classes as predefined functions to simplify bracket expressions. Below is a table that outlines some classes and the bracket expression equivalent.

| Syntax | Description | Equivalent |
| --- | --- | --- |
| **`[[:alnum:]]`** | All letters and numbers. | **`"[0-9a-zA-Z]"`** |
| **`[[:alpha:]]`** | All letters. | **`"[a-zA-Z]"`** |
| **`[[:blank:]]`** | Spaces and tabs. | **`[CTRL+V<TAB> ]`** |
| **`[[:digit:]]`** | Digits 0 to 9. | **`[0-9]`** |
| **`[[:lower:]]`** | Lowercase letters. | **`[a-z]`** |
| **`[[:punct:]]`** | Punctuation and other characters. | **`"[^a-zA-Z0-9]"`** |
| **`[[:upper:]]`** | Uppercase letters. | **`[A-Z]`** |
| **`[[:xdigit:]]`** | Hexadecimal digits. | **`"[0-9a-fA-F]"`** |

The complete list of grep character classes is in the [grep manual](https://www.gnu.org/software/grep/manual/grep.html#Character-Classes-and-Bracket-Expressions).

### Quantifiers

Quantifiers are metacharacters that specify the number of appearances. The following table shows each grep quantifier syntax with a short description.

| Syntax | Description |
| --- | --- |
| **`*`** | Zero or more matches. |
| **`?`** | Zero or one match. |
| **`+`** | One or more matches. |
| **`{n}`** | **`n`** matches. |
| **`{n,}`** | **`n`** or more matches. |
| **`{,m}`** | Up to **`m`** matches. |
| **`{n,m}`** | From **`n`** up to **`m`** matches. |

The **`*`** sign matches a pattern zero or more times. To demonstrate, run the following command:

```
grep m*and .bashrc
```

![grep asterisk terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-asterisk-terminal-output.png)

In this case, the **`*`** sign matches the letter **`m`** zero or more times. Therefore "**`and`**, **`mand`**, **`mmand`**" are all matches. The letter **`m`** repeats any number of times when followed by the **`*`** sign.

To match zero or exactly one match, use the **`?`** sign. Encase the statement in single quotes and escape the character to avoid interpretation. For example:

```
grep 'm\?and' .bashrc
```

![grep question mark terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-question-mark-terminal-output.png)

Alternatively, use extended regular expressions to avoid escaping:

```
grep -E 'm?and' .bashrc
```

![grep extended regex terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-extended-regex-terminal-output.png)

The output highlights all instances of **`and`** or **`mand`**.

Use range quantifiers to specify an exact number of repetitions. For example, search for strings with two vowels:

```
grep '[aeiouAEIOU]\{2\}' .bashrc
```

```
grep -E '[aeiouAEIOU]{2}' .bashrc
```

![grep limit 2 terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-limit-2-terminal-output.png)

The output highlights all words with two vowels.

### Alternation

Alternation allows for defining alternative matches. Encase the alternative strings in single quotes and separate each with an escaped pipe character (**`\|`**).

For example, to search for the words **`bash`** or **`alias`** in the *.bashrc* file, use:

```
grep 'bash\|alias' .bashrc
```

![grep bash or alias terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-bash-or-alias-terminal-output.png)

Alternatively, use extended regex and omit the escape character:

```
grep -E 'bash|alias' .bashrc
```

The output highlights both string instances in the file.

### Grouping

Regular expressions allow grouping patterns into one item. Place the group in escaped parenthesis for regular regex, or use extended.

For example, search for the string **`bashrc`** and make the **`rc`** characters optional:

```
grep 'bash\(rc\)\?' .bashrc
```

```
grep -E 'bash(rc)?' .bashrc
```

![grep regex grouping terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-regex-grouping-terminal-output.png)

The output highlights all instances of **`bashrc`**. Since **`rc`** is optional, the command also matches the word **`bash`**.

### Special Backslash Expressions

The grep command offers a few unique backslash expressions for advanced word boundary matching. Below is a table with short examples for each expression type.

| Syntax | Example | Matches  
(Bold text represents matches) |
| --- | --- | --- |
| **`\b`** | '\\band\\b' | **and**  
"**and**"  
\\**and**\\  
<space>**and**  
<tab>**and** |
| **`\B`** | '\\Band' | \_**and**  
\_**and**\_  
s**and**  
h**and**y |
| **`\<`** | '\\<and' | **and**  
"**and**"  
**and**y  
**and**\_  
**<space>and**  
**<tab>and** |
| **`\>`** | 'and\\>' | **and**  
**"and"**  
s**and**  
\_**and**  
<space>**and**  
<tab>**and** |
| **`\w`** | '\\wand' | **\_and**  
**\_and**\_  
**hand**y  
**sand** |
| **`\W`** | '\\Wand' | **"and**"  
**/and**/ |
| **`\s`** | '\\sand' | **<space>and  
<tab>and** |
| **`\S`** | '\\Sand' | **\_and**  
**"and**"  
**sand**  
**hand**y  
**\_and**\_  
**/and**/ |

For example, use **`\b`** boundaries to locate a word that is not a part of another word:

```
grep '\bse[et]\b' .bashrc
```

![grep boundaries special backslash terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-boundaries-special-backslash-terminal-output.png)

The expression locates words **`see`** and **`set`**. The boundary ensures word isolation.

### Escaping Meta-Characters

Escaping meta-characters treats special characters as literals. For example, to search for a period (.) at the end of a line, escape the meta-character:

```
grep '\.$' .bashrc
```

![grep special character matching terminal output](https://phoenixnap.com/kb/wp-content/uploads/2022/04/grep-special-character-matching-terminal-output.png)

Not allowing character interpretation helps when searching through source code or configuration files.

Conclusion

After working through the examples in this tutorial, you've mastered grep regex statements. Searching through files and directories with grep regex helps refine the search output to your specific use case.

Combine the basic rules and principles to yield complex expressions.
