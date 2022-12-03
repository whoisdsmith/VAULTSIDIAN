# Python Cheat Sheet by DaveChild - Download free from Cheatography - Cheatography.com: Cheat Sheets For Every Occasion



> ## Excerpt
> The Python cheat sheet is a one-page reference sheet for the Python programming language.




---
# Python Cheat Sheet by [DaveChild](http://www.cheatography.com/davechild/)





The Python cheat sheet is a one-page reference sheet for the Python programming language.





### Python sys Variables

argv

Command line args

builtin\_module\_names

Linked C modules

byteorder

Native byte order

check\_interval

Signal check frequency

exec\_prefix

Root directory

executable

Name of executable

exitfunc

Exit function name

modules

Loaded modules

path

Search path

platform

Current platform

stdin, stdout, stderr

File objects for I/O

version\_info

Python version info

winver

Version number

### Python sys.argv

sys.argv\[0\]

foo.py

sys.argv\[1\]

bar

sys.argv\[2\]

\-c

sys.argv\[3\]

qux

sys.argv\[4\]

\--h

sys.argv for the command:  
$ python foo.py bar -c qux --h

### Python os Variables

altsep

Alternative sep

curdir

Current dir string

defpath

Default search path

devnull

Path of null device

extsep

Extension separator

linesep

Line separator

name

Name of OS

pardir

Parent dir string

pathsep

Patch separator

sep

Path separator

Registered OS names: "posix", "nt",  
"mac", "os2", "ce", "java", "riscos"

### Python Class Special Methods

\_\_new\_\_(cls)

\_\_lt\_\_(self, other)

\_\_init\_\_(self, args)

\_\_le\_\_(self, other)

\_\_del\_\_(self)

\_\_gt\_\_(self, other)

\_\_repr\_\_(self)

\_\_ge\_\_(self, other)

\_\_str\_\_(self)

\_\_eq\_\_(self, other)

\_\_cmp\_\_(self, other)

\_\_ne\_\_(self, other)

\_\_index\_\_(self)

\_\_nonzero\_\_(self)

\_\_hash\_\_(self)

\_\_getattr\_\_(self, name)

\_\_getattribute\_\_(self, name)

\_\_setattr\_\_(self, name, attr)

\_\_delattr\_\_(self, name)

\_\_call\_\_(self, args, kwargs)

 

### Python List Methods

append(item)

pop(position)

count(item)

remove(item)

extend(list)

reverse()

index(item)

sort()

insert(position, item)

### Python String Methods

capitalize() \*

lstrip()

center(width)

partition(sep)

count(sub, start, end)

replace(old, new)

decode()

rfind(sub, start ,end)

encode()

rindex(sub, start, end)

endswith(sub)

rjust(width)

expandtabs()

rpartition(sep)

find(sub, start, end)

rsplit(sep)

index(sub, start, end)

rstrip()

isalnum() \*

split(sep)

isalpha() \*

splitlines()

isdigit() \*

startswith(sub)

islower() \*

strip()

isspace() \*

swapcase() \*

istitle() \*

title() \*

isupper() \*

translate(table)

join()

upper() \*

ljust(width)

zfill(width)

lower() \*

Methods marked \* are locale dependant for 8-bit strings.

### Python File Methods

close()

readlines(size)

flush()

seek(offset)

fileno()

tell()

isatty()

truncate(size)

next()

write(string)

read(size)

writelines(list)

readline(size)

### Python Indexes and Slices

len(a)

6

a\[0\]

0

a\[5\]

5

a\[-1\]

5

a\[-2\]

4

a\[1:\]

\[1,2,3,4,5\]

a\[:5\]

\[0,1,2,3,4\]

a\[:-2\]

\[0,1,2,3\]

a\[1:3\]

\[1,2\]

a\[1:-1\]

\[1,2,3,4\]

b=a\[:\]

Shallow copy of a

Indexes and Slices of a=\[0,1,2,3,4,5\]

 

### Python Datetime Methods

today()

fromordinal(ordinal)

now(timezoneinfo)

combine(date, time)

utcnow()

strptime(date, format)

fromtimestamp(timestamp)

utcfromtimestamp(timestamp)

### Python Time Methods

replace()

utcoffset()

isoformat()

dst()

\_\_str\_\_()

tzname()

strftime(format)

### Python Date Formatting

%a

Abbreviated weekday (Sun)

%A

Weekday (Sunday)

%b

Abbreviated month name (Jan)

%B

Month name (January)

%c

Date and time

%d

Day (leading zeros) (01 to 31)

%H

24 hour (leading zeros) (00 to 23)

%I

12 hour (leading zeros) (01 to 12)

%j

Day of year (001 to 366)

%m

Month (01 to 12)

%M

Minute (00 to 59)

%p

AM or PM

%S

Second (00 to 61⁴)

%U

Week number¹ (00 to 53)

%w

Weekday² (0 to 6)

%W

Week number³ (00 to 53)

%x

Date

%X

Time

%y

Year without century (00 to 99)

%Y

Year (2008)

%Z

Time zone (GMT)

%%

A literal "%" character (%)

¹ Sunday as start of week. All days in a new year preceding the first Sunday are considered to be in week 0.  
² 0 is Sunday, 6 is Saturday.  
³ Monday as start of week. All days in a new year preceding the first Monday are considered to be in week 0.  
⁴ This is not a mistake. Range takes account of leap and double-leap seconds.
