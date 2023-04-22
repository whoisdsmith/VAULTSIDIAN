# Text Processing From the Command Line

---

*( List of commands that can make you productive in pre-processing text file.)*

![](https://miro.medium.com/v2/resize:fit:700/1*mDFiewb7C0vXSWvbZ6VodQ.jpeg)

Every time you want to manipulate your text file, you don’t need to spin up a programming language. The common use cases are while reading a log file directly from a file or input stream; you might want to filter the results, sort them, replace words or whatever your use case be there are few commands that will definitely help you in long run.

Let’s take a look at some of my favorite ones.

**Cat:**

Reading the whole files into the shell. Cat can work with single or multiple files.

```
cat file1.txt file2.txt
```

**Head and Tail:**

Get data from the top or bottom of your file or input stream.

```
head -n 5 logs.logtail -n 6 logs.logtail -f logs.log // -f means follow; while streaming see what is being written; used for reading logs
```

**Word Count:**

Count words, lines or characters with “wc” command.

```
wc -l file.log // Use -c & -w for characters and words -l means line
```

**Exercise:**

Verify that “**tail**” command prints exactly 10 lines using “**wc**” command:

```
tail logs.log | wc -l
```

![](https://miro.medium.com/v2/resize:fit:308/1*ym7pY9lhpsDFoUYpX6A3rQ.png)

**Grep:**

Filter lines that match the pattern

```
grep rabin data.csv // Find word "rabin" and print linesgrep rabin data.csv | grep paudel // Find both rabin and paudelgrep -V donotfindthisword file.txt // Inverse matchinggrep -c countwords file.txt // Cound word "countwords"
```

**Exercise:**

Find the word “**import**” in your python project;

```
grep -r import ~/MyProject // -r means recursively in all files
```

**Cut:**

Extract portion of a file.

Args: -d is the delimiter for eg. comma or tab character in CSV files; -f is the column.

```
head file.csv | cut -d , -f 1,2 // extract first n second col
```

**Paste:**

Merge two different files into one multi col file

```
paste file1.txt file2.txt -d, // Combine two files with , delimeter
```

**Sorting:**

```
sort file.txt //sort text in filesort -r file.txt //sort reverse order
```

**Unique:**

Uniq command compares the two adjacent lines and filters unique values.

```
uniq file.txt
```

The above command does not remove all duplicates. To perform actual unique you need to sort data first.

```
sort file.txt | uniq -c // -c for printing no. of occurances
```

**Awk:**

Used in multi-column text files. Using awk you can do a lot more. It is kind of a programming language on its own.

```
cat multi-columns | awk '{ print $1,$2 }' // print col 1 & 2.
```

**Tr:**

Translate text from one format to another.

```
echo "converts a to A" | tr a Aecho "converts space to comma" | tr '[:space:]' ','echo "lower to upper" | tr '[:lower:]' '[:upper:]'
```

**Fold**:

Fold text file so that it will be easier to view those files

```
cat readme.md | fold -w 19 // fold from 19th char of each line
```

**Sed:**

Substitute text:

![](https://miro.medium.com/v2/resize:fit:516/1*FE5spJFn3zuTnklCN4hFBg.png)

These commands just scratch the surface of what you can do with the shell itself. I hope you liked the article.

I also write about other topics like recommendation systems, natural language processing and many more. If you are also exploring these topics, don’t forget to visit my profile and see if there are any posts that interest you.

If you like my article, don’t forget to [*follow me on Medium*](https://medium.com/@rabinpoudyal1995), or [*connect me on Linkedin*](https://www.linkedin.com/in/rabin-poudyal/), or [*follow me on twitter*](https://twitter.com/poudyal_rabin).
