# Fun Working With Files Using Awk And Sed

## Fun Working with Files Using Awk and Sed

---

There are two awesome Linux commands providing a great flexibility in manipulating with text files: awk and sed. These commands sadly are not so popular and widely highlighted as another Linux commands. Let’s see what we can do with these commands.

### Awk

Print all line containing string

```
awk '/mtllib/' test.txt
```

Print line number for lines containing substring

```
awk '/mtllib/ {print NR, $1, $2}' test.txt
```

Print fifth line

```
awk 'NR==5 {print}' test.txt
```

Print number of lines in file

```
awk 'END {print NR}'
```

Interesting trick: compare output of two commands awk using command diff

```
awk '{print $3}' f1.txt | sort -u > out1awk '{print $2}' f2.txt | sort -u > out2diff out1 out2
```

### Sed

Print lines in range numbers in file

```
sed -n '3,6 p' test.txt
```

Replace substring in file:

```
sed -i 's|Old|New|' test.txt
```

Replace substring by regex (all occurrences of ‘2/<digit>’ replace with ‘2’)

```
sed -i 's|2/.|2|g' test.txt
```

Delete lines containing specific pattern

```
sed -i '/debian/d' file
```

Add text to the beginning of file

```
sed -i '1isome text' test.txt
```

Here we add text ‘some text’ in the first line of file test.txt.

That’s it. Enjoy work with files using awk and sed commands.
