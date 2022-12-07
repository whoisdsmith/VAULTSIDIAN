- [Sphinx 3](http://sphinxsearch.com/docs/sphinx3.html#sphinx-3)
  - [Features overview](http://sphinxsearch.com/docs/sphinx3.html#features-overview)
  - [Features cheat sheet](http://sphinxsearch.com/docs/sphinx3.html#features-cheat-sheet)
  - [Getting started](http://sphinxsearch.com/docs/sphinx3.html#getting-started)
    - [Getting started on Linux (and MacOS)](http://sphinxsearch.com/docs/sphinx3.html#getting-started-on-linux-and-macos)
    - [Getting started on Windows](http://sphinxsearch.com/docs/sphinx3.html#getting-started-on-windows)
    - [Running queries via MySQL shell](http://sphinxsearch.com/docs/sphinx3.html#running-queries-via-mysql-shell)
    - [Writing your first config](http://sphinxsearch.com/docs/sphinx3.html#writing-your-first-config)
    - [Running queries from PHP, Python, etc](http://sphinxsearch.com/docs/sphinx3.html#running-queries-from-php-python-etc)
    - [Running queries via HTTP](http://sphinxsearch.com/docs/sphinx3.html#running-queries-via-http)
    - [Installing `indexer` SQL drivers on Linux](http://sphinxsearch.com/docs/sphinx3.html#installing-indexer-sql-drivers-on-linux)
  - [Main concepts](http://sphinxsearch.com/docs/sphinx3.html#main-concepts)
    - [Indexes](http://sphinxsearch.com/docs/sphinx3.html#indexes)
    - [Documents](http://sphinxsearch.com/docs/sphinx3.html#documents)
    - [Fields](http://sphinxsearch.com/docs/sphinx3.html#fields)
    - [Attributes](http://sphinxsearch.com/docs/sphinx3.html#attributes)
  - [Using DocStore](http://sphinxsearch.com/docs/sphinx3.html#using-docstore)
  - [Using attribute indexes](http://sphinxsearch.com/docs/sphinx3.html#using-attribute-indexes)
    - [Query optimizer, and index hints](http://sphinxsearch.com/docs/sphinx3.html#query-optimizer-and-index-hints)
  - [Using k-batches](http://sphinxsearch.com/docs/sphinx3.html#using-k-batches)
  - [Doing bulk data loads](http://sphinxsearch.com/docs/sphinx3.html#doing-bulk-data-loads)
  - [Using JSON](http://sphinxsearch.com/docs/sphinx3.html#using-json)
    - [JSON comparison quirks](http://sphinxsearch.com/docs/sphinx3.html#json-comparison-quirks)
  - [Using array attributes](http://sphinxsearch.com/docs/sphinx3.html#using-array-attributes)
  - [Using wordforms](http://sphinxsearch.com/docs/sphinx3.html#using-wordforms)
  - [Using UDFs](http://sphinxsearch.com/docs/sphinx3.html#using-udfs)
    - [UDFs overview](http://sphinxsearch.com/docs/sphinx3.html#udfs-overview)
    - [UDF programming introduction](http://sphinxsearch.com/docs/sphinx3.html#udf-programming-introduction)
    - [UDF argument and return types](http://sphinxsearch.com/docs/sphinx3.html#udf-argument-and-return-types)
    - [UDF call batching](http://sphinxsearch.com/docs/sphinx3.html#udf-call-batching)
    - [Using `FACTORS()` in UDFs](http://sphinxsearch.com/docs/sphinx3.html#using-factors-in-udfs)
    - [UDF calls sequences](http://sphinxsearch.com/docs/sphinx3.html#udf-calls-sequences)
  - [Indexing: CSV and TSV files](http://sphinxsearch.com/docs/sphinx3.html#indexing-csv-and-tsv-files)
  - [Indexing: special chars, blended tokens, and mixed codes](http://sphinxsearch.com/docs/sphinx3.html#indexing-special-chars-blended-tokens-and-mixed-codes)
    - [Blended tokens (with special characters)](http://sphinxsearch.com/docs/sphinx3.html#blended-tokens-with-special-characters)
    - [Mixed codes (with letters and digits)](http://sphinxsearch.com/docs/sphinx3.html#mixed-codes-with-letters-and-digits)
    - [Blending modes](http://sphinxsearch.com/docs/sphinx3.html#blending-modes)
    - [Searching vs blended tokens and mixed codes](http://sphinxsearch.com/docs/sphinx3.html#searching-vs-blended-tokens-and-mixed-codes)
  - [Searching: query syntax](http://sphinxsearch.com/docs/sphinx3.html#searching-query-syntax)
    - [Operators](http://sphinxsearch.com/docs/sphinx3.html#operators)
    - [Modifiers](http://sphinxsearch.com/docs/sphinx3.html#modifiers)
    - [Cheat sheet](http://sphinxsearch.com/docs/sphinx3.html#cheat-sheet)
    - [Keyword modifiers](http://sphinxsearch.com/docs/sphinx3.html#keyword-modifiers)
    - [Boolean operators (brackets, AND, OR, NOT)](http://sphinxsearch.com/docs/sphinx3.html#boolean-operators-brackets-and-or-not)
    - [Phrase operator](http://sphinxsearch.com/docs/sphinx3.html#phrase-operator)
    - [MAYBE operator](http://sphinxsearch.com/docs/sphinx3.html#maybe-operator)
    - [Term-OR operator](http://sphinxsearch.com/docs/sphinx3.html#term-or-operator)
    - [Field and position limit operator](http://sphinxsearch.com/docs/sphinx3.html#field-and-position-limit-operator)
    - [Proximity and NEAR operators](http://sphinxsearch.com/docs/sphinx3.html#proximity-and-near-operators)
    - [Quorum operator](http://sphinxsearch.com/docs/sphinx3.html#quorum-operator)
    - [Strict order operator (BEFORE)](http://sphinxsearch.com/docs/sphinx3.html#strict-order-operator-before)
    - [SENTENCE and PARAGRAPH operators](http://sphinxsearch.com/docs/sphinx3.html#sentence-and-paragraph-operators)
    - [ZONE and ZONESPAN operators](http://sphinxsearch.com/docs/sphinx3.html#zone-and-zonespan-operators)
  - [Searching: geosearches](http://sphinxsearch.com/docs/sphinx3.html#searching-geosearches)
  - [Searching: vector searches](http://sphinxsearch.com/docs/sphinx3.html#searching-vector-searches)
  - [Ranking: factors](http://sphinxsearch.com/docs/sphinx3.html#ranking-factors)
    - [Factor aggregation functions](http://sphinxsearch.com/docs/sphinx3.html#factor-aggregation-functions)
    - [Keyword flags](http://sphinxsearch.com/docs/sphinx3.html#keyword-flags)
    - [Query-level ranking factors](http://sphinxsearch.com/docs/sphinx3.html#query-level-ranking-factors)
    - [Document-level ranking factors](http://sphinxsearch.com/docs/sphinx3.html#document-level-ranking-factors)
    - [Field-level ranking factors](http://sphinxsearch.com/docs/sphinx3.html#field-level-ranking-factors)
  - [Ranking: builtin ranker formulas](http://sphinxsearch.com/docs/sphinx3.html#ranking-builtin-ranker-formulas)
  - [Ranking: IDF magics](http://sphinxsearch.com/docs/sphinx3.html#ranking-idf-magics)
    - [How Sphinx computes IDF](http://sphinxsearch.com/docs/sphinx3.html#how-sphinx-computes-idf)
  - [Ranking: picking fields with `rank_fields`](http://sphinxsearch.com/docs/sphinx3.html#ranking-picking-fields-with-rank_fields)
  - [Operations: “siege mode”, temporary global query limits](http://sphinxsearch.com/docs/sphinx3.html#siege-mode)
  - [SphinxQL reference](http://sphinxsearch.com/docs/sphinx3.html#sphinxql-reference)
    - [BULK UPDATE syntax](http://sphinxsearch.com/docs/sphinx3.html#bulk-update-syntax)
    - [KILL syntax](http://sphinxsearch.com/docs/sphinx3.html#kill-syntax)
    - [SELECT syntax](http://sphinxsearch.com/docs/sphinx3.html#select-syntax)
    - [SHOW INDEX AGENT STATUS syntax](http://sphinxsearch.com/docs/sphinx3.html#show-index-agent-status-syntax)
    - [SHOW VARIABLES syntax](http://sphinxsearch.com/docs/sphinx3.html#show-variables-syntax)
  - [Functions reference](http://sphinxsearch.com/docs/sphinx3.html#functions-reference)
    - [`DOT()` function](http://sphinxsearch.com/docs/sphinx3.html#dot-function)
    - [`FVEC()` function](http://sphinxsearch.com/docs/sphinx3.html#fvec-function)
    - [`PP()` function](http://sphinxsearch.com/docs/sphinx3.html#pp-function)
    - [Slice functions](http://sphinxsearch.com/docs/sphinx3.html#slice-functions)
    - [`STRPOS()` function](http://sphinxsearch.com/docs/sphinx3.html#strpos-function)
  - [Server variables reference](http://sphinxsearch.com/docs/sphinx3.html#server-variables-reference)
    - [`attrindex_thresh` variable](http://sphinxsearch.com/docs/sphinx3.html#attrindex_thresh-variable)
    - [`log_debug_filter` variable](http://sphinxsearch.com/docs/sphinx3.html#log_debug_filter-variable)
    - [`log_level` variable](http://sphinxsearch.com/docs/sphinx3.html#log_level-variable)
    - [`net_spin_msec` variable](http://sphinxsearch.com/docs/sphinx3.html#net_spin_msec-variable)
    - [`query_log_format` variable](http://sphinxsearch.com/docs/sphinx3.html#query_log_format-variable)
    - [`query_log_min_msec` variable](http://sphinxsearch.com/docs/sphinx3.html#query_log_min_msec-variable)
    - [`sql_fail_filter` variable](http://sphinxsearch.com/docs/sphinx3.html#sql_fail_filter-variable)
    - [`sql_log_file` variable](http://sphinxsearch.com/docs/sphinx3.html#sql_log_file-variable)
  - [Changes in 3.x](http://sphinxsearch.com/docs/sphinx3.html#changes-in-3.x)
    - [Version 3.3.1, 06 jul 2020](http://sphinxsearch.com/docs/sphinx3.html#version-3.3.1-06-jul-2020)
    - [Version 3.2.1, 31 jan 2020](http://sphinxsearch.com/docs/sphinx3.html#version-3.2.1-31-jan-2020)
    - [Version 3.1.1, 17 oct 2018](http://sphinxsearch.com/docs/sphinx3.html#version-3.1.1-17-oct-2018)
    - [Version 3.0.3, 30 mar 2018](http://sphinxsearch.com/docs/sphinx3.html#version-3.0.3-30-mar-2018)
    - [Version 3.0.2, 25 feb 2018](http://sphinxsearch.com/docs/sphinx3.html#version-3.0.2-25-feb-2018)
    - [Version 3.0.1, 18 dec 2017](http://sphinxsearch.com/docs/sphinx3.html#version-3.0.1-18-dec-2017)
  - [Changes since v.2.x](http://sphinxsearch.com/docs/sphinx3.html#changes-since-v.2.x)
  - [Copyrights](http://sphinxsearch.com/docs/sphinx3.html#copyrights)

Sphinx is a free, dual-licensed search server. Sphinx is written in C++, and focuses on query performance and search relevance.

The primary client API is currently SphinxQL, a dialect of SQL. Almost any MySQL connector should work. Additionally, basic HTTP/JSON API and native APIs for a number of languages (PHP, Python, Ruby, C, Java) are provided.

This document is an effort to build a better documentation for Sphinx v.3.x and up. Think of it as a book or a tutorial which you could actually _read_; think of the previous “reference manual” as of a “dictionary” where you look up specific syntax features. The two might (and should) eventually converge.

## Features overview

Top level picture, what does Sphinx offer?

- SQL, HTTP/JSON, and custom native SphinxAPI access APIs
- NRT (Near Real Time) and offline batch indexing
- Full-text and non-text (parameter) searching
- Relevance ranking, from basic formulas to ML models
- Federated results from multiple servers
- Decent performance

Other things that seem worth mentioning (this list is probably incomplete at all times, and definitely in random order):

- Morphology and text-processing tools
  - Fully flexible tokenization (see `charset_table` and `exceptions`)
  - Proper morphology (lemmatizer) for English, Russian, and German (see `morphology`)
  - Basic morphology (stemmer) for many other languages
  - User-specified wordforms, `core 2 duo => c2d`
- Native JSON support
- Geosearch support
- Fast expressions engine
- Query suggestions
- Snippets builder
- …

And, of course, there is always stuff that we know we currently lack!

- Index replication
- …

## Features cheat sheet

This section is supposed to provide a bit more detail on all the available features; to cover them more or less fully; and give you some further pointers into the specific reference sections (on the related config directives and SphinxQL statements).

- Full-text search queries, see `SELECT ... WHERE MATCH('this')` SphinxQL statement
  - Boolean matching operators (implicit AND, explicit OR, NOT, and brackets), as in `(one two) | (three !four)`
  - Boolean matching optimizations, see `OPTION boolean_simplify=1` in `SELECT` statement
  - Advanced text matching operators
    - Field restrictions, `@title hello world` or `@!title hello` or `@(title,body) any of the two` etc
    - In-field position restrictions, `@title[50] hello`
    - MAYBE operator for optional keyword matching, `cat MAYBE dog`
    - phrase matching, `"roses are red"`
    - quorum matching, `"pick any 3 keywords out of this entire set"/3`
    - proximity matching, `"within 10 positions all terms in yoda order"~10` or `hello NEAR/3 world NEAR/4 "my test"`
    - strict order matching, `(bag of words) << "exact phrase" << this|that`
    - sentence matching, `all SENTENCE words SENTENCE "in one sentence"`
    - paragraph matching, `"Bill Gates" PARAGRAPH "Steve Jobs"`
    - zone and zone-span matching, `ZONE:(h3,h4) in any of these title tags` and `ZONESPAN:(h2) only in a single instance`
  - Keyword modifiers (that can usually be used within operators)
    - exact (pre-morphology) form modifier, `raining =cats and =dogs`
    - field-start and field-end modifiers, `^hello world$`
    - IDF (ranking) boost, `boosted^1.234`
  - Substring and wildcard searches
    - see `min_prefix_len` and `min_infix_len` directives
    - use `th?se three keyword% wild*cards *verywher*` (`?` = 1 char exactly; `%` = 0 or 1 char; `*` = 0 or more chars)
- …

TODO: describe more, add links!

## Getting started

That should now be rather simple. No magic installation required! On any platform, the _sufficient_ thing to do is:

1. Get the binaries.
2. Run `searchd`
3. Create indexes.
4. Run queries.

See more details on that (running in config-less mode) just below.

Or alternatively, you can ETL your data offline, using the `indexer` tool:

1. Get the binaries.
2. Create `sphinx.conf`, with at least 1 `index` section.
3. Run `indexer --all` once, to initially create the indexes.
4. Run `searchd`
5. Run queries.
6. Run `indexer --all --rotate` regularly, to update the indexes.

Note that instead of inserting the data into indexes online, the `indexer` tool instead creates a shadow copy of the specified index(es) offline, and then sends a signal to `searchd` to pick up that copy. So you should _never_ get a partially populated index with `indexer`; it’s always all-or-nothing.

More details on running with configs are also below, refer to the [“Writing your first config”](http://sphinxsearch.com/docs/sphinx3.html#writing-your-first-config) section.

### Getting started on Linux (and MacOS)

Versions and file names _will_ vary, and you most likely _will_ want to configure Sphinx at least a little, but for an immediate quickstart:

    $ wget -q http://sphinxsearch.com/files/sphinx-3.0.2-2592786-linux-amd64.tar.gz
    $ tar zxf sphinx-3.0.2-2592786-linux-amd64.tar.gz
    $ cd sphinx-3.0.2-2592786-linux-amd64/bin
    $ ./searchd
    Sphinx 3.0.2 (commit 2592786)
    Copyright (c) 2001-2018, Andrew Aksyonoff
    Copyright (c) 2008-2016, Sphinx Technologies Inc (http://sphinxsearch.com)

    listening on all interfaces, port=9312
    listening on all interfaces, port=9306
    WARNING: No extra index definitions found in data folder
    $

That’s it; the daemon should now be running and accepting connections on port 9306. And you can connect to it using MySQL CLI (see below for more details, or just try `mysql -P9306` right away).

### Getting started on Windows

Pretty much the same story, except that on Windows `searchd` will not automatically go into background:

    C:\Sphinx\>searchd.exe
    Sphinx 3.0-dev (c3c241f)
    ...
    accepting connections
    prereaded 0 indexes in 0.000 sec

This is alright. Do not kill it. Just switch to a separate session and start querying.

### Running queries via MySQL shell

Run the MySQL CLI and point it to a port 9306. For example on Windows:

    C:\>mysql -h127.0.0.1 -P9306
    Welcome to the MySQL monitor.  Commands end with ; or \g.
    Your MySQL connection id is 1
    Server version: 3.0-dev (c3c241f)
    ...

I have intentionally used `127.0.0.1` in this example for two reasons (both caused by MySQL CLI quirks, not Sphinx):

- sometimes, an IP address is required to use the `-P9306` switch, not `localhost`
- sometimes, `localhost` works but causes a connection delay

But in the simplest case even just `mysql -P9306` should work fine.

And from there, just run SphinxQL queries:

    mysql> CREATE TABLE test (gid integer, title field stored,
        -> content field stored);
    Query OK, 0 rows affected (0.00 sec)

    mysql> INSERT INTO test (id, title) VALUES (123, 'hello world');
    Query OK, 1 row affected (0.00 sec)

    mysql> INSERT INTO test (id, gid, content) VALUES (234, 345, 'empty title');
    Query OK, 1 row affected (0.00 sec)

    mysql> SELECT * FROM test;
    +------+------+-------------+-------------+
    | id   | gid  | title       | content     |
    +------+------+-------------+-------------+
    |  123 |    0 | hello world |             |
    |  234 |  345 |             | empty title |
    +------+------+-------------+-------------+
    2 rows in set (0.00 sec)

    mysql> SELECT * FROM test WHERE MATCH('hello');
    +------+------+-------------+---------+
    | id   | gid  | title       | content |
    +------+------+-------------+---------+
    |  123 |    0 | hello world |         |
    +------+------+-------------+---------+
    1 row in set (0.00 sec)

    mysql> SELECT * FROM test WHERE MATCH('@content hello');
    Empty set (0.00 sec)

SphinxQL is our own SQL dialect, described in more detail in the respective [SphinxQL Reference](http://sphinxsearch.com/docs/sphinx3.html#sphinxql-reference) section.

### Writing your first config

All those easy examples above were utilizing a config-less mode, where `searchd` stores and manages all the data and settings `./sphinxdata` data folder, and you have to manage everything via `searchd` itself.

However, because as of v.3.x the config-less mode is not yet complete (certain settings and tools are still missing), many instances would likely still want to specify their indexes and settings via ye good olde `sphinx.conf` config file.

You can begin with `etc/sphinx-min.conf.dist` example as a starting point. That example shows how to use both RT indexes that you would populate on the fly, and plain indexes that you would populate from your database. For the latter, there also is a tiny matching `etc/example.sql` MySQL dump with a few sample tables and rows that the `test1` index from `sphinx-min.conf.dist` would access.

However, even that small sample is not really minimal. The minimal config only requires you to specify 2 paths for log and pid files, and define 1 index:

    searchd
    {
        log = ./data/searchd.log
        pid_file = ./data/searchd.pid
    }

    index mydocs
    {
        type = rt
        path = ./data/mydocs
        rt_field = title
        rt_attr_json = j
    }

And with just that, you can start `searchd` in config mode and start firing queries right away. (Do not forget to create the `data` directory though.)

    $ mkdir data

    $ ./searchd
    Sphinx 3.3.1-dev (commit 00642f6c)
    Copyright (c) 2001-2020, Andrew Aksyonoff
    Copyright (c) 2008-2016, Sphinx Technologies Inc (http://sphinxsearch.com)

    using config file './sphinx.conf'...
    listening on all interfaces, port=9306
    precaching index 'mydocs'
    precached 1 indexes using 1 threads in 0.0 sec

    $ mysql -h127.0.0.1 -P9306
    mysql> insert into mydocs values(111, 'hello world', '{"foo":"bar"}');
    Query OK, 1 row affected (0.01 sec)

    mysql> select * from mydocs where match('hello');
    +------+---------------+
    | id   | j             |
    +------+---------------+
    |  111 | {"foo":"bar"} |
    +------+---------------+
    1 row in set (0.00 sec)

### Running queries from PHP, Python, etc

    <?php

    $conn = mysqli_connect("127.0.0.1:9306", "", "", "");
    if (mysqli_connect_errno())
        die("failed to connect to Sphinx: " . mysqli_connect_error());

    $res = mysqli_query($conn, "SHOW VARIABLES");
    while ($row = mysqli_fetch_row($res))
        print "$row[0]: $row[1]\n";

TODO: examples

### Running queries via HTTP

TODO: examples

### Installing `indexer` SQL drivers on Linux

This only affects `indexer` ETL tool only. If you never bulk load data from SQL sources using it (of course CSV and XML sources are still fine), you can safely skip this section. (And on Windows all the drivers come with the package.)

Depending on your OS, the required package names may vary. Here are some current (as of Mar 2018) package names for Ubuntu and CentOS:

    ubuntu$ apt-get install libmysqlclient-dev libpq-dev unixodbc-dev
    ubuntu$ apt-get install libmariadb-client-lgpl-dev-compat

    centos$ yum install mariadb-devel postgresql-devel unixODBC-devel

Why might these be needed, and how they work?

`indexer` natively supports MySQL (or MariaDB), PostgreSQL, and UnixODBC drivers. Meaning it can natively connect to those databases, run SQL queries, extract results, and create full-text indexes from that. Binaries now always come with that _support_ enabled.

However, you still need to have a specific driver _library_ installed on your system, so that `indexer` could dynamically load it, and access the database. Depending on the specific database and OS you use, the package names might be different, but here go a few common pointers.

The driver libraries are loaded by name. The following names are attempted:

- MySQL: `libmysqlclient.so` or `libmariadb.so`
- PostgreSQL: `libpq.so`
- ODBC: `libodbc.so`

To support MacOS, `.dylib` extension (in addition to `.so`) is also tried.

## Main concepts

Alas, many projects tend to reinvent their own dictionary, and Sphinx is no exception. Sometimes that probably creates confusion for no apparent reason. For one, what SQL guys call “tables” (or even “relations” if they are old enough to remember Edgar Codd), and MongoDB guys call “collections”, we the text search guys tend to call “indexes”, and not really out of mischief and malice either, but just because for us, those things _are_ primarily FT (full-text) indexes. Thankfully, most of the concepts are close enough, so our personal little Sphinx dictionary is tiny. Let’s see.

Short cheat sheet!

Sphinx

Closest SQL equivalent

Index

Table

Document

Row

Field or attribute

Column and/or a FULLTEXT index

Indexed field

_Just_ a FULLTEXT index on a text column

Stored field

Text column _and_ a FULLTEXT index on it

Attribute

Column

MVA

Column with an INT_SET type

JSON attribute

Column with a JSON type

Attribute index

Index

Document ID, docid

Column called “id”, with a BIGINT type

Row ID, rowid

Internal Sphinx row number

And now for a little more elaborate explanation.

### Indexes

Sphinx indexes are semi-structured collections of documents. They may seem closer to SQL tables than to Mongo collections, but in their core, they really are neither. The primary, foundational data structure here is a _full-text index_. It is a special structure that lets us respond very quickly to a query like “give me the (internal) identifiers of all the documents that mention This or That keyword”. And everything else (any extra attributes, or document storage, or even the SQL or HTTP querying dialects, and so on) that Sphinx provides is essentially some kind of an addition on top of that base data structure. Well, hence the “index” name.

Schema-wise, Sphinx indexes try to combine the best of schemaful and schemaless worlds. For “columns” where you know the type upfront, you can use the statically typed attributes, and get the absolute efficiency. For more dynamic data, you can put it all into a JSON attribute, and still get quite decent performance.

So in a sense, Sphinx indexes == SQL tables, except (a) full-text searches are fast and come with a lot of full-text-search specific tweaking options; (b) JSON “columns” (attributes) are quite natively supported, so you can go schemaless; and (c) for full-text indexed fields, you can choose to store _just_ the full-text index and ditch the original values.

### Documents

Documents are essentially just a list of named text fields, and arbitrary-typed attributes. Quite similar to SQL rows; almost indistiguishable, actually.

As of v.3.0.1, Sphinx still requires a unique `id` attribute, and implicitly injects an `id BIGINT` column into indexes (as you probably noticed in the [Getting started](http://sphinxsearch.com/docs/sphinx3.html#getting-started) section). We still use those docids to identify specific rows in `DELETE` and other statements. However, unlike in v.2.x, we no longer use docids to identify documents internally. Thus, zero and negative docids are already allowed.

### Fields

Fields are the texts that Sphinx indexes and makes keyword-searchable. They always are _indexed_, as in full-text indexed. Their original, unindexed contents can also be _stored_ into the index for later retrieval. By default, they are not, and Sphinx is going to return attributes only, and _not_ the contents. However, if you explicitly mark them as stored (either with a `stored` flag in `CREATE TABLE` or in the ETL config file using `stored_fields` directive), you can also fetch the fields back:

    mysql> CREATE TABLE test1 (title field);
    mysql> INSERT INTO test1 VALUES (123, 'hello');
    mysql> SELECT * FROM test1 WHERE MATCH('hello');
    +------+
    | id   |
    +------+
    |  123 |
    +------+
    1 row in set (0.00 sec)

    mysql> CREATE TABLE test2 (title field stored);
    mysql> INSERT INTO test2 VALUES (123, 'hello');
    mysql> SELECT * FROM test2 WHERE MATCH('hello');
    +------+-------+
    | id   | title |
    +------+-------+
    |  123 | hello |
    +------+-------+
    1 row in set (0.00 sec)

Stored fields contents are stored in a special index component called document storage, or DocStore for short.

### Attributes

Sphinx supports the following attribute types:

- INTEGER, unsigned 32-bit integer
- BIGINT, signed 64-bit integer
- FLOAT, 32-bit (single precision) floating point
- BOOL, 1-bit boolean
- STRING, a text string
- JSON, a JSON document
- MVA, an order-insensitive set of unique INTEGERs
- MVA64, an order-insensitive set of unique BIGINTs

All of these should be pretty straightforward. However, there are a couple Sphinx specific JSON performance tricks worth mentioning:

- All scalar values (integers, floats, doubles) are converted and internally stored natively.
- All scalar value _arrays_ are detected and also internally stored natively.
- You can use `123.45f` syntax extension to mark 32-bit floats (by default all floating point values in JSON are 64-bit doubles).

For example, when the following document is stored into a JSON column in Sphinx:

    {"title":"test", "year":2017, "tags":[13,8,5,1,2,3]}

Sphinx detects that the “tags” array consists of integers only, and stores the array data using 24 bytes exactly, using just 4 bytes per each of the 6 values. Of course, there still are the overheads of storing the JSON keys, and the general document structure, so the _entire_ document will take more than that. Still, when it comes to storing bulk data into Sphinx index for later use, just provide a consistently typed JSON array, and that data will be stored - and processed! - with maximum efficiency.

Attributes are supposed to fit into RAM, and Sphinx is optimized towards that case. Ideally, of course, all your index data should fit into RAM, while being backed by a fast enough SSD for persistence.

Now, there are _fixed-width_ and _variable-width_ attributes among the supported types. Naturally, scalars like INTEGER and FLOAT will always occupy exactly 4 bytes each, while STRING and JSON types can be as short as, well, empty; or as long as several megabytes. How does that work internally? Or in other words, why don’t I just save everything as JSON?

The answer is performance. Internally, Sphinx has two separate storages for those row parts. Fixed-width attributes, including hidden system ones, are essentially stored in big static NxM matrix, where N is the number of rows, and M is the number of fixed-width attributes. Any accesses to those are very quick. All the variable-width attributes for a single row are grouped together, and stored in a separate storage. A single offset into that second storage (or “vrow” storage, short for “variable-width row part” storage) is stored as hidden fixed-width attribute. Thus, as you see, accessing a string or a JSON or an MVA value, let alone a JSON key, is somewhat more complicated. For example, to access that `year` JSON key from the example just above, Sphinx would need to:

- read `vrow_offset` from a hidden integer attribute
- access the vrow part using that offset
- decode the vrow, and find the needed JSON attribute start
- decode the JSON, and find the `year` key start
- check the key type, just in case it needs conversion to integer
- finally, read the `year` value

Of course, optimizations are done on every step here, but still, if you access a _lot_ of those values (for sorting or filtering the query results), there will be a performance impact. Also, the deeper the key is buried into that JSON, the worse. For example, using a tiny test with 1,000,000 rows and just 4 integer attributes plus exactly the same 4 values stored in a JSON, computing a sum yields the following:

Attribute

Time

Slowdown

Any INT

0.032 sec

\-

1st JSON key

0.045 sec

1.4x

2nd JSON key

0.052 sec

1.6x

3rd JSON key

0.059 sec

1.8x

4th JSON key

0.065 sec

2.0x

And with more attributes it would eventually slowdown even worse than 2x times, especially if we also throw in more complicated attributes, like strings or nested objects.

So bottom line, why not JSON everything? As long as your queries only touch a handful of rows each, that is fine, actually! However, if you have a _lot_ of data, you should try to identify some of the “busiest” columns for your queries, and store them as “regular” typed columns, that somewhat improves performance.

## Using DocStore

Storing fields into your indexes is easy, just list those fields in a `stored_fields` directive and you’re all set:

    index mytest
    {
        type = rt
        path = data/mytest

        rt_field = title
        rt_field = content
        stored_fields = title, content
        # hl_fields = title, content

        rt_attr_uint = gid
    }

Let’s check how that worked:

    mysql> desc mytest;
    +---------+--------+-----------------+------+
    | Field   | Type   | Properties      | Key  |
    +---------+--------+-----------------+------+
    | id      | bigint |                 |      |
    | title   | field  | indexed, stored |      |
    | content | field  | indexed, stored |      |
    | gid     | uint   |                 |      |
    +---------+--------+-----------------+------+
    4 rows in set (0.00 sec)

    mysql> insert into mytest (id, title) values (123, 'hello world');
    Query OK, 1 row affected (0.00 sec)

    mysql> select * from mytest where match('hello');
    +------+------+-------------+---------+
    | id   | gid  | title       | content |
    +------+------+-------------+---------+
    |  123 |    0 | hello world |         |
    +------+------+-------------+---------+
    1 row in set (0.00 sec)

Yay, original document contents! Not a huge step generally, not for a database anyway; but a nice improvement for Sphinx which was initially designed “for searching only” (oh, the mistakes of youth). And DocStore can do more than that, namely:

- store indexed fields, `store_fields` directive
- store unindexed fields, `stored_only_fields` directive
- store precomputed data to speedup snippets, `hl_fields` directive
- be fine-tuned a little, using `docstore_type`, `docstore_comp`, and `docstore_block` directives

So DocStore can effectively replace the existing `rt_attr_string` directive. What are the differences, and when to use each?

`rt_attr_string` creates an _attribute_, uncompressed, and stored in RAM. Attributes are supposed to be small, and suitable for filtering (WHERE), sorting (ORDER BY), and other operations like that, by the millions. So if you really need to run queries like … WHERE title=‘abc’, or in case you want to update those strings on the fly, you will still need attributes.

But complete original document contents are rather rarely accessed in _that_ way! Instead, you usually need just a handful of those, in the order of 10s to 100s, to have them displayed in the final search results, and/or create snippets. DocStore is designed exactly for that. It compresses all the data it receives (by default), and tries to keep most of the resulting “archive” on disk, only fetching a few documents at a time, in the very end.

Snippets become pretty interesting with DocStore. You can generate snippets from either specific stored fields, or the entire document, or a subdocument, respectively:

    SELECT id, SNIPPET(title, QUERY()) FROM mytest WHERE MATCH('hello')
    SELECT id, SNIPPET(DOCUMENT(), QUERY()) FROM mytest WHERE MATCH('hello')
    SELECT id, SNIPPET(DOCUMENT({title}), QUERY()) FROM mytest WHERE MATCH('hello')

Using `hl_fields` can accelerate highlighting where possible, sometimes making snippets _times_ faster. If your documents are big enough (as in, a little bigger than tweets), try it! Without `hl_fields`, SNIPPET() function will have to reparse the document contents every time. With it, the parsed representation is compressed and stored into the index upfront, trading off a not-insignificant amount of CPU work for more disk space, and a few extra disk reads.

And speaking of disk space vs CPU tradeoff, these tweaking knobs let you fine-tune DocStore for specific indexes:

- `docstore_type = vblock_solid` (default) groups small documents into a single compressed block, upto a given limit: better compression, slower access
- `docstore_type = vblock` stores every document separately: worse compression, faster access
- `docstore_block = 16k` (default) lets you tweak the block size limit
- `docstore_comp = lz4hc` (default) uses LZ4HC algorithm for compression: better compression, but slower
- `docstore_comp = lz4` uses LZ4 algorithm: worse compression, but faster
- `docstore_comp = none` disables compression

## Using attribute indexes

Quick kickoff: we now have `CREATE INDEX` statement, and sometimes it _does_ make your queries faster!

    CREATE INDEX i1 ON mytest(group_id)
    DESC mytest
    SELECT * FROM mytest WHERE group_id=1
    SELECT * FROM mytest WHERE group_id BETWEEN 10 and 20
    SELECT * FROM mytest WHERE MATCH('hello world') AND group_id=23
    DROP INDEX i1 ON mytest

Point reads, range reads, and intersections between `MATCH()` and index reads are all intended to work. Moreover, `GEODIST()` can also automatically use indexes (see more below). One of the goals is to completely eliminate the need to insert “fake keywords” into your index. (Also, it’s possible to _update_ attribute indexes on the fly, as opposed to indexed text.)

Indexes on JSON keys should also work, but you might need to cast them to a specific type when creating the index:

    CREATE INDEX j1 ON mytest(j.group_id)
    CREATE INDEX j2 ON mytest(INTEGER(j.year))
    CREATE INDEX j3 ON mytest(FLOAT(j.latitude))

As of v.3.0, attribute indexes can only be created on RT indexes. However, you can (almost) _instantly_ convert your plain indexes to RT by using `ATTACH ... WITH TRUNCATE`, and run `CREATE INDEX` after that, as follows:

    ATTACH INDEX myplain TO myrt WITH TRUNCATE
    CREATE INDEX date_added ON myrt(date_added)

Geosearches with `GEODIST()` can also benefit quite a lot from attribute indexes. They can automatically compute a bounding box (or boxes) around a static reference point, and then process only a fraction of data using index reads. Refer to [Geosearches section](http://sphinxsearch.com/docs/sphinx3.html#searching-geosearches) for more details.

TODO: describe more!

### Query optimizer, and index hints

Query optimizer is the mechanism that decides, on a per-query basis, whether to use or to ignore specific indexes to compute the current query.

The optimizer can usually choose any combination of any applicable indexes. The specific index combination gets chosen based on cost estimates. Curiously, that choice is not exactly completely obvious even when we have just 2 indexes.

For instance, assume that we are doing a geosearch, something like this:

    SELECT ... FROM test1
    WHERE (lat BETWEEN 53.23 AND 53.42) AND (lon BETWEEN -6.45 AND -6.05)

Assume that we have indexes on both `lat` and `lon` columns, and can use them. More, we can get an exact final result set out of that index pair, without any extra checks needed. But should we? Instead of using both indexes it is actually sometimes more efficient to use just one! Because with 2 indexes, we have to:

1. Perform `lat` range index read, get X `lat` candidate rowids
2. Perform `lon` range index read, get Y `lon` candidate rowids
3. Intersect X and Y rowids, get N matching rowids
4. Lookup N resulting rows
5. Process N resulting rows

While when using 1 index on `lat` we only have to:

1. Perform `lat` range index read, get X `lat` candidate rowids
2. Lookup X candidate rows
3. Perform X checks for `lon` range, get N matching rows
4. Process N resulting rows

Now, `lat` and `lon` frequently are somewhat correlated. Meaning that X, Y, and N values can all be pretty close. For example, let’s assume we have 11K matches in that specific latitude range, 12K matches in longitude range, and 10K final matches, ie. `X = 11000, Y = 12000, N = 10000`. Then using just 1 index means that we can avoid reading 12K `lat` rowids and then intersecting 23K rowids, introducing, however, 2K extra row lookups and 12K `lon` checks instead. Guess what, row lookups and extra checks are actually cheaper operations, and we are doing less of them. So with a few quick estimates, using only 1 index out of 2 applicable ones suddenly looks like a better bet. That can be indeed confirm on real queries, too.

And that’s exactly how the optimizer works. Basically, it checks multiple possible index combinations, tries to estimate the associated query costs, and then picks the best one it finds.

However, the number of possible combinations grows explosively with the attribute index count. Consider a rather crazy (but possible) case with as many as 20 applicable indexes. That means more than 1 million possible “on/off” combinations. Even quick estimates for _all_ of them would take too much time. There are internal limits in the optimizer to prevent that. Which in turn means that eventually some “ideal” index set might not get selected. (But, of course, that is a rare situation. Normally there are just a few applicable indexes, say from 1 to 10, so the optimizer can afford “brute forcing” upto 1024 possible index combinations, and does so.)

Now, perhaps even worse, both the count and cost estimates are just that, ie. only estimates. They might be slightly off, or way off. The actual query costs might be somewhat different than estimated when we execute the query.

For those reasons, optimizer might occasionally pick a suboptimal query plan. In that event, or perhaps just for testing purposes, you can tweak its behavior with `SELECT` hints, and make it forcibly use or ignore specific attribute indexes. For a reference on the exact syntax and behavior, refer to [“Index hints clause”](http://sphinxsearch.com/docs/sphinx3.html#index-hints-clause).

## Using k-batches

K-batches (“kill batches”) let you bulk delete older versions of the documents (rows) when bulk loading new data into Sphinx, for example, adding a new delta index on top of an older main archive index.

K-batches in Sphinx v.3.x replace k-lists (“kill lists”) from v.2.x and before. The major differences are that:

1. They are _not_ anonymous anymore.
2. They are now only applied once on loading. (As oppposed to every search, yuck).

“Not anonymous” means that when loading a new index with an associated k-batch into `searchd`, **you now have to explicitly specify target indexes** that it should delete the rows from. In other words, “deltas” now _must_ explicitly specify all the “main” indexes that they want to erase old documents from, at index-time.

The effect of applying a k-batch is equivalent to running (just once) a bunch of `DELETE FROM X WHERE id=Y` queries, for every index X listed in `kbatch` directive, and every document id Y stored in the k-batch. With the index format updates this is now both possible, **even in “plain” indexes**, and quite efficient too.

K-batch only gets applied once. After a succesful application to all the target indexes, the batch gets cleared.

So, for example, when you load an index called `delta` with the following settings:

    index delta
    {
        ...
        sql_query_kbatch = SELECT 12 UNION SELECT 13 UNION SELECT 14
        kbatch = main1, main2
    }

The following (normally) happens:

- `delta` kbatch file is loaded
  - in this example it will have 3 document ids: 12, 13, and 14
- documents with those ids are deleted from `main1`
- documents with those ids are deleted from `main2`
- `main1`, `main2` save those deletions to disk
- if all went well, `delta` kbatch file is cleared

All these operations are pretty fast, because deletions are now internally implemented using a bitmap. So deleting a given document by id results in a hash lookup and a bit flip. In plain speak, very quick.

“Loading” can happen either by restarting or rotation or whatever, k-batches should still try to apply themselves.

Last but not least, you can also use `kbatch_source` to avoid explicitly storing all newly added document ids into a k-batch, instead, you can use `kbatch_source = kl, id` or just `kbatch_source = id`; this will automatically add all the document ids from the index to its k-batch. The default value is `kbatch_source = kl`, that is, to use explicitly provided docids only.

## Doing bulk data loads

TODO: describe rotations (legacy), RELOAD, ATTACH, etc.

## Using JSON

For the most part using JSON in Sphinx should be very simple. You just put pretty much arbitrary JSON in a proper column (aka attribute). Then you just access the necessary keys using a `col1.key1.subkey2.subkey3` syntax. Or, you access the array values using `col1.key1[123]` syntax. And that’s it.

For a literally 30-second kickoff, you can configure a test RT index like this:

    index jsontest
    {
        type = rt
        path = data/jsontest
        rt_field = title
        rt_attr_json = j
    }

Then restart or `searchd` or reload the config, and fire away a few test queries:

    mysql> INSERT INTO jsontest (id, j) VALUES (1, '{"foo":"bar", "year":2019,
      "arr":[1,2,3,"yarr"], "address":{"city":"Moscow", "country":"Russia"}}');
    Query OK, 1 row affected (0.00 sec)

    mysql> SELECT j.foo FROM jsontest;
    +-------+
    | j.foo |
    +-------+
    | bar   |
    +-------+
    1 row in set (0.00 sec)

    mysql> SELECT j.year+10, j.arr[3], j.address.city FROM jsontest;
    +-----------+----------+----------------+
    | j.year+10 | j.arr[3] | j.address.city |
    +-----------+----------+----------------+
    |    2029.0 | yarr     | Moscow         |
    +-----------+----------+----------------+
    1 row in set (0.00 sec)

However, sometimes that is not quite enough (mostly for performance reasons), and thus we have both several Sphinx-specific **JSON syntax extensions**, and several **important internal implementation details** to discuss, including a few Sphinx-specific limits. Briefly, those are as follows:

- optimized scalar storage (for `int8`, `int32`, `int64`, `bool`, `float`, and `NULL` types)
- optimized array storage (for `int8`, `int32`, `int64`, `float`, `double`, and `string` types)
- optimized key name storage with key compression (optional, with `json_packed_keys = 1` directive)
- `0.0f` syntax extension for 32-bit float values
- `int8[]` and `float[]` syntax extensions for 8-bit integer and 32-bit float arrays, respectively

**Optimized storage** means that _usually_ Sphinx auto-detects the actual value types, both for standalone values and for arrays, and then uses the smallest storage type that works.

So when a 32-bit (4-byte) integer is enough for a numeric value, Sphinx would automatically store just that. If that overflows, no need to worry, Sphinx would just automatically switch to 8-byte integer values, or even `double` values (still 8-byte).

Ditto for arrays. When your arrays contain a mix of actual types, Sphinx handles that just fine, and stores a generic array, where every element has a different type attached to it. However, when your array only actually contains one very specific type (for example, regular 32-bit integers only), Sphinx auto-detects that fact, and stores _that_ array in an optimized manner, using just 4 bytes per value, and skipping the repeated types. All the builtin functions support all such optimized array types, and have a special fast codepath to handle them, in a transparent fashion.

As of v.3.2, array value types that might get optimized that way are `int8`, `int32`, `int64`, `float`, `double`, and `string`. This covers pretty much all the usual numeric types, and therefore all you have to do to ensure that the optimizations kick in is, well, to only use one actual type in your data.

So everything is on autopilot, mostly. However, there are several exceptions to that rule that still require a tiny bit of effort from you!

**First, there is a catch with `float` vs `double` types.** The default storage type for floating point values in Sphinx is the high-precision, 64-bit `double` type, just as (kinda) specified by JSON.

So the regular `{"scale":1.23}` syntax would have Sphinx store an 8-byte `double` value. However, that just might be overkill precision for some (if not most!) tasks, and to save on storage, you might want to store your values using the 32-bit (4-byte) `float` type instead.

Unfortunately, at the moment there is no standard way to specify that, and so Sphinx offers a custom extension: attach `f` suffix to your value, ie. use `{"scale":1.23f}` syntax instead. That works in Sphinx, and that lets it know that a `float` type is enough.

**Second, `int8` arrays must be explicit.** Even though Sphinx can auto-detect the fact that all your array values are integers in the -128 to 127 range, and can be stored efficiently using just 1 byte per value, it does _not_ just make that assumption, and uses `int32` type instead.

And this happens because there is no way for Sphinx to tell by looking at _just_ those values whether you realy wanted an optimized `int8` vector, or the intent was to just have a placeholder (filled with either `0`, or `-1`, or what have you) `int32` vector for future updates. Given that JSON updates are currently in-place, at this decision point Sphinx chooses to go with the more conservative but flexible route, and store an `int32` vector even for something that could be store more efficiently like `[0, 0, 0, 0]`.

To force that vector into super-slim 1-byte values, you _have_ to use a syntax extension, and use `int8[0, 0, 0, 0]` as your value.

**Third, watch out for integer vs float mixes.** The auto-detection happens on a per-value basis. Meaning that an array value like `[1, 2, 3.0]` will be marked as mixing two different types, `int32` and `double`. So neither the `int32` nor (worse) `double` array storage optimization can kick in for this particular array.

You can enforce any JSON-standard type on Sphinx here using regular JSON syntax. To store it as integers, you should simply get rid of that pesky dot that triggers doubles, and use `[1, 2, 3]` syntax. For doubles, on the contrary, the dot should be everywhere, ie. you should use `[1.0, 2.0, 3.0]` syntax.

Finally, for the non-standard `float` type extension, you can also use the `f` suffix, ie. `[1.0f, 2.0f, 3.0f]` syntax. But that might be inconvenient, so you can also use the `float[1, 2, 3.0]` syntax instead. Either of these two forms enables Sphinx to auto-convert your vector to nice and fast optimized floats.

That was all about the values though. What about the keys?

**Normally, keys are stored as is.** Meaning that if you have a `superLongKey` in (almost) every single document, that key will be stored as a plain old text string, and repeated as many times as there are documents. And all those repetitions would consume some RAM bytes. Flexible, but not really efficient.

So the rule of thumb is, super-long key names are, well, okay, but not really great. Just as with regular JSON. Of course, for smaller indexes the savings might just be negligible. But for bigger ones, you might want to consider shorter key names.

Or, **packed JSON keys** feature alleviates that automatically. It keeps track of the most frequently mentioned keys, and stores top keys using just 1 byte per key value. You can enable it by setting `json_packed_keys = 1` flag in your index config (and rebuilding the index where necessary). That way, you can use as long key names as you want, and Sphinx will kinda “zip” the JSON internally.

Beware and benchmark, though, that currently there can occasionally be some associated performance impact here (even though not huge), both at indexing and at search time. (Otherwise, the packing would just be always on!)

### JSON comparison quirks

Comparisons with JSON can be a little tricky when it comes to value types. Especially the numeric ones, because of all the `integer` vs `float` vs `double` jazz. (And, mind you, by default the floating-point values will be stored as `double`.) Briefly, beware that:

1. String comparisons are strict, and require the string type.

    Meaning that `WHERE j.str1='abc'` check must only pass when _all_ the following conditions are true: 1) `str1` key exists; 2) `str1` value type is exactly `string`; 3) the value matches.

    Therefore, for a sudden _integer_ value compared against a string constant, for example, `{"str1":123}` value against a `WHERE j.str1='123'` condition, the check will fail. As it should, there are no implicit conversions here.
2. Numeric comparisons against integers match any numeric type, not just integers.

    Meaning that both `{"key1":123}` and `{"key1":123.0}` values must pass the `WHERE j.key1=123` check. Again, as expected.
3. Numeric comparisons against floats _forcibly_ convert double values to (single-precision) floats, and roundoff issues may arise.

    Meaning that when you store something like `{"key1":123.0000001}` into your index, then the `WHERE j.key1=123.0` check will pass, because roundoff to `float` looses that fractional part. However, at the same time `WHERE j.key1=123` check will _not_ pass, because _that_ check will use the original double value and compare it against the integer constant.

    This might be a bit confusing, but otherwise (without roundoff) the situation would be arguably worse: in an even more counter-intuitive fashion, `{"key1":2.22}` does _not_ pass the `WHERE j.key1>=2.22` check, because the reference constant here is `float(2.22)`, and then because of rounding, `double(2.22) < float(2.22)`!

TODO: describe limits, json_xxx settings, our syntax extensions, etc.

## Using array attributes

Array attributes let you save a fixed amount of integer or float values into your index. The supported types are:

- `attr_int_array` that stores signed 32-bit integers;
- `attr_int8_array` that stores signed 8-bit integers (-128 to 127 range);
- `attr_float_array` that stores 32-bit floats.

To declare an array attribute, use the following syntax:

`{rt|sql|xmlpipe|csvpipe|tsvpipe}_attr_{int|int8|float}_array = NAME[SIZE]`

Where `NAME` is the attribute name, and `SIZE` is the array size, in elements. For example:

    index rt
    {
        type = rt

        rt_field = title
        rt_field = content

        rt_attr_uint = gid # regular attribute
        rt_attr_float_array = vec1[5] # 5D array of floats
        rt_attr_int8_array = vec2[3] # 3D array of small 8-bit integers
        # ...
    }

    source test1
    {
        type = mysql

        sql_attr_int8_array = vec1[17] # 17D array of small 8-bit integers
        # ...
    }

The array dimensions must be between 2 and 8192, inclusive.

The array gets aligned to the nearest 4 bytes. This means that an `int8_array` with 17 elements will actually use 20 bytes for storage.

The expected input array value for both `INSERT` queries and source indexing is either a comma or space-separated string with the values, or an empty string:

    INSERT INTO rt (id, vec1) VALUES (123, '3.14, -1, 2.718, 2019, 100500');
    INSERT INTO rt (id, vec1) VALUES (124, '');

Empty strings will zero-fill the array. Non-empty strings are subject to strict validation. First, there must be exactly as many values as the array can hold. So you can not store 3 or 7 values into a 5-element array. Second, the value ranges might also be be validated. So you will not be able to store a value of `1000` into an `int8_array` because it’s out of -128..127 range.

Attempting to `INSERT` an invalid array value will fail. For example:

    mysql> INSERT INTO rt (id, vec1) VALUES (200, '1 2 3');
    ERROR 1064 (42000): bad array value

    mysql> INSERT INTO rt (id, vec1) VALUES (200, '1 2 3 4 5 6');
    ERROR 1064 (42000): bad array value

    mysql> INSERT INTO rt (id, vec2) VALUES (200, '0, 1, 2345');
    ERROR 1064 (42000): bad array value

However, when batch indexing with `indexer`, an invalid array value will be reported as a warning, and zero-fill the array, but it will **not** fail the entire indexing batch.

At the moment, the only function that supports arrays is `DOT()`, so you can compute a dot product between an array and a constant vector:

    mysql> SELECT id, DOT(vec1,FVEC(1,2,3,4,5)) d FROM rt;
    +------+--------------+
    | id   | d            |
    +------+--------------+
    |  123 | 510585.28125 |
    |  124 |            0 |
    +------+--------------+
    2 rows in set (0.00 sec)

## Using wordforms

Sphinx supports several different keyword remapping types (usually applied both when indexing and when searching), all currently called wordforms. The principal types are as follows.

1. Morphology-replacing 1:1 wordforms.
2. Pre-morphology M:N wordforms.
3. Post-morphology 1:1 wordforms.

Additionally, two of these types can be applied at indexing time only.

4. Document-only morphology-replacing 1:1 wordforms.
5. Document-only pre-morphology M:N wordforms.

Wordforms are usually all listed in a separate text file (or a set of files), and added to the index with a `wordforms` directive. The wordforms file syntax for all these types is as follows.

    geese => goose              # type 1, morph-repl 1:1
    core 2 duo => c2d           # type 2, pre-morph M:N
    e8400 => c2d e8400          # type 2, pre-morph M:N
    ~vehicle => car             # type 3, post-morph 1:1
    !foo => bar                 # type 4, doc-only morph-repl 1:1
    !grrm => grrm george martin # type 5, doc-only pre-morph M:N

So generally wordforms are just two lists of keywords (source and destination mappings respectively), separated by `=>` special token.

Post-morphology wordforms are marked with `~` in the first column.

Document-only wordforms are marked with `!` in the first column.

Comments are marked with `#`, and everything from `#` to the end of a line is considered a comment.

Briefly, all these different types work as follows.

**Morphology-replacing wordforms** effectively are the top-priority morphology alternative. They engage before any morphology, and the _fully_ substitute any other morphology processing. So use them with extreme care (or better yet, avoid using them at all) when you have any other morphology processing enabled.

For instance, that `geese => goose` example above is utterly _wrong_ when you use `morphology = stem_en`. No, it does properly normalize that plural `geese` to singular `goose`, so that part is correct. Problem is, Porter stemmer does not normalize `goose` to itself, it will emit `goos` stem instead. So in order to fixup Porter stemmer specifically you would have to map to that _stem_, ie. use a `geese => goos` wordform. Extreme care.

**Pre-morphology wordforms** remap the source keywords before morphology, and then the destination keywords are additionally passed through the morphology. So, for example, `six geese => 6 goose` would _not_ be subject to `stem_en` issue above, as both `6` and `goose` would also be stemmed.

At the moment only the M:N wordforms can be pre-morphology, not 1:1, so you have to have either multiple source keywords, or multiple destination keywords.

**Post-morphology wordforms** remap the source keywords after morphology. Note that at the moment (and rather counter-intuitively) the destination keywords will _not_ be passed through morphology one more time, so the `stem_en` issue arises once again.

**Document-only wordforms** are only applied at indexing time, and never at query time. This is pretty useful for indexing time expansions, and that’s why that example with `grrm` maps it to itself too, and not just `george martin`.

In the “expansion” usecase, they are more efficient when _searching_, compared to similar regular wordforms.

Indeed, when searching for a source mapping, regular wordforms would expand to all keywords (in our example, to all 3 keywords, `grrm george martin`), fetch and intersect them, and do all that work for… nothing! Because we can obtain exactly the same result much more efficiently by simply fetching just the source keywords (just `grrm` in our example). And that’s exactly how document-only wordforms work, they would just skip the expansion altogether.

And when searching for (a part of) a destination mapping, nothing would change. In that case both document-only and regular wordforms would just execute the query completely identically.

Bottom line, use document-only wordforms when you’re doing expansions, in order to avoid that unnecessary performance hit.

## Using UDFs

### UDFs overview

Sphinx supports User Defined Functions (or UDFs for short) that let you extend its expression engine:

    SELECT id, attr1, myudf(attr2, attr3+attr4) ...

You can load and unload UDFs into `searchd` dynamically, ie. without having to restart the daemon itself, and then use them in most expressions when searching and ranking. Quick summary of the UDF features is as follows.

- UDFs can accept most of the argument types that Sphinx supports, namely:
  - **numerics**, ie. integers (32-bit and 64-bit) and floats (32-bit);
  - **MVAs**, ie. sets of integers (32-bit and 64-bit);
  - **strings**, including binary non-ASCIIZ blobs;
  - **`FACTORS()`**, ie. special blobs with ranking signals;
  - **JSON objects**, including subobjects or individual fields;
  - **float vectors**.
- UDFs can return integer, float, or string values.
- UDFs can check the argument number, types, and names during the query setup phase, and raise errors.

UDFs have a wide variety of uses, for instance:

- adding custom mathematical or string functions;
- accessing the database or files from within Sphinx;
- implementing complex ranking functions.

UDFs reside in the external dynamic libraries (`.so` files on UNIX and `.dll` on Windows systems). Library files need to reside in a trusted folder specified by `plugin_dir` directive, for obvious security reasons: securing a single folder is easy; letting anyone install arbitrary code into `searchd` is a risk. You can load and unload them dynamically into `searchd` with `CREATE FUNCTION` and `DROP FUNCTION` SphinxQL statements, respectively. Also, you can seamlessly reload UDFs (and other plugins) with `RELOAD PLUGINS` statement. Sphinx keeps track of the currently loaded functions, that is, every time you create or drop an UDF, `searchd` writes its state to the `sphinxql_state` file as a plain good old SQL script.

Once you successfully load an UDF, you can use it in your `SELECT` or other statements just as any of the builtin functions:

    SELECT id, MYCUSTOMFUNC(groupid, authorname), ... FROM myindex

Multiple UDFs (and other plugins) may reside in a single library. That library will only be loaded once. It gets automatically unloaded once all the UDFs and plugins from it are dropped.

Aggregation functions are not supported just yet. In other words, your UDFs will be called for just a single document at a time and are expected to return some value for that document. Writing a function that can compute an aggregate value like `AVG()` over the entire group of documents that share the same `GROUP BY` key is not yet possible. However, you can use UDFs within the builtin aggregate functions: that is, even though `MYCUSTOMAVG()` is not supported yet, `AVG(MYCUSTOMFUNC())` should work alright!

UDFs are local. In order to use them on a cluster, you have to put the same library on all its nodes and run proper `CREATE FUNCTION` statements on all the nodes too. This might change in the future versions.

### UDF programming introduction

The UDF interface is plain C. So you would usually write your UDF in C or C++. (Even though in theory it might be possible to use other languages.)

Your very first starting point should be `src/udfexample.c`, our example UDF library. That libary implements several different functions, to demonstrate how to use several different techniques (stateless and stateful UDFs, different argument types, batched calls, etc).

The files that provide the UDF interface are:

- `src/sphinxudf.h` that declares the essential types and helper functions;
- `src/sphinxudf.c` that implements those functions.

For UDFs that **do not** implement ranking, and therefore do not need to handle `FACTORS()` arguments, simply including the `sphinxudf.h` header is sufficient.

To be able to parse the `FACTORS()` blobs from your UDF, however, you will also need to compile and link with `sphinxudf.c` source file.

Both `sphinxudf.h` and `sphinxudf.c` are standalone. So you can copy around those files only. They do not depend on any other bits of Sphinx source code.

Within your UDF, you should literally implement and export just two functions.

**First**, you must define `int LIBRARYNAME_ver() { return SPH_UDF_VERSION; }` in order to implement UDF interface version control. LIBRARYNAME should be replaced with the name of your library. Here’s a more complete example:

    #include <sphinxudf.h>

    // our library will be called udfexample.so, thus, so it must define
    // a version function named udfexample_ver()
    int udfexample_ver()
    {
        return SPH_UDF_VERSION;
    }

This version checker protects you from accidentally loading libraries with mismatching UDF interface versions. (Which would in turn usually cause either incorrect behavior or crashes.)

**Second**, you must implement the actual function, too. For example:

    sphinx_int64_t testfunc(SPH_UDF_INIT * init, SPH_UDF_ARGS * args,
        char * error_message)
    {
       return 123;
    }

UDF function names in SphinxQL are case insensitive. However, the respective C/C++ **function names must be all lower-case**, or the UDF will fail to load.

More importantly, it is vital that:

1. the calling convention is C (aka `__cdecl`);
2. arguments list matches the plugin system expectations exactly;
3. the return type matches the one you specify in `CREATE FUNCTION`;
4. the implemented C/C++ functions are thread-safe.

Unfortunately, there is no (easy) way for `searchd` to automatically check for those mistakes when loading the function, and they could crash the server and/or result in unexpected results.

Let’s discuss the simple `testfunc()` example in a bit more detail.

The first argument, a pointer to `SPH_UDF_INIT` structure, is essentially just a pointer to our function state. Using that state is optional. In this example, the function is stateless, it simply returns 123 every time it gets called. So we do not have to define an initialization function, and we can simply ignore that argument.

The second argument, a pointer to `SPH_UDF_ARGS`, is the most important one. All the actual call arguments are passed to your UDF via this structure. It contains the call argument count, names, types, etc. So whether your function gets called like with simple constants, like this:

    SELECT id, testfunc(1) ...

or with a bunch of subexpressions as its arguments, like this:

    SELECT id, testfunc('abc', 1000*id+gid, WEIGHT()) ...

or anyhow else, it will receive the very same `SPH_UDF_ARGS` structure, in **all** of these cases. However, the _data_ passed in the args structure can be a little different.

In the `testfunc(1)` call example `args->arg_count` will be set to 1, because, naturally we have just one argument. In the second example, `arg_count` will be equal to 3. Also `args->arg_types` array will contain different type data for these two calls. And so on.

Finally, the third argument, `char * error_message` serves both as error flag, and a method to report a human-readable message (if any). UDFs should only raise that flag/message to indicate _unrecoverable_ internal errors; ones that would prevent any subsequent attempts to evaluate that instance of the UDF call from continuing.

You must _not_ use this flag for argument type checks, or for any other error reporting that is likely to happen during “normal” use. This flag is designed to report sudden critical runtime errors only, such as running out of memory.

If we need to, say, allocate temporary storage for our function to use, or check upfront whether the arguments are of the supported types, then we need to add two more functions, with UDF initialization and deinitialization, respectively.

    int testfunc_init ( SPH_UDF_INIT * init, SPH_UDF_ARGS * args,
        char * error_message )
    {
        // allocate and initialize a little bit of temporary storage
        init->func_data = malloc(sizeof(int));
        *(int*)init->func_data = 123;

        // return a success code
        return 0;
    }

    void testfunc_deinit(SPH_UDF_INIT * init)
    {
        // free up our temporary storage
        free(init->func_data);
    }

Note how `testfunc_init()` also receives the call arguments structure. At that point in time we do not yet have any actual per-row _values_ though, so the `args->arg_values` will be `NULL`. But the argument names and types are already known, and will be passed. You can check them in the initialization function and return an error if they are of an unsupported type.

### UDF argument and return types

UDFs can receive arguments of pretty much any valid internal Sphinx type. When in doubt, refer to `sphinx_udf_argtype` enum in `sphinxudf.h` for a full list. For convenience, here’s a short reference table:

UDF arg type

C/C++ type, and a short description

Len

UINT32

`uint32_t`, unsigned 32-bit integer

\-

INT64

`int64_t`, signed 64-bit integer

\-

FLOAT

`float`, single-precision (32-bit) IEEE754 float

\-

STRING

`char *`, non-ASCIIZ string, with a separate length

Yes

UINT32SET

`uint32_t *`, sorted set of u32 integers

Yes

INT64SET

`int64_t *`, sorted set of i64 integers

Yes

FACTORS

`void *`, special blob with ranking signals

\-

JSON

`char *`, JSON (sub)object or field in a string format

\-

FLOAT_VEC

`float *`, an unsorted array of floats

Yes

The `Len` column in this table means that the argument length is passed separately via `args->str_lengths[i]` in addition to the argument value `args->arg_values[i]` itself.

For `STRING` arguments, the length contains the string length, in bytes. For all other types, it contains the number of elements.

As for the return types, UDFs can currently return numeric or string values. The respective types are as follows:

Sphinx type

Regular return type

Batched output arg type

`INTEGER`

`sphinx_int64_t`

`int *`

`BIGINT`

`sphinx_int64_t`

`sphinx_int64_t *`

`FLOAT`

`double`

`float *`

`STRING`

`char *`

\-

Batched calls are discussed below.

We still define our own `sphinx_int64_t` type in `sphinxudf.h` for clarity and convenience, but these days, any standard 64-bit integer type like `int64_t` or `long long` should also suffice, and can be safely used in your UDF code.

Also note that for `STRING` types you **must** use `args->fn_malloc` function to allocate the returned values.

Note how _internally_ in your UDF you can use whatever allocator you want, so the `testfunc_init()` example above is correct even though it uses `malloc()` directly. You manage that pointer yourself, it gets freed up using a matching `free()` call, and all is well. However, the _returned_ strings values will be managed by Sphinx, and we have our own allocator. So for the return values specifically, you need to use it too.

### UDF call batching

Since v.3.3 Sphinx supports two types of the “main” UDF call with a numeric return type:

- regular, called with exactly 1 row at a time;
- batched, called with batches of 1 to 128 rows at a time.

These two types have different C/C++ signatures, for example:

    /// regular call that RETURNS INTEGER
    /// note the `sphinx_int64_t` ret type
    sphinx_int64_t foo(SPH_UDF_INIT * init, SPH_UDF_ARGS * args,
        char * error);

    /// batched call that RETURNS INTEGER
    /// note the `int *` out arg type
    void foo_batch(SPH_UDF_INIT * init, SPH_UDF_ARGS * args,
        int * results, int batch_size, char * error);

UDF must define at least 1 of these two functions. As of v.3.3, UDF can define both functions, but batched calls take priority. So when both `foo_batch()` and `foo()` are defined, the engine will only use `foo_batch()`, and completely ignore `foo()`.

Batched calls are needed for performance. For instance, processing multiple documents at once with certain CatBoost ML models could be more than 5x faster.

As mentioned a little earlier, return types for batched calls differ from regular ones, again for performance reasons. So yes, the types in the example above are correct. Regular, single-row `foo()` call must use `sphinx_int64_t` for its return type either when the function was created with `RETURNS INTEGER` or `RETURNS BIGINT`, for simplicity. However the batched multi-row `foo_batch()` call **must** use an output buffer typed as `int *` when created with `RETURNS INTEGER`; or a buffer typed as `sphinx_int64_t *` when created with `RETURNS BIGINT`; just as mentioned in that types table earlier.

Current target batch size is 128, but that size may change in either direction in the future. Assume little about `batch_size`, and very definitely do _not_ hardcode the current limit anywhere. (Say, it is reasonably safe to assume that batches will always be in 1 to 65536 range, though.)

Engine should accumulate matches upto the target size, so that most UDF calls receive complete batches. However, trailing batches will be sized arbitrarily. For example, for 397 matches there should be 4 calls to `foo_batch()`, with 128, 128, 128, and 13 matches per batch respectively.

Arguments (and their sizes where applicable) are stored into `arg_values` (and `str_lengths`) sequentially for every match in the batch. For example, you can access them as follows:

    for (int row = 0; row < batch_size; row++)
        for (int arg = 0; arg < args->arg_count; arg++)
        {
            int index = row * args->args_count + arg;
            use_arg(args->arg_values[index], args->str_lengths[index]);
        }

Batched UDF **must** fill the **entire** results array with some sane default value, even if it decides to fail with an unrecoverable error in the middle of the batch. It must never return garbage results.

On error, engine will stop calling the batched UDF for the rest of the current `SELECT` query (just as it does with regular UDFs), and automatically zero out the rest of the values. However, it is the UDFs responsbility to completely fill the failed batch anyway.

Batched calls are currently only supported for numeric UDFs, ie. functions that return `INTEGER`, `BIGINT`, or `FLOAT`; batching is not yet supported for `STRING` functions. That may change in the future.

### Using `FACTORS()` in UDFs

Most of the types map straightforwardly to the respective C types. The most notable exception is the `SPH_UDF_TYPE_FACTORS` argument type. You get that type by passing `FACTORS()` expression as an argument to your UDF. The value that the UDF will receive is a binary blob in a special internal format.

To extract individual ranking signals from that blob, you need to use either of the two `sphinx_factors_XXX()` or `sphinx_get_YYY_factor()` function families.

The first family consists of just 3 functions:

- `sphinx_factors_init()` that initializes the unpacked `SPH_UDF_FACTORS` structure;
- `sphinx_factors_unpack()` that unpacks a binary blob value into it;
- `sphinx_factors_deinit()` that cleans up an deallocates `SPH_UDF_FACTORS`.

So you need to call `init()` and `unpack()` first, then you can use the fields within the `SPH_UDF_FACTORS` structure, and then you have to call `deinit()` for cleanup. The resuling code would be rather simple, like this:

    // init!
    SPH_UDF_FACTORS F;
    sphinx_factors_init(&F);

    if (sphinx_factors_unpack((const unsigned int *)args->arg_values[0], &F))
    {
        sphinx_factors_deinit(&F); // no leaks please
        return -1;
    }

    // process!
    int result = F.field[3].hit_count;
    // ... maybe more math here ...

    // cleanup!
    sphinx_factors_deinit(&F);
    return result;

However, this access simplicity has an obvious drawback. It will cause several memory allocations per each processed document (made by `init()` and `unpack()` and later freed by `deinit()` respectively), which might be slow.

So there is another interface to access `FACTORS()` that consists of a bunch of `sphinx_get_YYY_factor()` functions. It is more verbose, but it accesses the blob data directly, and it _guarantees_ zero allocations and zero copying. So for top-notch ranking UDF performance, you want that one. Here goes the matching example code that also accesses just 1 signal from just 1 field:

    // init!
    const unsigned int * F = (const unsigned int *)args->arg_values[0];
    const unsigned int * field3 = sphinx_get_field_factors(F, 3);

    // process!
    int result = sphinx_get_field_factor_int(field3, SPH_FIELDF_HIT_COUNT);
    // ... maybe more math here ...

    // done! no cleanup needed
    return result;

### UDF calls sequences

Depending on how your UDFs are used in the query, the main function call (`testfunc()` in our running example) might get called in a rather different volume and order. Specifically,

- UDFs referenced in `WHERE`, `ORDER BY`, or `GROUP BY` clauses must and will be evaluated for every matched document. They will be called in the **natural matching order**.
- without subselects, UDFs that can be evaluated at the very last stage over the final result set will be evaluated that way, but before applying the `LIMIT` clause. They will be called in the **result set order**.
- with subselects, such UDFs will also be evaluated _after_ applying the inner `LIMIT` clause.

The calling sequence of the other functions is fixed, though. Namely,

- `testfunc_init()` is called once when initializing the query. It can return a non-zero code to indicate a failure; in that case query gets terminated early, and the error message from the `error_message` buffer is returned.
- `testfunc()` or `testfunc_batch()` is called for every eligible row batch (see above), whenever Sphinx needs to compute the UDF value(s). This call can indicate an unrecoverable error by writing either a value of 1, or some human-readable message to the `error_message` argument. (So in other words, you can use `error_message` either as a boolean flag, or a string buffer.)
- After getting a non-zero `error_message` from the main UDF call, the engine guarantees to stop calling that UDF call for subsequent rows for the rest of the query. A default return value of 0 for numerics and an empty string for strings will be used instead. Sphinx might or might not choose to terminate such queries early, neither behavior is currently guaranteed.
- `testfunc_deinit()` is called once when the query processing (in a given index shard) ends. It must get called even if the main call reported an unrecoverable error earlier.

## Indexing: CSV and TSV files

`indexer` supports indexing data in both CSV and TSV formats, via the `csvpipe` and `tsvpipe` source types, respectively. Here’s a brief cheat sheet on the respective source directives.

- `csvpipe_command = ...` specifies a command to run (for instance, `csvpipe_command = cat mydata.csv` in the simplest case).
- `csvpipe_header = 1` tells the `indexer` to pick the column list from the first row (otherwise, by default, the column list has to be specified in the config file).
- `csvpipe_attr_XXX` (where `XXX` is an attribute type, i.e. one of `bigint`, `bool`, `float`, `json`, `multi`, `multi_64`, `string`, `timestamp`, or `uint`) specifies an attribute type for a given column.
- `csvpipe_field` and `csvpipe_field_string` specify a regular full-text field and a full-text field that should also be stored as a `string` attribute, respectively.
- `csvpipe_delimiter` changes the column delimiter to a given character (this is `csvpipe` only; `tsvpipe` naturally uses tabs).

When working with TSV, you would use the very same directives, but start them with `tsvpipe` prefix (i.e. `tsvpipe_command`, `tsvpipe_header`, etc).

The first column is currently always treated as `id`, and must be a unique document identifier.

The first row can either be treated as a named list of columns (when `csvpipe_header = 1`), or as a first row of actual data. By default it’s treated as data. The column names are trimmed, so a bit of extra whitespace should not hurt.

`csvpipe_header` affects how CSV input columns are matched to Sphinx attributes and fields.

With `csvpipe_header = 0` the input file only contains data, so the order of columns is taken from the config file. Thus, the order of `csvpipe_attr_XXX` and `csvpipe_field` directives is very important in this case. You will have to explicitly declare _all_ the fields and attributes (except the leading `id`), and in _exactly_ the same order they appear in the CSV file. `indexer` will warn if there were unmatched or extraneous columns.

With `csvpipe_header = 1` the input file starts with the column names list, so the declarations from the config file are only used to adjust the types. So in this case, the order of `csvpipe_attr_XXX` and `csvpipe_field` directives does not matter any more. Also, by default all the input CSV columns will be considered as fields, so you only need to explicitly configure attributes, not fields. For example, the following should work nicely, and index `title` and `content` as fields automatically:

    1.csv:

    id, gid, title, content
    123, 11, hello world, document number one
    124, 12, hello again, document number two

    sphinx.conf:

    source csv1
    {
        type = csvpipe
        csvpipe_command = cat 1.csv
        csvpipe_header = 1
        csvpipe_attr_uint = gid
    }

## Indexing: special chars, blended tokens, and mixed codes

Sphinx provides tools to help you better index (and then later search):

- terms that have special characters in them, like `@Rihanna`, or `Procter&Gamble` or `U.S.A`, etc;
- terms that mix letters and digits, like `UE53N5740AU`.

The general approach, so-called “blending”, is the same in both cases:

- we always store a certain “base” (most granular) tokenization;
- we also additonally store (“blend”) extra tokens, as configured;
- we then let you search for either original or extra tokens.

So in the examples just above Sphinx can:

- index base tokens, such as `rihanna` or `ue53n5740au`;
- index special tokens, such as `@rihanna`;
- index parts of mixed-codes tokens, such as `ue 53` and `ue53`.

### Blended tokens (with special characters)

To index **blended tokens**, i.e. tokens with special characters in them, you should:

- add your special “blended” characters to the `blend_chars` directive;
- configure several processing modes for the extra tokens (optionally) using the `blend_mode` directive;
- rebuild your index.

Blended characters are going to be indexed both as separators, and _at the same time_ as valid characters. They are considered separators when generating the base tokenization (or “base split” for short). But in addition they also are processed as valid characters when generating extra tokens.

For instance, when you set `blend_chars = @, &, .` and index the text `@Rihanna Procter&Gamble U.S.A`, the base split stores the following six tokens into the final index: `rihanna`, `procter`, `gamble`, `u`, `s`, and `a`. Exactly like it would without the `blend_chars`, based on just the `charset_table`.

And because of `blend_chars` settings, the following three _extra_ tokens get stored: `@rihanna`, `procter&gamble`, and `u.s.a`. Regular characters are still case-folded according to `charset_table`, but those special blended characters are now preserved. As opposed to being treated as whitespace, like they were in the base split. So far so good.

But why not just add `@, &, .` to `charset_table` then? Because that way we would completely lose the base split. _Only_ the three “magic” tokens like `@rihanna` would be stored. And then searching for their “parts” (for example, for just `rihanna` or just `gamble`) would not work. Meh.

Last but not least, the in-field token positions are adjusted accordingly, and shared between the base and extra tokens:

- pos 1, `rihanna` and `@rihanna`
- pos 2, `procter` and `procter&gamble`
- pos 3, `gamble`
- pos 4, `u` and `u.s.a`
- pos 5, `s`
- pos 6, `a`

Bottom line, `blend_chars` lets you enrich the index and store extra tokens with special characters in those. That might be a handy addition to your regular tokenization based on `charset_table`.

### Mixed codes (with letters and digits)

To index **mixed codes**, i.e. terms that mix letters and digits, you need to enable `blend_mixed_codes = 1` setting (and reindex).

That way Sphinx adds extra spaces on _letter-digit boundaries_ when making the base split, but still stores the full original token as an extra. For example, `UE53N5740AU` gets broken down to as much as 5 parts:

- pos 1, `ue` and `ue53n5740au`
- pos 2, `53`
- pos 3, `n`
- pos 4, `5740`
- pos 5, `au`

Besides the “full” split and the “original” code, it is also possible to store prefixes and suffixes. See `blend_mode` discussion just below.

Also note that on certain input data mixed codes indexing can generate a lot of undesired noise tokens. So when you have a number of fields with special terms that do _not_ need to be processed as mixed codes (consider either terms like `_category1234`, or just long URLs), you can use the `mixed_codes_fields` directive and limit mixed codes indexing to human-readable text fields only. For instance:

    blend_mixed_codes = 1
    mixed_codes_fields = title, content

That could save you a noticeable amount of both index size and indexing time.

### Blending modes

There’s somewhat more than one way to generate extra tokens. So there is a directive to control that. It’s called `blend_mode` and it lets you list all the different processing variants that you require:

- `trim_none`, store a full token with all the blended characters;
- `trim_head`, store a token with heading blended characters trimmed;
- `trim_tail`, store a token with trailing blended characters trimmed;
- `trim_both`, store a token with both heading and trailing blended characters trimmed;
- `skip_pure`, do _not_ store tokens that only contain blended characters;
- `prefix_tokens`, store all possible prefix tokens;
- `suffix_tokens`, store all possible suffix tokens.

To visualize all those trims a bit, consider the following setup:

    blend_chars = @, !
    blend_mode = trim_none, trim_head, trim_tail, trim_both

    doc_title = @someone!

Quite a bunch of extra tokens will be indexed in this case:

- `someone` for the base split;
- `@someone!` for `trim_none`;
- `someone!` for `trim_head`;
- `@someone` for `trim_tail`;
- `someone` (yes, again) for `trim_both`.

`trim_both` option might seem redundant here for a moment. But do consider a bit more complicated term like `&U.S.A!` where all the special characters are blended. It’s base split is three tokens (`u`, `s`, and `a`); it’s original full form (stored for `trim_none`) is lower-case `&u.s.a!`; and so for this term `trim_both` is the only way to still generate the cleaned-up `u.s.a` variant.

`prefix_tokens` and `suffix_tokens` actually begin to generate something non-trivial on that very same `&U.S.A!` example, too. For the record, that’s because its base split is long enough, 3 or more tokens. `prefix_tokens` would be the only way to store the (useful) `u.s` prefix; and `suffix_tokens` would in turn store the (questionable) `s.a` suffix.

But `prefix_tokens` and `suffix_tokens` modes are, of course, especially useful for indexing mixed codes. The following gets stored with `blend_mode = prefix_tokens` in our running example:

- pos 1, `ue`, `ue53`, `ue53n`, `ue53n5740`, and `ue53n5740au`
- pos 2, `53`
- pos 3, `n`
- pos 4, `5740`
- pos 5, `au`

And with `blend_mode = suffix_tokens` respectively:

- pos 1, `ue` and `ue53n5740au`
- pos 2, `53` and `53n5740au`
- pos 3, `n` and `n5740au`
- pos 4, `5740` and `5740au`
- pos 5, `au`

Of course, there still can be missing combinations. For instance, `ue 53n` query will still not match any of that. However, for now we intentionally decided to avoid indexing _all_ the possible base token subsequences, as that seemed to produce way too much noise.

### Searching vs blended tokens and mixed codes

The rule of thumb is quite simple. All the extra tokens are **indexing-only**. And in queries, all tokens are treated “as is”.

**Blended characters** are going to be handled as valid characters in the queries, and _require_ matching.

For example, querying for `"@rihanna"` will _not_ match `Robyn Rihanna Fenty is a Barbadian-born singer` document. However, querying for just `rihanna` will match both that document, and `@rihanna doesn't tweet all that much` document.

**Mixed codes** are _not_ going to be automatically “sliced” in the queries.

For example, querying for `UE53` will _not_ automatically match neither `UE 53` nor `UE 37 53` documents. You need to manually add extra whitespace into your query term for that.

## Searching: query syntax

By default, full-text queries in Sphinx are treated as simple “bags of words”, and all keywords are required in a document to match. In other words, by default we perform a strict boolean AND over all keywords.

However, text queries are much more flexible than just that, and Sphinx has its own full-text query language to expose that flexibility.

You essentially use that language _within_ the `MATCH()` clause in your `SELECT` statements. So in this section, when we refer to just the `hello world` (text) query for brevity, the actual complete SphinxQL statement that you would run is something like `SELECT *, WEIGHT() FROM myindex WHERE MATCH('hello world')`.

That said, let’s begin with a couple key concepts, and a cheat sheet.

### Operators

Operators generally work on arbitrary subexpressions. For instance, you can combine keywords using operators AND and OR (and brackets) as needed, and build any boolean expression that way.

However, there is a number of exceptions. Not all operators are universally compatible. For instance, phrase operator (double quotes) naturally only works on keywords. You can’t build a “phrase” from arbitrary boolean expressions.

Some of the operators use special characters, like the phrase operator uses double quotes: `"this is phrase"`. Thus, sometimes you might have to filter out a few special characters from end-user queries, to avoid unintentionally triggering those operators.

Other ones are literal, and their syntax is an all-caps keyword. For example, MAYBE operator would quite literally be used as `(rick MAYBE morty)` in a query. To avoid triggering those operators, it should be sufficient to lower-case the query: `rick maybe morty` is again just a regular bag-of-words query that just requires all 3 keywords to match.

### Modifiers

Modifiers are attached to individual keywords, and they must work at all times, and must be allowed within any operator. So no compatibility issues there!

A couple examples would be the exact form modifier or the field start modifier, `=exact ^start`. They limit matching of “their” keyword to either its exact morphological form, or at the very start of (any) field, respectively.

### Cheat sheet

As of v.3.2, there are just 4 per-keyword modifiers.

Modifier

Example

Description

exact form

`=cats`

Only match this exact form, needs `index_exact_words`

field start

`^hello`

Only match at the very start of (any) field

field end

`world$`

Only match at the very end of (any) field

IDF boost

`boost^1.23`

Multply keyword IDF by a given value when ranking

The operators are a bit more interesting!

Operator

Example

Description

brackets

`(one two)`

Group a subexpression

AND

`one two`

Match both args

OR

`one | two`

Match any arg

term-OR

`one || two`

Match any keyword, and reuse in-query position

NOT

`one -two`

Match 1st arg, but exclude matches of 2nd arg

NOT

`one !two`

Match 1st arg, but exclude matches of 2nd arg

MAYBE

`one MAYBE two`

Match 1st arg, but include 2nd arg when ranking

field limit

`@title one @body two`

Limit matching to a given field

fields limit

`@(title,body) test`

Limit matching to given fields

fields limit

`@!(phone,year) test`

Limit matching to all but given fields

fields limit

`@* test`

Reset any previous field limits

position limit

`@title[50] test`

Limit matching to N first positions in a field

phrase

`"one two"`

Match all keywords as an (exact) phrase

phrase

`"one * * four"`

Match all keywords as an (exact) phrase

proximity

`"one two"~3`

Match all keywords within a proximity window

quorum

`"uno due tre"/2`

Match any N out of all keywords

quorum

`"uno due tre"/0.7`

Match any given fraction of all keywords

BEFORE

`one << two`

Match args in this specific order only

NEAR

`one NEAR/3 "two three"`

Match args in any order within a given distance

SENTENCE

`one SENTENCE "two three"`

Match args in one sentence; needs `index_sp`

PARAGRAPH

`one PARAGRAPH two`

Match args in one paragraph; needs `index_sp`

ZONE

`ZONE:(h3,h4) one two`

Match in given zones only; needs `index_zones`

ZONESPAN

`ZONESPAN:(h3,h4) one two`

Match in contiguous spans only; needs `index_zones`

Now let’s discuss all these modifiers and operators in a bit more detail.

### Keyword modifiers

**Exact form** modifier is only applicable when morphology (ie. either stemming or lemmatizaion) is enabled. With morphology on, Sphinx searches for normalized keywords by default. This modifier lets you search for an exact original form. It requires `index_exact_words` setting to be enabled.

The syntax is `=` at the keyword start.

    =exact

For the sake of an example, assume that English stemming is enabled, ie. that the index was configured with `morphology = stem_en` setting. Also assume that we have these three sample documents:

    id, content
    1, run
    2, runs
    3, running

Without `index_exact_words`, only the normalized form, namely `run`, is stored into the index for every document. Even with the modifier, it is impossible to differentiate between them.

With `index_exact_words = 1`, both the normalized and original keyword forms are stored into the index. However, by default the keywords are also normalized when searching. So a query `runs` will get normalized to `run`, and will still match all 3 documents.

And finally, with `index_exact_words = 1` and with the exact form modifier, a query like `=runs` will be able to match just the original form, and return just the document #2.

For convenience, you can also apply this particular modifier to an entire phrase operator, and it will propagate down to all keywords.

    ="runs down the hills"
    "=runs =down =the =hills"

**Field start modifier** makes the keyword match if and only if it occurred at the very beginning of (any) full-text field. (Technically, it will only match postings with an in-field position of 1.)

The syntax is `^` at the keyword start, mimicked after regexps.

    ^fieldstart

**Field end modifier** makes the keyword match if and only if it occurred at the very end of (any) full-text field. (Technically, it will only match postings with a special internal “end-of-field” flag.)

The syntax is `$` at the keyword start, mimicked after regexps.

    fieldend$

**IDF boost modifier** lets you adjust the keyword IDF value (used for ranking), it multiples the IDF value by a given constant. That affects a number of ranking factors that build upon the IDF. That in turn also affects default ranking.

The syntax is `^` followed by a scale constant.

    boostme^1.23

### Boolean operators (brackets, AND, OR, NOT)

These let you implement grouping (with brackets) and classic boolean logic. The respective formal syntax is as follows:

- brackets: `(expr1)`
- AND: `expr1 expr2`
- OR: `expr1 | expr2`
- NOT: `-expr1` or `!expr1`

Where `expr1` and `expr2` are either keywords, or any other computable text query expressions. Here go a few query examples showing all of the operators.

    (shaken !stirred)
    "barack obama" (alaska | california | texas | "new york")
    one -(two | (three -four))

Nothing too exciting to see here. But still there are a few quirks worth a quick mention. Here they go, in no particular order.

**OR operator precedence is higher than AND.**

In other words, ORs take priority, they are evaluated first, ANDs are then evaluated on top of ORs. Thus, `looking for cat | dog | mouse` query is equivalent to `looking for (cat | dog | mouse)`, and _not_ `(looking for cat) | dog | mouse`.

**ANDs are implicit.**

There isn’t any explicit syntax for them in Sphinx. Just put two expressions right next to each other, and that’s it.

**No all-caps versions for AND/OR/NOT, those are valid keywords.**

So something like `rick AND morty` is equivalent to `rick and morty`, and both these queries require all 3 keywords to match, including that literal `and`.

Notice the difference in behavior between this, and, say, `rick MAYBE morty`, where the syntax for operator MAYBE is that all-caps keyword.

**Field and zone limits affect the entire (sub)expression.**

Meaning that `@title` limit in a `@title hello world` query applies to all keywords, not just a keyword or expression immediately after the limit operator. Both keywords in this example would need to match in the `title` field, not only the first `hello`. An explicit way to write this query, with an explicit field limit for every keyword, would be `(@title hello) (@title world)`.

**Brackets push and pop field and zone limits.**

For example, `(@title hello) world` query requires `hello` to be matched in `title` only. But that limit ends on a closing bracket, and `world` can then match anywhere in the document again. Therefore _this_ query is equivalent to something like `(@title hello) (@* world)`.

Even more curiously, but quite predictably, `@body (@title hello) world` query would in turn be equivalent to `(@title hello) (@body world)`. The first `@body` limit gets pushed on an opening bracket, and then restored on a closing one.

Sames rules apply to zones, see `ZONE` and `ZONESPAN` operators below.

**In-query positions in boolean operators are sequential.**

And while those do not affect _matching_ (aka text based filtering), they do noticeably affect _ranking_. For example, even if you splice a phrase with ORs, a rather important “phrase match degree” ranking factor (the one called ‘lcs’) does not change at all, even though matching changes quite a lot:

    mysql> select id, weight(), title from test1
      where match('@title little black dress');
    +--------+----------+--------------------+
    | id     | weight() | title              |
    +--------+----------+--------------------+
    | 334757 |     3582 | Little black dress |
    +--------+----------+--------------------+
    1 row in set (0.01 sec)

    mysql> select id, weight(), title from test1
      where match('@title little | black | dress');
    +--------+----------+------------------------+
    | id     | weight() | title                  |
    +--------+----------+------------------------+
    | 334757 |     3582 | Little black dress     |
    | 420209 |     2549 | Little Black Backpack. |
    ...

So in a sense, everything you construct using brackets and operators still looks like a single huge “phrase” (bag of words, really) to the ranking code. As if there were no brackets and no operators.

**Operator NOT is really operator ANDNOT.**

While a query like `-something` technically can be computed, more often than not such a query is just a programming error. And a potentially expensive one at that, because an implicit list of _all_ the documents in the index could be quite big. Here go a few examples.

    // correct query, computable at every level
    aaa -(bbb -(ccc ddd))

    // non-computable queries
    -aaa
    aaa | -bbb

(On a side note, that might also raise the philosophical question of ranking documents that contain zero matched keywords; thankfully, from an engineering perspective it would be extremely easy to brutally cut that Gordian knot by merely setting the weight to zero, too.)

For that reason, NOT operator requires something computable to its left. An isolated NOT will raise a query error. In case that you _absolutely_ must, you can append some special magic keyword (something like `__allmydocs`, to your taste) to all your documents when indexing. Two example non-computable queries just above would then become:

    (__allmydocs -aaa)
    aaa | (__allmydocs -bbb)

**Operator NOT only works at term start.**

In order to trigger, it must be preceded with a whitespace, or a bracket, or other clear keyword boundary. For instance, `cat-dog` is by default actually equivalent to merely `cat dog`, while `cat -dog` with a space does apply the operator NOT to `dog`.

### Phrase operator

Phrase operator uses the de-facto standard double quotes syntax and basically lets you search for an exact phrase, ie. several keywords in this exact order, without any gaps between them. For example.

    "mary had a little lamb"

Yep, boring. But of course there is a bit more even to this simple operator.

**Exact form modifier works on the entire operator.** Of course, any modifiers must work within a phrase, that’s what modifiers are all about. But with exact form modifiers there’s extra syntax sugar that lets you apply it to the entire phrase at once: `="runs down the hills"` form is a bit easier to write than `"=runs =down =the =hills"`.

**Standalone star “matches” any keyword.** Or rather, they skip that position when matching the phrase. Text queries do not really work with document texts. They work with just the specified keywords, and analyze their in-document and in-query positions. Now, a special star token within a phrase operator will not actually match anything, it will simply adjust the query position when parsing the query. So there will be no impact on search performance at all, but the phrase keyword positions will be shifted. For example.

    "mary had * * lamb"

**Stopwords “match” any keyword.** The very same logic applies to stopwords. Stopwords are not even stored in the index, so we have nothing to match. But even on stopwords, we still need adjust both the in-document positions when indexing, and in-query positions when matching.

This sometimes causes a little counter-intuitive and unexpected (but inevitable!) matching behavior. Consider the following set of documents:

    id, content
    1, Microsoft Office 2016
    2, we are using a lot of software from Microsoft in the office
    3, Microsoft opens another office in the UK

Assume that `in` and `the` are our only stopwords. What documents would be matched by the following two phrase queries?

1. `"microsoft office"`
2. `"microsoft in the office"`

Query #1 only matches document #1, no big surprise there. However, as we just discussed, query #2 is in fact equivalent to `"microsoft * * office"`, because of stopwords. And so it matches both documents #2 and #3.

### MAYBE operator

Operator MAYBE is occasionally needed for ranking. It takes two arbitrary expressions, and only requires the first one to match, but uses the (optional) matches of the second expression for ranking.

    expr1 MAYBE expr2

For instance, `rick MAYBE morty` query matches exactly the same documents as just `rick`, but with that extra MAYBE, documents that mention both `rick` and `morty` will get ranked higher.

Arbitrary expressions are supported, so this is also valid:

    rick MAYBE morty MAYBE (season (one || two || three) -four')

### Term-OR operator

Term-OR operator (double pipe) essentially lets you specify “properly ranked” per-keyword synonyms at query time.

Matching-wise, it just does regular boolean OR over several keywords, but ranking-wise (and unlike the regular OR operator), it does _not_ increment their in-query positions. That keeps any positional ranking factors intact.

Naturally, it only accepts individual keywords, you can not term-OR a keyword and a phrase or any other expression. Also, term-OR is currently not supported within phrase or proximity operators, though that is an interesting possibility.

It should be easiest to illustrate it with a simple example. Assume we are still searching for that little black dress, as we did in our example on the regular OR operator.

    mysql> select id, weight(), title from rt
      where match('little black dress');
    +------+----------+-----------------------------------------------+
    | id   | weight() | title                                         |
    +------+----------+-----------------------------------------------+
    |    1 |     3566 | little black dress                            |
    |    3 |     1566 | huge black/charcoal dress with a little white |
    +------+----------+-----------------------------------------------+
    2 rows in set (0.00 sec)

So far so good. But looks like `charcoal` is a synonym that we could use here. Let’s try to use it using the regular OR operator.

    mysql> select id, weight(), title from rt
      where match('little black|charcoal dress');
    +------+----------+-----------------------------------------------+
    | id   | weight() | title                                         |
    +------+----------+-----------------------------------------------+
    |    3 |     3632 | huge black/charcoal dress with a little white |
    |    1 |     2566 | little black dress                            |
    |    2 |     2566 | little charcoal dress                         |
    +------+----------+-----------------------------------------------+
    3 rows in set (0.00 sec)

Oops, what just happened? We now also match document #2, which is good, but why is the document #3 ranked so high all of a sudden?

That’s because with regular ORs ranking would, basically, look for the entire query as if without any operators, ie. the ideal phrase match would be not just `"little black dress"`, but the entire `"little black charcoal dress"` query with all special operators removed.

There is no such a “perfect” 4 keyword full phrase match in our small test database. (If there was, it would get top rank.) From the phrase ranking point of view, the next kinda-best thing to it is the `"black/charcoal dress"` part, where a 3 keyword subphrase matches the query. And that’s why it gets ranked higher that `"little black dress"`, where the longest common subphrase between the document and the query is `"little black"`, only 2 keywords long, not 3.

But that’s not what we wanted in this case at all; we just wanted to introduce a synonym for `black`, rather than break ranking! And that’s exactly what term-OR operator is for.

    mysql> select id, weight(), title from rt
      where match('little black||charcoal dress');
    +------+----------+-----------------------------------------------+
    | id   | weight() | title                                         |
    +------+----------+-----------------------------------------------+
    |    1 |     3566 | little black dress                            |
    |    2 |     3566 | little charcoal dress                         |
    |    3 |     2632 | huge black/charcoal dress with a little white |
    +------+----------+-----------------------------------------------+
    3 rows in set (0.00 sec)

Good, ranking is back to expected. Both the original exact match `"little black dress"` and synonymical `"little charcoal dress"` are now at the top again, because of a perfect phrase match (which is favored by the default ranker).

Note that while all the examples above revolved around a single positional factor `lcs` (which is used in the default ranker), there are more positional factors than just that. See the section on [Ranking factors](http://sphinxsearch.com/docs/sphinx3.html#ranking-factors) for more details.

### Field and position limit operator

Field limit operator limits matching of the subsequent expressions to a given field, or a set of fields. Field names must exist in the index, otherwise the query will fail with an error.

There are several syntax forms available.

1. `@field` limits matching to a single given field. This is the simplest form. `@(field)` is also valid.
2. `@(f1,f2,f3)` limits matching to multiple given fields. Note that the match might happen just partially in one of the fields. For example, `@(title,body) hello world` does _not_ require that both keywords match in the very same field! Document like `{"id":123, "title":"hello", "body":"world"}` (pardon my JSON) does match this query.
3. `@!(f1,f2,f3)` limits matching to all the fields _except_ given ones. This can be useful to avoid matching end-user queries against some internal system fields, for one. `@!f1` is also valid syntax in case you want to skip just the one field.
4. `@*` syntax resets any previous limits, and re-enables matching all fields.

In addition, all forms except `@*` can be followed by an optional `[N]` clause, which limits the matching to `N` first tokens (keywords) within a field. All of the examples below are valid:

- `@title[50] test`
- `@(title,body)[50] test`
- `@!title[50] test`

To reiterate, field limits are “contained” by brackets, or more formally, any current limits are stored on an opening bracket, and restored on a closing one.

When in doubt, use `SHOW PLAN` to figure out what limits are actually used:

    mysql> set profiling=1;
      select * from rt where match('(@title[50] hello) world') limit 0;
      show plan \G
    ...

    *************************** 1. row ***************************
    Variable: transformed_tree
       Value: AND(
      AND(fields=(title), max_field_pos=50, KEYWORD(hello, querypos=1)),
      AND(KEYWORD(world, querypos=2)))
    1 row in set (0.00 sec)

We can see that `@title` limit was only applied to `hello`, and reset back to matching all fields (and positions) on a closing bracket, as expected.

### Proximity and NEAR operators

**Proximity operator** matches all the specified keywords, in any order, and allows for a number of gaps between those keywords. The formal syntax is as follows:

    "keyword1 keyword2 ... keywordM"~N

Where `N` has a little weird meaning. It is the allowed number of gaps (other keywords) that can occur between those `M` specified keywords, but additionally incremented by 1.

For example, consider a document that reads `"Mary had a little lamb whose fleece was white as snow"`, and consider two queries: `"lamb fleece mary"~4`, and `"lamb fleece mary"~5`. We have exactly 4 extra words between `mary`, `lamb`, and `fleece`, namely those 4 are `had`, `a`, `little`, and `whose`. This means that the first query with `N = 4` will _not_ match, because with `N = 4` the proximity operator actually allows for 3 gaps only, not 4. And thus the second example query will match, as with `N = 5` it allows for 4 gaps (plus 1 permutation).

**NEAR operator** is a generalized version of proximity operator. Its syntax is:

    expr1 NEAR/N expr2

Where `N` has the same meaning as in the proximity operator, the number of allowed gaps plus one. But with NEAR we can use arbitrary expressions, not just individual keywords.

    (binary | "red black") NEAR/2 tree

Left and right expressions can still match in any order. For example, a query `progress NEAR/2 bar` would match both these documents:

1. `progress bar`
2. `a bar called Progress`

NEAR is left associative, meaning that `arg1 NEAR/X arg2 NEAR/Y arg3` will be evaluated as `(arg1 NEAR/X arg2) NEAR/Y arg3`. It has the same (lowest) precedence as BEFORE.

Note that while with just 2 keywords proximity and NEAR operators are identical (eg. `"one two"~N` and `one NEAR/N two` should behave exactly the same), with more keywords that is _not_ the case.

Because when you stack multiple keywords with NEAR, then upto `N - 1` gaps are allowed per _each_ keyword in the stack. Consider this example with two stacked NEAR operators: `one NEAR/3 two NEAR/3 three`. It allows for upto 2 gaps between `one` and `two`, and then for 2 more gaps between `two` and three. That’s less restrictive than the proximity operator with the same N (`"one two three"~3`), as the proximity operator will only allow 2 gaps total. So a document with `one aaa two bbb ccc three` text will match the NEAR query, but _not_ the proximity query.

And vice versa, what if we bump the limit in proximity to match the total limit allowed by all NEARs? We get `"one two three"~5` (4 gaps allowed, plus that magic 1), so that anything that matches the NEARs variant would also match the proximity variant. But now a document `one two aaa bbb ccc ddd three` ceases to match the NEARs, because the gap between `two` and `three` is too big. And now the proximity operator becomes less restrictive.

Bottom line is, the proximity operator and a stack of NEARs are _not_ really interchangeable, they match a bit different things.

### Quorum operator

Quorum matching operator essentially lets you perform fuzzy matching. It’s less strict than matching all the argument keywords. It will match all documents with at least N keywords present out of M total specified. Just like with proximity (or with AND), those N can occur in any order.

    "keyword1 keyword2 ... keywordM"/N
    "keyword1 keyword2 ... keywordM"/fraction

For a specific example, `"the world is a wonderful place"/3` will match all documents that have any 3 of the specified words, or more.

Naturally, N must be less or equal to M. Also, M must be anywhere from 1 to 256 keywords, inclusive. (Even though quorum with just 1 keyword makes little sense, that is allowed.)

Fraction must be from 0.0 to 1.0, more details below.

Quorum with `N = 1` is effectively equivalent to a stack of ORs, and can be used as syntax sugar to replace that. For instance, these two queries are equivalent:

    red | orange | yellow | green | blue | indigo | violet
    "red orange yellow green blue indigo violet"/1

Instead of an absolute number `N`, you can also specify a fraction, a floating point number between 0.0 and 1.0. In this case Sphinx will automatically compute `N` based on the number of keywords in the operator. This is useful when you don’t or can’t know the keyword count in advance. The example above can be rewritten as `"the world is a wonderful place"/0.5`, meaning that we want to match at least 50% of the keywords. As there are 6 words in this query, the autocomputed match threshold would also be 3.

Fractional threshold is rounded up. So with 3 keywords and a fraction of 0.5 we would get a final threshold of 2 keywords, as `3 * 0.5 = 1.5` rounds up as 2. There’s also a lower safety limit of 1 keyword, as matching zero keywords makes zero sense.

When the quorum threshold is too restrictive (ie. when N is greater than M), the operator gets automatically replaced with an AND operator. The same fallback happens when there are more than 256 keywords.

### Strict order operator (BEFORE)

This operator enforces a strict “left to right” order (ie. the query order) on its arguments. The arguments can be arbitrary expressions. The syntax is `<<`, and there is no all-caps version.

    expr1 << expr2

For instance, `black << cat` query will match a `black and white cat` document but _not_ a `that cat was black` document.

Strict order operator has the lowest priority, same as NEAR operator.

It can be applied both to just keywords and more complex expressions, so the following is a valid query:

    (bag of words) << "exact phrase" << red|green|blue

### SENTENCE and PARAGRAPH operators

These operators match the document when both their arguments are within the same sentence or the same paragraph of text, respectively. The arguments can be either keywords, or phrases, or the instances of the same operator. (That is, you can stack several SENTENCE operators or PARAGRAPH operators. Mixing them is however not supported.) Here are a few examples:

    one SENTENCE two
    one SENTENCE "two three"
    one SENTENCE "two three" SENTENCE four

The order of the arguments within the sentence or paragraph does not matter.

These operators require indexes built with [`index_sp`](http://sphinxsearch.com/docs/sphinx2.html#conf-index-sp) setting (sentence and paragraph indexing feature) enabled, and revert to a mere AND otherwise. You can refer to documentation on `index_sp` for additional details on what’s considered a sentence or a paragraph.

### ZONE and ZONESPAN operators

Zone limit operator is a bit similar to field limit operator, but restricts matching to a given in-field zone (or a list of zones). The following syntax variants are supported:

    ZONE:h1 test
    ZONE:(h2,h3) test
    ZONESPAN:h1 test
    ZONESPAN:(h2,h3) test

Zones are named regions within a field. Essentially they map to HTML (or XML) markup. Everything between `<h1>` and `</h1>` is in a zone called `h1` and could be matched by that `ZONE:h1 test` query.

Note that ZONE and ZONESPAN limits will get reset not only on a closing bracket, or on the next zone limit operator, but on a next _field_ limit operator too! So make sure to specify zones explicitly for every field. Also, this makes operator `@*` a _full_ reset, ie. it should reset both field and zone limits.

Zone limits require indexes built with zones support (see documentation on [`index_zones`](http://sphinxsearch.com/docs/sphinx2.html#conf-index-zones) for a bit more details).

The difference between ZONE and ZONESPAN limit is that the former allows its arguments to match in multiple disconnected spans of the same zone, and the latter requires that all matching occurs within a single contiguous span.

For instance, `(ZONE:th hello world)` query _will_ match this example document.

    <th>Table 1. Local awareness of Hello Kitty brand.</th>
    .. some table data goes here ..
    <th>Table 2. World-wide brand awareness.</th>

In this example we have 2 spans of `th` zone, `hello` will match in the first one, and `world` in the second one. So in a sense ZONE works on a concatenation of all the zone spans.

And if you need to further limit matching to any of the individual contiguous spans, you should use the ZONESPAN operator. `(ZONESPAN:th hello world)` query does _not_ match the document above. `(ZONESPAN:th hello kitty)` however does!

## Searching: geosearches

Efficient geosearches are possible with Sphinx, and the related features are:

- `GEODIST()` function that computes a distance between two geopoints
- `CONTAINS()` function that checks if a geopoint is inside a geopolygon
- [attribute indexes](http://sphinxsearch.com/docs/sphinx3.html#using-attribute-indexes) that are used for fast, early distance checks

**Attribute indexes for geosearches.**

When you create indexes on your latitude and longitude columns (and you should), query optimizer can utilize those in a few important `GEODIST()` usecases:

1. Single constant anchor case:

    SELECT GEODIST(lat,lon,$lat,$lon) dist ...
        WHERE dist <= $radius

2. Multiple constant anchors case:

    SELECT
        GEODIST(lat,lon,$lat1,$lon1) dist1,
        GEODIST(lat,lon,$lat2,$lon2) dist2,
        GEODIST(lat,lon,$lat3,$lon3) dist3,
        ...,
        (dist1 < $radius1 OR dist2 < $radius2 OR dist3 < $radius3 ...) ok
    WHERE ok=1

These cases are known to the query optimizer, and once it detects them, it can choose to perform an approximate attribute index read (or reads) first, instead of scanning the entire index. When the quick approximate read is selective enough, which frequently happens with small enough search distances, savings can be huge.

Case #1 handles your typical “give me everything close enough to a certain point” search. When the anchor point and radius are all constant, Sphinx will automatically precompute a bounding box that fully covers a “circle” with a required radius around that anchor point, ie. find some two internal min/max values for latitude and longitude, respectively. It will then quickly check attribute indexes statistics, and if the bounding box condition is selective enough, it will switch to attribute index reads instead of a full scan.

Here’s a working query example:

    SELECT *, GEODIST(lat,lon,55.7540,37.6206,{in=deg,out=km}) AS dist
      FROM myindex WHERE dist<=100

Case #2 handles multi-anchor search, ie. “give me documents that are either close enough to point number 1, or to point number 2, etc”. The base approach is exactly the same, but _multiple_ boundboxes are generated, multiple index reads are performed, and their results are all merged together.

Here’s another example:

    SELECT id,
       GEODIST(lat, lon, 55.777, 37.585, {in=deg,out=km}) d1,
       GEODIST(lat, lon, 55.569, 37.576, {in=deg,out=km}) d2,
       geodist(lat, lon, 56.860, 35.912, {in=deg,out=km}) d3,
       (d1<1 OR d2<1 OR d3<1) ok
    FROM myindex WHERE ok=1

Note that if we reformulate the queries a little, and the optimizer does not recognize the eligible cases any more, the optimization will _not_ trigger. For example:

    SELECT *, 2*GEODIST(lat,lon,55.7540,37.6206,{in=deg,out=km})<=100 AS flag
      FROM myindex WHERE flag=1

Obviously, “the boundbox optimization” is actually still feasible in this case, but the optimizer will not recognize that and switch to full scan.

To ensure whether these optimizations are working for you, use `EXPLAIN` on your query. Also, make sure the radius small enough when doing those checks.

Another interesting bit is that sometimes optimizer can quite _properly_ choose to only use one index instead of two, or avoid using the indexes at all.

Say, what if our radius covers the entire country? All our documents will be within the boundbox anyway, and simple full scan will indeed be faster. That’s why you should use some “small enough” test radius with `EXPLAIN`.

Or say, what if we have another, super-selective `AND id=1234` condition in our query? Doing index reads will be just as extraneous, the optimizer will choose to perform a lookup by `id` instead.

## Searching: vector searches

You can implement vector searches with Sphinx and there are several different features intended for that, namely:

- fixed array attributes, eg. `rt_attr_int8_array = vec1[128]`
- JSON array attributes, eg. `{"vec2": int8[1,2,3,4]}`
- [`DOT()` function](http://sphinxsearch.com/docs/sphinx3.html#dot-function) to compute dot products
- [`FVEC()` function](http://sphinxsearch.com/docs/sphinx3.html#fvec-function) to specify vector constants

Let’s see how all these parts connect together.

**First, storage.** You can store your per-document vectors using any of the following options:

- fixed-size fixed-type arrays, ie. `XXX_attr_YYY_array` directive
- JSON arrays with implicit types, ie. regular `[1,2,3,4]` values in JSON
- JSON arrays with explicit types, ie. `int8[1,2,3,4]` or `float[1,2,3,4]` syntax extensions

Fixed arrays are the fastest to access, but not flexible at all. Also, they require some RAM per every document. For instance, a fixed array with 32 floats (`rt_attr_float_array = test1[32]`) will consume 128 bytes per _every_ row, whether or not it contains any actual data (and arrays without any explicit data will be filled with zeroes).

JSON arrays are slower to access, and consume a bit more memory per row, but that memory is only consumed per _used_ row. Meaning that when your vectors are defined sparsely (for, say, just 1M documents out of the entire 10M collection), then it might make sense to use JSON anyway to save some RAM.

JSON arrays are also “mixed” by default, that is, can contain values with arbitrary different types. With vector searches however you would normally want to use optimized arrays, with a single type attached to _all_ values. Sphinx can auto-detect integer arrays in JSON, with values that fit into either int32 or int64 range, and store and later process them efficiently. However, to enforce either int8 or float type on a JSON array, you have to _explicitly_ use our JSON syntax extensions.

To store an array of `float` values in JSON, you have to:

- either specify `float` type in each value with `1.234f` syntax (because by default `1.234` gets a `double` type in JSON), eg: `[1.0f, 2.0f, 3.0f]`
- or specify array type with `float[...]` syntax, eg: `float[1,2,3]`

To store an array of `int8` values (ie. from -128 to 127 inclusive) in JSON, the only option is to:

- specify array type with `int8[...]` syntax, eg: `int8[1,2,3]`

In both these cases, we require an explicit type to differentiate between the two possible options (`float` vs `double`, or `int8` vs `int` case), and by default, we choose to use higher precision rather than save space.

**Second, calculations.** The workhorse here is the `DOT()` function that computes a dot product between the two vector arguments, ie. a sum of the products of the corresponding vector components.

The most frequent usecase is, of course, computing a `DOT()` between some per-document array (stored either as an attribute or in JSON) and a constant. The latter should be specifed with `FVEC()`:

    SELECT id, DOT(vec1, FVEC(1,2,3,4)) FROM mydocuments
    SELECT id, DOT(json.vec2, FVEC(1,2,3,4)) FROM mydocuments

Note that `DOT()` internally optimizes its execution depending on the actual argument types (ie. float vectors, or integer vectors, etc). That is why the two following queries perform very differently:

    mysql> SELECT id, DOT(vec1, FVEC(1,2,3,4,...)) d
      FROM mydocuments ORDER BY d DESC LIMIT 3;
    ...
    3 rows in set (0.047 sec)

    mysql> SELECT id, DOT(vec1, FVEC(1.0,2,3,4,...)) d
      FROM mydocuments ORDER BY d DESC LIMIT 3;
    ...
    3 rows in set (0.073 sec)

In this example, `vec1` is an integer array, and we `DOT()` it against either an integer constant vector, or a float constant vector. Obviously, int-by-int vs int-by-float multiplications are a bit different, and hence the performance difference.

## Ranking: factors

Sphinx lets you specify custom ranking formulas for `weight()` calculations, and tailor text-based relevance ranking for your needs. For instance:

    SELECT *, WEIGHT() FROM myindex WHERE MATCH('hello world')
    OPTION ranker=expr('sum(lcs)*1000+bm15')

This mechanism is called the **expression ranker** and its ranking formulas (expressions) can access a few more special variables, called ranking factors, than a regular expression. (Of course, all the per-document attributes and all the math and other functions are still accessible to these formulas, too.)

**Ranking factors (aka ranking signals)** are, basically, a bunch of different values computed for every document (or even field), based on the current search query. They essentially describe various aspects of the specific document match, and so they are used as input variables in a ranking formula, or a ML model.

There are three types (or levels) of factors, that determine when exactly some given factor can and will be computed:

- **query factors**: values that only depend on the search query, but not the document, like `query_word_count`;
- **document factors**: values that depend on both the query _and_ the matched document, like `doc_word_count` or `bm15`;
- **field factors**: values that depend on both the query _and_ the matched full-text field, like `word_count` or `lcs`.

**Query factors** are naturally computed just once at the query start, and from there they stay constant. Those are usually simple things, like a number of unique keywords in the query. You can use them anywhere in the ranking formula.

**Document factors** additionally depend on the document text, and so they get computed for every matched document. You can use them anywhere in the ranking formula, too. Of these, a few variants of the classic `bm25()` function are arguably the most important for relevance ranking.

Finally, **field factors** are even more granular, they get computed for every single field. And thus they then have to be aggregated into a singular value by some **factor aggregation function** (as of v.3.2, the supported functions are either `SUM()` or `TOP()`).

And before we discuss every specific factor in a bit more details, here goes the obligatory **factors cheat sheet**.

- **Hits** in Sphinx == postings in IR == formally “a number of (a certain type of) matching keyword occurrences in the current field”

Name

Level

Type

Summary

has_digit_words

query

int

number of `has_digit` words that contain `[0-9]` chars (but may also contain other chars)

is_latin_words

query

int

number of `is_latin` words, ie. words with `[a-zA-Z]` chars only

is_noun_words

query

int

number of `is_noun` words, ie. tagged as nouns (by the lemmatizer)

is_number_words

query

int

number of `is_number` words, ie. integers with `[0-9]` chars only

max_lcs

query

int

maximum possible LCS value for the current query

query_word_count

query

int

number of unique inclusive keywords in a query

bm15

doc

int

quick estimate of `BM25(1.2, 0)` without query syntax support

bm25a(k1, b)

doc

int

precise `BM25()` value with configurable `K1`, `B` constants and syntax support

bm25f(k1, b, …)

doc

int

precise `BM25F()` value with extra configurable field weights

doc_word_count

doc

int

number of unique keywords matched in the document

field_mask

doc

int

bit mask of the matched fields

atc

field

float

Aggregate Term Closeness, `log(1+sum(idf1*idf2*pow(distance, -1.75))` over “best” term pairs

exact_field_hit

field

bool

whether field is fully covered by the query, in the query term order

exact_hit

field

bool

whether query == field

exact_order

field

bool

whether all query keywords were a) matched and b) in query order

full_field_hit

field

bool

whether field is fully covered by the query, in arbitrary term order

has_digit_hits

field

int

number of `has_digit` keyword hits

hit_count

field

int

total number of any-keyword hits

is_latin_hits

field

int

number of `is_latin` keyword hits

is_noun_hits

field

int

number of `is_noun` keyword hits

is_number_hits

field

int

number of `is_number` keyword hits

lccs

field

int

Longest Common Contiguous Subsequence between query and document, in words

lcs

field

int

Longest Common Subsequence between query and document, in words

max_idf

field

float

`max(idf)` over keywords matched in this field

max_window_hits(n)

field

int

`max(window_hit_count)` computed over all N-word windows in the current field

min_best_span_pos

field

int

first maximum LCS span position, in words, 1-based

min_gaps

field

int

min number of gaps between the matched keywords over the matching spans

min_hit_pos

field

int

first matched occurrence position, in words, 1-based

min_idf

field

float

`min(idf)` over keywords matched in this field

sum_idf

field

float

`sum(idf)` over keywords matched in this field

sum_idf_boost

field

float

`sum(idf_boost)` over keywords matched in this field

tf_idf

field

float

`sum(tf*idf)` over matched keywords, ie. `sum(idf)` over all occurrences

user_weight

field

int

user-specified field weight (via `OPTION field_weights`)

wlccs

field

float

Weighted LCCS, `sum(idf)` over contiguous keyword spans

word_count

field

int

number of unique keyword matched in this field

### Factor aggregation functions

Formally, a (field) factor aggregation function is a single argument function that takes an expression with field-level factors, iterates it over all the matched fields, and computes the final result over the individual per-field values.

Currently supported aggregation functions are:

- `SUM()`, sums the argument expression over all matched fields. For instance, `sum(1)` should return a number of matched fields.
- `TOP()`, returns the greatest value of the argument over all matched fields. For instance, `top(max_idf)` should return a maximum per-keyword IDF over the entire document.

Naturally, these are only needed over expressions with field-level factors, query-level and document-level factors can be used in the formulas “as is”.

### Keyword flags

When searching and ranking, Sphinx classifies every query keyword with regards to a few classes of interest. That is, it flags a keyword with a “noun” class when the keyword is a (known) noun, or flags it with a “number” class when it is an integer, etc.

At the moment we identify 4 keyword classes and assign the respective flags. Those 4 flags in turn generate 8 ranking factors, 4 query-level per-flag keyword counts, and 4 field-level per-class hit counts. The flags are described in a bit more detail just below.

It’s important to understand that all the flags are essentially assigned at _query_ parsing time, without looking into any actual index _data_ (as opposed to tokenization and morphology settings). Also, query processing rules apply. Meaning that the valid keyword modifiers are effectively stripped before assigning the flags.

#### `has_digit` flag

Keyword is flagged as `has_digit` when there is at least one digit character, ie. from `[0-9]` range, in that keyword.

Other characters are allowed, meaning that `l33t` is a `has_digit` keyword.

But they are not required, and thus, any `is_number` keyword is by definition a `has_digit` keyword.

#### `is_latin` flag

Keyword is flagged as `is_latin` when it completely consists of Latin letters, ie. any of the `[a-zA-Z]` characters. No other characters are allowed.

For instance, `hello` is flagged as `is_latin`, but `l33t` is _not_, because of the digits.

Also note that wildcards like `abc*` are _not_ flagged as `is_latin`, even if all the actual expansions are latin-only. Technically, query keyword flagging only looks at the query itself, and not the index data, and can not know anything about the actual expansions yet. (And even if it did, then inserting a new row with a new expansion could suddenly break the `is_latin` property.)

At the same time, as query keyword modifiers like `^abc` or `=abc` still get properly processed, these keywords _are_ flagged as `is_latin` alright.

#### `is_noun` flag

Keyword is flagged as `is_noun` when (a) there is at least one lemmatizer enabled for the index, and (b) that lemmatizer classifies that standalone keyword as a noun.

For example, with `morphology = lemmatize_en` configured in our example index, we get the following:

    mysql> CALL KEYWORDS('deadly mortal sin', 'en', 1 AS stats);
    +------+-----------+------------+------+------+-----------+------------+----------------+----------+---------+-----------+-----------+
    | qpos | tokenized | normalized | docs | hits | plain_idf | global_idf | has_global_idf | is_latin | is_noun | is_number | has_digit |
    +------+-----------+------------+------+------+-----------+------------+----------------+----------+---------+-----------+-----------+
    | 1    | deadly    | deadly     | 0    | 0    | 0.000000  | 0.000000   | 0              | 1        | 0       | 0         | 0         |
    | 2    | mortal    | mortal     | 0    | 0    | 0.000000  | 0.000000   | 0              | 1        | 1       | 0         | 0         |
    | 3    | sin       | sin        | 0    | 0    | 0.000000  | 0.000000   | 0              | 1        | 1       | 0         | 0         |
    +------+-----------+------------+------+------+-----------+------------+----------------+----------+---------+-----------+-----------+
    3 rows in set (0.00 sec)

However, as you can see from this very example, `is_noun` POS tagging is not completely precise.

For now it works on individual words rather than contexts. So even though in _this_ particular query context we could technically guess that “mortal” is not a noun, in general it sometimes is. Hence the `is_noun` flags in this example are 0/1/1, though ideally they would be 0/0/1 respectively.

Also, at the moment the tagger prefers to overtag. That is, when “in doubt”, ie. when the lemmatizer reports that a given wordform can either be a noun or not, we do not (yet) analyze the probabilities, and just always set the flag.

Another tricky bit is the handling of non-dictionary forms. As of v.3.2 the lemmatizer reports all such predictions as nouns.

So use with care; this can be a noisy signal.

#### `is_number` flag

Keyword is flagged as `is_number` when _all_ its characters are digits from the `[0-9]` range. Other characters are not allowed.

So, for example, `123` will be flagged `is_number`, but neither `0.123` nor `0x123` will be flagged.

To nitpick on this particular example a bit more, note that `.` does not even get parsed as a character by default. So with the default `charset_table` that query text will not even produce a single keyword. Instead, by default it gets tokenized as two tokens (keywords), `0` and `123`, and _those_ tokens in turn _are_ flagged `is_number`.

### Query-level ranking factors

These are perhaps the simplest factors. They are entirely independent from the documents being ranked; they only describe the query. So they only get computed once, at the very start of query processing.

#### has_digit_words

Query-level, a number of unique `has_digit` keywords in the query. Duplicates should only be accounted once.

#### is_latin_words

Query-level, a number of unique `is_latin` keywords in the query. Duplicates should only be accounted once.

#### is_noun_words

Query-level, a number of unique `is_noun` keywords in the query. Duplicates should only be accounted once.

#### is_number_words

Query-level, a number of unique `is_number` keywords in the query. Duplicates should only be accounted once.

#### max_lcs

Query-level, maximum possible value that the `sum(lcs*user_weight)` expression can take. This can be useful for weight boost scaling. For instance, (legacy) `MATCHANY` ranker formula uses this factor to _guarantee_ that a full phrase match in _any_ individual field ranks higher than any combination of partial matches in all fields.

#### query_word_count

Query-level, a number of unique and inclusive keywords in a query. “Inclusive” means that it’s additionally adjusted for a number of excluded keywords. For example, both `one one one one` and `(one !two)` queries should assign a value of 1 to this factor, because there is just one unique non-excluded keyword.

### Document-level ranking factors

These are a few factors that “look” at both the query and the (entire) matching document being ranked. The most useful among these are several variants of the classic BM-family factors (as in Okapi BM25).

#### bm15

Document-level, a quick estimate of a classic `BM15(1.2)` value. It is computed without keyword occurrence filtering (ie. over all the term postings rather than just the matched ones). Also, it ignores the document and fields lengths.

For example, if you search for an exact phrase like `"foo bar"`, and both `foo` and `bar` keywords occur 10 times each in the document, but the _phrase_ only occurs once, then this `bm15` estimate will still use 10 as TF (Term Frequency) values for both these keywords, ie. account all the term occurrences (postings), instead of “accounting” just 1 actual matching posting.

So `bm15` uses pre-computed document TFs, rather that computing actual matched TFs on the fly. By design, that makes zero difference all when running a simple bag-of-words query against the entire document. However, once you start using pretty much _any_ query syntax, the differences become obvious.

To discuss one, what if you limit all your searches to a single field with, and the query is `@title foo bar`? Should the weights really depend on contents of any other fields, as we clearly intended to limit our searches to titles? They should not. However, with the `bm15` approximation they will. But this really is just a performance vs quality tradeoff.

Last but not least, this factor was not-quite-correctly named `bm25` for quite a while, until v.3.0.2. (It can be argued that in a way it did compute the BM25 value, for a very specific `k1 = 1.2` and `b = 0` case. But come on. There is a special name for that `b = 0` family of cases, and it is `bm15`.)

#### bm25a()

Document-level, parametrized, computes a value of classic `BM25(k1,b)` function with the two given (required) parameters. For example:

    SELECT ... OPTION ranker=expr('10000*bm25a(2.0, 0.7)')

Unlike `bm15`, this factor only account the _matching_ occurrences (postings) when computing TFs. It also requires `index_field_lengths = 1` setting to be on, in order to compute the current and average document lengths (which is in turn required by BM25 function with non-zero `b` parameters).

It is called `bm25a` only because `bm25` was initially taken (mistakenly) by that `BM25(1.2, 0)` value estimate that we now (properly) call `bm15`; no other hidden meaning in that `a` suffix.

#### bm25f()

Document-level, parametrized, computes a value of an extended `BM25F(k1,b)` function with the two given (required) parameters, and an extra set of named per-field weights. For example:

    SELECT ... OPTION ranker=expr('10000*bm25f(2.0, 0.7, {title = 3})')

Unlike `bm15`, this factor only account the _matching_ occurrences (postings) when computing TFs. It also requires `index_field_lengths = 1` setting to be on.

BM25F extension lets you assign bigger weights to certain fields. Internally those weights will simply pre-scale the TFs before plugging them into the original BM25 formula. For an original TR, see [Zaragoza et al (1994), “Microsoft Cambridge at TREC-13: Web and HARD tracks”](https://trec.nist.gov/pubs/trec13/papers/microsoft-cambridge.web.hard.pdf) paper.

#### doc_word_count

Document-level, a number of unique keywords matched in the entire document.

#### field_mask

Document-level, a 32-bit mask of matched fields. Fields with numbers 33 and up are ignored in this mask.

### Field-level ranking factors

Generally, a field-level factor is just some numeric value computed by the ranking engine for every matched in-document text field, with regards to the current query, describing this or this aspect of the actual match.

As a query can match multiple fields, but the final weight needs to be a single value, these per-field values need to be folded into a single one. Meaning that, unlike query-level and document-level factors, you can’t use them directly in your ranking formulas:

    mysql> SELECT id, weight() FROM test1 WHERE MATCH('hello world')
    OPTION ranker=expr('lcs');
     
    ERROR 1064 (42000): index 'test1': field factors must only
    occur within field aggregates in a ranking expression

The correct syntax should use one of the aggregation functions. Multiple different aggregations are allowed:

    mysql> SELECT id, weight() FROM test1 WHERE MATCH('hello world')
    OPTION ranker=expr('sum(lcs) + top(max_idf) * 1000');

Now let’s discuss the individual factors in a bit more detail.

#### atc

Field-level, Aggregate Term Closeness. This is a proximity based measure that grows higher when the document contains more groups of more closely located and more important (rare) query keywords.

**WARNING:** you should use ATC with `OPTION idf='plain,tfidf_unnormalized'`; otherwise you could get rather unexpected results.

ATC basically works as follows. For every keyword _occurrence_ in the document, we compute the so called _term closeness_. For that, we examine all the other closest occurrences of all the query keywords (keyword itself included too), both to the left and to the right of the subject occurrence. We then compute a distance dampening coefficient as `k = pow(distance, -1.75)` for all those occurrences, and sum the dampened IDFs. Thus for every occurrence of every keyword, we get a “closeness” value that describes the “neighbors” of that occurrence. We then multiply those per-occurrence closenesses by their respective subject keyword IDF, sum them all, and finally, compute a logarithm of that sum.

Or in other words, we process the best (closest) matched keyword pairs in the document, and compute pairwise “closenesses” as the product of their IDFs scaled by the distance coefficient:

    pair_tc = idf(pair_word1) * idf(pair_word2) * pow(pair_distance, -1.75)

We then sum such closenesses, and compute the final, log-dampened ATC value:

    atc = log(1 + sum(pair_tc))

Note that this final dampening logarithm is exactly the reason you should use `OPTION idf=plain`, because without it, the expression inside the `log()` could be negative.

Having closer keyword occurrences actually contributes _much_ more to ATC than having more frequent keywords. Indeed, when the keywords are right next to each other, we get `distance = 1` and `k = 1`; and when there is only one extra word between them, we get `distance = 2` and `k = 0.297`; and with two extra words in-between, we get `distance = 3` and `k = 0.146`, and so on.

At the same time IDF attenuates somewhat slower. For example, in a 1 million document collection, the IDF values for 3 example keywords that are found in 10, 100, and 1000 documents would be 0.833, 0.667, and 0.500, respectively.

So a keyword pair with two rather rare keywords that occur in just 10 documents each but with 2 other words in between would yield `pair_tc = 0.101` and thus just barely outweigh a pair with a 100-doc and a 1000-doc keyword with 1 other word between them and `pair_tc = 0.099`.

Moreover, a pair of two _unique_, 1-document keywords with ideal IDFs, and with just 3 words between them would fetch a `pair_tc = 0.088` and lose to a pair of two 1000-doc keywords located right next to each other, with a `pair_tc = 0.25`.

So, basically, while ATC does combine both keyword frequency and proximity, it is still heavily favoring the proximity.

#### exact_field_hit

Field-level, boolean, whether the current field was (seemingly) fully covered by the query, and in the right (query) term order, too.

This flag should be set when the field is basically either “equal” to the entire query, or equal to a query with a few terms thrown away. Note that term order matters, and it must match, too.

For example, if our query is `one two three`, then either `one two three`, or just `one three`, or `two three` should all have `exact_field_hit = 1`, because in these examples all the _field_ keywords are matched by the query, and they are in the right order. However, `three one` should get `exact_field_hit = 0`, because of the wrong (non-query) term order. And then if we throw in any extra terms, `one four three` field should also get `exact_field_hit = 0`, because `four` was not matched by the query, ie. this field is not covered fully.

Also, beware that stopwords and other text processing tools might “break” this factor.

For example, when the field is `one stop three`, where `stop` is a stopword, we would still get 0 instead of 1, even though intuitively it should be ignored, and the field should be kinda equal to `one three`, and we get a 1 for that. How come?

This is because stopwords are _not_ really ignored completely. They do still affect _positions_ (and that’s intentional, so that matching operators and other ranking factors would work as expected, just in some other example cases).

Therefore, this field gets indexed as `one * three`, where star marks a skipped position. So when matching the `one two three` query, the engine knows that positions number 1 and 3 were matched alright. But there is no (efficient) way for it to tell what exactly was in that missed position 2 in the original field; ie. was there a stopword, or was there any _regular_ word that the query simply did not mention (like in the `one four three` example). So when computing this factor, we see that there was an unmatched position, therefore we assume that the field was not covered fully (by the query terms), and set the factor to 0.

#### exact_hit

Field-level, boolean, whether a query was a full and exact match of the entire current field (that is, after normalization, morphology, etc). Used in the SPH04 ranker.

#### exact_order

Field-level, boolean, whether all of the query keywords were matched in the current field in the exact query order. (In other words, whether our field “covers” the entire query, and in the right order, too.)

For example, `(microsoft office)` query would yield `exact_order = 1` in a field with the `We use Microsoft software in our office.` content.

However, the very same query in a field with `(Our office is Microsoft free.)` text would yield `exact_order = 0` because, while the coverage is there (all words are matched), the order is wrong.

#### full_field_hit

Field-level, boolean, whether the current field was (seemingly) fully covered by the query.

This flag should be set when all the _field_ keywords are matched by the query, in whatever order. In other words, this factor requires “full coverage” of the field by the query, and “allows” to reorder the words.

For example, a field `three one` should get `full_field_hit = 1` against a query `one two three`. Both keywords were “covered” (matched), and the order does not matter.

Note that all documents where `exact_field_hit = 1` (which is even more strict) must also get `full_field_hit = 1`, but not vice versa.

Also, beware that stopwords and other text processing tools might “break” this factor, for exactly the same reasons that we disscussed a little earlier in [exact_field_hit](http://sphinxsearch.com/docs/sphinx3.html#exact_field_hit).

#### has_digit_hits

Field-level, total matched field hits count over just the `has_digit` keywords.

#### hit_count

Field-level, total field hits count over all keywords. In other words, total number of keyword occurrences that were matched in the current field.

Note that a single keyword may occur (and match!) multiple times. For example, if `hello` occurs 3 times in a field and `world` occurs 5 times, `hit_count` will be 8.

#### is_noun_hits

Field-level, total matched field hits count over just the `is_noun` keywords.

#### is_latin_hits

Field-level, total matched field hits count over just the `is_latin` keywords.

#### is_number_hits

Field-level, total matched field hits count over just the `is_number` keywords.

#### lccs

Field-level, Longest Common Contiguous Subsequence. A length of the longest contiguous subphrase between the query and the document, computed in keywords.

LCCS factor is rather similar to LCS but, in a sense, more restrictive. While LCS could be greater than 1 even though no two query words are matched right next to each other, LCCS would only get greater than 1 if there are _exact_, contiguous query subphrases in the document.

For example, `one two three four five` query vs `one hundred three hundred five hundred` document would yield `lcs = 3`, but `lccs = 1`, because even though mutual dispositions of 3 matched keywords (`one`, `three`, and `five`) do match between the query and the document, none of the occurences are actually next to each other.

Note that LCCS still does not differentiate between the frequent and rare keywords; for that, see WLCCS factor.

#### lcs

Field-level, Longest Common Subsequence. This is the length of a maximum “verbatim” match between the document and the query, counted in words.

By construction, it takes a minimum value of 1 when only “stray” keywords were matched in a field, and a maximum value of a query length (in keywords) when the entire query was matched in a field “as is”, in the exact query order.

For example, if the query is `hello world` and the field contains these two words as a subphrase anywhere in the field, `lcs` will be 2. Another example, this works on _subsets_ of the query too, ie. with `hello world program` query the field that only contains `hello world` subphrase also a gets an `lcs` value of 2.

Note that any _non-contiguous_ subset of the query keyword works here, not just a subset of adjacent keywords. For example, with `hello world program` query and `hello (test program)` field contents, `lcs` will be 2 just as well, because both `hello` and `program` matched in the same respective positions as they were in the query. In other words, both the query and field match a non-contiguous 2-keyword subset `hello * program` here, hence the value of 2 of `lcs`.

However, if we keep the `hello world program` query but our field changes to `hello (test computer program)`, then the longest matching subset is now only 1-keyword long (two subsets match here actually, either `hello` or `program`), and `lcs` is therefore 1.

Finally, if the query is `hello world program` and the field contains an exact match `hello world program`, `lcs` will be 3. (Hopefully that is unsurprising at this point.

#### max_idf

Field-level, `max(idf)` over all keywords that were matched in the field.

#### max_window_hits()

Field-level, parametrized, computes `max(window_hit_count)` over all N-keyword windows (where N is the parameter). For example:

    mysql> SELECT *, weight() FROM test1 WHERE MATCH('one two')
        -> OPTION ranker=expr('sum(max_window_hits(3))');
    +------+-------------------+----------+
    | id   | title             | weight() |
    +------+-------------------+----------+
    |    1 | one two           |        2 |
    |    2 | one aa two        |        2 |
    |    4 | one one aa bb two |        1 |
    |    3 | one aa bb two     |        1 |
    +------+-------------------+----------+
    3 rows in set (0.00 sec)

So in this example we are looking at rather short 3-keyword windows, and in document number 3 our matched keywords are too far apart, so the factor is 1. However, in document number 4 the `one one aa` window has 2 occurrences (even though of just one keyword), so the factor is 2 there. Documents number 1 and 2 are straightfoward.

#### min_best_span_pos

Field-level, the position of the first maximum LCS keyword span.

For example, assume that our query was `hello world program`, and that the `hello world` subphrase was matched twice in the current field, in positions 13 and 21. Now assume that `hello` and `world` additionally occurred elsewhere in the field (say, in positions 5, 8, and 34), but as those occurrences were not next to each other, they did not count as a subphrase match. In this example, `min_best_span_pos` will be 13, ie. the position of a first occurence of a longest (maximum) match, LCS-wise.

Note how for the single keyword queries `min_best_span_pos` must always equal `min_hit_pos`.

#### min_gaps

Field-level, the minimum number of positional gaps between (just) the keywords matched in field. Always 0 when less than 2 keywords match; always greater or equal than 0 otherwise.

For example, with the same `big wolf` query, `big bad wolf` field would yield `min_gaps = 1`; `big bad hairy wolf` field would yield `min_gaps = 2`; `the wolf was scary and big` field would yield `min_gaps = 3`; etc. However, a field like `i heard a wolf howl` would yield `min_gaps = 0`, because only one keyword would be matching in that field, and, naturally, there would be no gaps _matched_ keywords.

Therefore, this is a rather low-level, “raw” factor that you would most likely want to _adjust_ before actually using for ranking.

Specific adjustments depend heavily on your data and the resulting formula, but here are a few ideas you can start with:

- any `min_gaps` based boosts could be simply ignored when `word_count < 2`;
- non-trivial `min_gaps` values (ie. when `word_count <= 2`) could be clamped with a certain “worst case” constant while trivial values (ie. when `min_gaps = 0` and `word_count < 2`) could be replaced by that constant;
- a transfer function like `1 / (1 + min_gaps)` could be applied (so that better, smaller min_gaps values would maximize it and worse, bigger `min_gaps` values would fall off slowly).

#### min_hit_pos

Field-level, the position of the first matched keyword occurrence, counted in words. Positions begins from 1, so `min_hit_pos = 0` must be impossible in an actually matched field.

#### min_idf

Field-level, `min(idf)` over all keywords (not occurrences!) that were matched in the field.

#### sum_idf

Field-level, `sum(idf)` over all keywords (not occurrences!) that were matched in the field.

#### sum_idf_boost

Field-level, `sum(idf_boost)` over all keywords (not occurrences!) that were matched in the field.

#### tf_idf

Field-level, a sum of `tf*idf` over all the keywords matched in the field. (Or, naturally, a sum of `idf` over all the matched postings.)

For the record, `TF` is the Term Frequency, aka the number of (matched) keyword occurrences in the current field.

And `IDF` is the Inverse Document Frequency, a floating point value between 0 and 1 that describes how frequent this keyword is in the index.

Basically, frequent (and therefore _not_ really interesting) words get lower IDFs, hitting the minimum value of 0 when the keyword is present in all of the indexed documents. And vice versa, rare, unique, and therefore interesting words get higher IDFs, maxing out at 1 for unique keywords that occur in just a single document.

#### user_weight

Field-level, a user specified per-field weight (for a bit more details on how to set those, refer to [`OPTION field_weights`](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-select) section). By default all these weights are set to 1.

#### wlccs

Field-level, Weighted Longest Common Contiguous Subsequence. A sum of IDFs over the keywords of the longest contiguous subphrase between the current query and the field.

WLCCS is computed very similarly to LCCS, but every “suitable” keyword occurrence increases it by the keyword IDF rather than just by 1 (which is the case with both LCS and LCCS). That lets us rank sequences of more rare and important keywords higher than sequences of frequent keywords, even if the latter are longer. For example, a query `Zanzibar bed and breakfast` would yield `lccs = 1` against a `hotels of Zanzibar` field, but `lccs = 3` against a `London bed and breakfast` field, even though `Zanzibar` could be actually somewhat more rare than the entire `bed and breakfast` phrase. WLCCS factor alleviates (to a certain extent) by accounting the keyword frequencies.

#### word_count

Field-level, the number of unique keywords matched in the field. For example, if both `hello` and `world` occur in the current field, `word_count` will be 2, irregardless of how many times do both keywords occur.

## Ranking: builtin ranker formulas

All of the built-in Sphinx rankers can be emulated with the expression based ranker. You just need to pass a proper formula using the `OPTION ranker` clause.

Such emulation is, of course, going to be slower than using the built-in, pre-compiled rankers. But it still might be of interest if you want to start fine-tuning your ranking formula from an existing built-in baselines ranker. (Also, these formulas kinda define the nitty gritty built-in ranker details in a nicely readable fashion.)

Ranker

Formula

PROXIMITY_BM25

`sum(lcs*user_weight)*1000 + bm25`

BM25

`bm25`

NONE

`1`

WORDCOUNT

`sum(hit_count*user_weight)`

PROXIMITY

`sum(lcs*user_weight)`

MATCHANY

`sum((word_count + (lcs - 1)*max_lcs)*user_weight)`

FIELDMASK

`field_mask`

SPH04

`sum((4*lcs + 2*(min_hit_pos==1) + exact_hit)*user_weight)*1000 + bm25`

And here goes a complete example query:

    SELECT id, weight() FROM test1
    WHERE MATCH('hello world')
    OPTION ranker=expr('sum(lcs*user_weight)*1000 + bm25')

## Ranking: IDF magics

Sphinx supports several different IDF (Inverse Document Frequency) calculation options. Those can affect your relevance ranking (aka scoring) when you are:

- _either_ sharding your data, even with built-in rankers;
- _or_ doing any custom ranking work, even on a single shard.

By default, term IDFs are (a) per-shard, and (b) computed online. So they might fluctuate significantly when ranking. And several other ranking factors rely on them, so the entire rank might change a lot in a seeimingly random fashion. The reasons are twofold.

First, IDFs usually differ across shards (i.e. individual indexes that make up a bigger combined index). This means that a completely identical document might rank differently depending on a specific shard it ends up in. Not great.

Second, IDFs might change from query to query, as you update the index data. That instability in time might or might not be a desired effect.

To help alleviate these quirks (if they affect your use case), Sphinx offers two features:

1. `local_df` option to aggregate sharded IDFs.
2. `global_idf` feature to enforce prebuilt static IDFs.

`local_df` syntax is `SELECT ... OPTION local_df=1` and enabling that option tells the query to compute IDFs (more) precisely, i.e. over the entire index rather than individual shards. The default value is 0 (off) for performance reasons.

`global_idf` feature is more complicated and includes several components:

- `indextool --dumpdict --stats` switch that generates the source data, i.e. the per-shard dictionary dumps;
- `indextool --buildidf` switch that builds a static IDF file from those;
- per-shard `global_idf` config directive that lets you assign a static IDF file to your shards;
- per-query `OPTION global_idf=1` that forces the query to use that file.

Both these features affect the input variables used for IDF calculations. More specifically:

- let `n` be the DF, document frequency (for a given term);
- let `N` be the corpus size, total number of documents;
- by default, both `n` and `N` are per-shard;
- with `local_df`, they both are summed across shards;
- with `global_idf`, they both are taken from a static IDF file.

The static `global_idf` file actually stores a bunch of `n` values for every individual term, and the `N` value for the entire corpus, summed over all the source files that were available during `--buildidf` stage. For terms that are not present in the static `global_idf` file, their current (dynamic) DF values will be used. `local_df` should also still affect those.

To avoid overflows, `N` is adjusted up for the actual corpus size. Meaning that, for example, if the `global_idf` file says there were 1000 documents, but your index carries 3000 documents, then `N` is set to the bigger value, i.e. 3000. Therefore, you should either avoid using too small data slices for dictionary dumps, and/or manually adjust the frequencies, otherwise your static IDFs might be quite off.

To keep the `global_idf` file reasonably compact, you can use the additional `--skip-uniq` switch when doing the `--buildidf` stage. That switch will filter out all terms that only occur once. That usually reduces the `.idf` file size greatly, while still yielding exact or almost-exact results.

### How Sphinx computes IDF

Starting with v.3.3 we removed several legacy IDF calculation methods, and now Sphinx always uses the following formula to compute IDF from `n` (the document frequency) and `N` (the corpus size).

- `idf = log(N/n) / (2*log(N+1)) * term_idf_boost`

So we start with de-facto standard `raw_idf = log(N/n)`; then we normalize that for the corpus size; and further compress the `idf` into `[0.0, 0.5)` range.

Then we apply per-term user boosts from the query, if any. `term_idf_boost` defaults to `1.0` but can be arbitrarily changed for individual query terms by using the respective modifier, eg. `... WHERE MATCH('cat^1.2 dog')`.

For the record, both this IDF normalization itself and the specific `[0,0.5)` range are now mostly historical. The normalization is considered for removal.

## Ranking: picking fields with `rank_fields`

When your indexes and queries contain any special “fake” keywords (usually used to speedup matching), it makes sense to exclude those from ranking. That can be achieved by putting such keywords into special fields, and then using `OPTION rank_fields` clause in the `SELECT` statement to pick the fields with actual text for ranking. For example:

    SELECT id, weight(), title FROM myindex
    WHERE MATCH('hello world @sys _category1234')
    OPTION rank_fields='title content'

`rank_fields` is designed to work as follows. Only the keyword occurrences in the ranked fields get processed when computing ranking factors. Any other occurrences are ignored (by ranking, that is).

Note a slight caveat here: for _query-level_ factors, only the _query_ itself can be analyzed, not the index data.

This means that when you do not explicitly specify the fields in the query, the query parser _must_ assume that the keyword can actually occur anywhere in the document. And, for example, `MATCH('hello world _category1234')` will compute `query_word_count=3` for that reason. This query does indeed have 3 keywords, even if `_category1234` never _actually_ occurs anywhere except `sys` field.

Other than that, `rank_fields` is pretty straightforward. _Matching_ will still work as usual. But for _ranking_ purposes, any occurrences (hits) from the “system” fields can be ignored and hidden.

## Operations: “siege mode”, temporary global query limits

Sphinx `searchd` now has a so-called “siege mode” that temporarily imposes server-wide limits on _all_ the incoming `SELECT` queries, for a given amount of time. This is useful when some client is flooding `searchd` with heavy requests and, for whatever reason, stopping those requests at other levels is complicated.

Siege mode is controlled via a few global server variables. The example just below will introduce a siege mode for 15 seconds, and impose limits of at most 1000 processed documents and at most 0.3 seconds (wall clock) per query:

    set global siege=15
    set global siege_max_fetched_docs=1000
    set global siege_max_query_msec=300

Once the timeout reaches zero, the siege mode will be automatically lifted.

There also are intentionally hardcoded limits you can’t change, namely:

- upper limit for `siege` is 300 seconds, i.e. 5 minutes
- upper limit for `siege_max_fetched_docs` is 1,000,000 documents
- upper limit for `siege_max_query_msec` is 1 second, i.e. 1000 msec

Note that **current siege limits are reset when the siege stops.** So in the example above, if you start another siege in 20 seconds, then that next siege will be restarted with 1M docs and 1000 msec limits, and _not_ the 1000 docs and 300 msec limits from the previous one.

Siege mode can be turned off at any moment by zeroing out the timeout:

The current siege status is reported in `SHOW STATUS`:

    mysql> show status like 'siege%';
    +------------------------+---------+
    | Counter                | Value   |
    +------------------------+---------+
    | siege_sec_left         | 296     |
    | siege_max_query_msec   | 1000    |
    | siege_max_fetched_docs | 1000000 |
    +------------------------+---------+
    3 rows in set (0.00 sec)

Next order of business, the document limit has a couple interesting details that require explanation.

First, the `fetched_docs` counter is calculated a bit differently for term and non-term searches. For term searches, it counts all the (non-unique!) rows that were fetched by full-text term readers, batch by batch. For non-term searches, it counts all the (unique) alive rows that were matched (either by an attribute index read, or by a full scan).

Second, for multi-index searches, the `siege_max_fetched_docs` limit will be split across the local indexes (shards), weighted by their document count.

If you’re really curious, let’s discuss those bits in more detail.

The non-term search case is rather easy. All the actually stored rows (whether coming either from a full scan or an attribute index reads) will be first checked for liveness, then accounted in the `fetched_docs` counter, then either further processed (with extra calculations, filters, etc). Bottom line, a query limited this way will run “hard” calculations, filter checks, etc on at most N rows. So best case scenario (if all `WHERE` filters pass), the query will return N rows, and never even a single row more.

Now, the term search case is more interesting. The lowest-level term readers will also emit individual rows, but as opposed to the “scan” case, either the terms or the rows might be duplicated. The `fetched_docs` counter merely counts those emitted rows, as it needs to limit the total amount of work done. So, for example, with a 2-term query like `(foo bar)` the processing will stop when _both_ terms fetch N documents total from the full-text index… even if not a single document was _matched_ just yet! If a term is duplicated, for example, like in a `(foo foo)` query, then _both_ the occurrences will contribute to the counter. Thus, for a query with M required terms all AND-ed together, the upper limit on the _matched_ documents should be roughly equal to N/M, because every matched document will be counted as “processed” M times in every term reader. So either `(foo bar)` or `(foo foo)` example queries with a limit of 1000 should result in roughly 500 matches tops.

That “roughly” just above means that, occasionally, there might be slightly more matches. As for performance reasons the term readers work in batches, the actual `fetched_docs` counter might get slightly bigger than the imposed limit, by the batch size at the most. But that must be insignificant as processing just a single small batch is very quick.

And as for splitting the limit between the indexes, it’s simply pro-rata, based on the per-index document count. For example, assume that `siege_max_fetched_docs` is set to 1000, and that you have 2 local indexes in your query, one with 1400K docs and one with 600K docs respectively. (It does not matter whether those are referenced directly or via a distributed index.) Then the per-index limits will be set to 700 and 300 documents respectively. Easy.

Last but not least, beware that the entire point of the “siege mode” is to **intentionally degrade the search results for too complex searches**! Use with extreme care; essentially only use it to stomp out cluster fires that can not be quickly alleviated any other way; and at this point we recommend to only _ever_ use it manually.

## SphinxQL reference

This section should eventually contain the complete SphinxQL reference. If the statement you’re looking for is not yet documented here, please refer to legacy [SphinxQL v.2.x reference](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-reference) document.

Here’s a complete list of SphinxQL statements.

- [ALTER syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-attach)
- [ATTACH INDEX syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-attach-index)
- [BEGIN syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-begin)
- [BEGIN, COMMIT, and ROLLBACK syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-commit)
- [BULK UPDATE syntax](http://sphinxsearch.com/docs/sphinx3.html#bulk-update-syntax)
- [CALL KEYWORDS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-call-keywords)
- [CALL QSUGGEST syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-call-qsuggest)
- [CALL SNIPPETS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-call-snippets)
- [CALL SUGGEST syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-call-suggest)
- [CREATE FUNCTION syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-create-function)
- [CREATE PLUGIN syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-create-plugin)
- [DELETE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-delete)
- [DESCRIBE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-describe)
- [DROP FUNCTION syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-drop-function)
- [DROP PLUGIN syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-drop-plugin)
- [FLUSH ATTRIBUTES syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-flush-attributes)
- [FLUSH HOSTNAMES syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-flush-hostnames)
- [FLUSH RAMCHUNK syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-flush-ramchunk)
- [FLUSH RTINDEX syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-flush-rtindex)
- [INSERT and REPLACE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-insert)
- [KILL syntax](http://sphinxsearch.com/docs/sphinx3.html#kill-syntax)
- [OPTIMIZE INDEX syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-optimize-index)
- [RELOAD INDEX syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-reload-index)
- [RELOAD PLUGINS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-reload-plugins)
- [REPLACE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-replace)
- [ROLLBACK syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-rollback)
- [SELECT ‘system_variable’ syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-select-sysvar)
- [SELECT syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-select)
- [SET syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-set)
- [SET TRANSACTION syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-set-transaction)
- [SHOW AGENT STATUS](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-agent-status)
- [SHOW CHARACTER SET syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-character-set)
- [SHOW COLLATION syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-collation)
- [SHOW DATABASES syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-databases)
- [SHOW INDEX AGENT STATUS syntax](http://sphinxsearch.com/docs/sphinx3.html#show-index-agent-status-syntax)
- [SHOW INDEX SETTINGS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-index-settings)
- [SHOW INDEX STATUS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-index-status)
- [SHOW META syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-meta)
- [SHOW PLAN syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-plan)
- [SHOW PLUGINS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-plugins)
- [SHOW PROFILE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-profile)
- [SHOW STATUS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-status)
- [SHOW TABLES syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-tables)
- [SHOW THREADS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-threads)
- [SHOW VARIABLES syntax](http://sphinxsearch.com/docs/sphinx3.html#show-variables-syntax)
- [SHOW WARNINGS syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-show-warnings)
- [TRUNCATE RTINDEX syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-truncate-rtindex)
- [UPDATE syntax](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-update)

### BULK UPDATE syntax

    BULK UPDATE ftindex (id, col1 [, col2 [, col3 ...]]) VALUES
    (id1, val1_1 [, val1_2 [, val1_3 ...]]),
    (id2, val2_1 [, val2_2 [, val2_3 ...]]),
    ...
    (idN, valN_1 [, valN_2 [, valN_3 ...]])

`BULK UPDATE` lets you update multiple rows with a single statement. Compared to running N individual statements, bulk updates provide both cleaner syntax and better performance.

Overall they are quite similar to regular updates. To summarize quickly:

- you can update (entire) attributes, naturally keeping their types (even when changing the width, ie. when updating a string, or entire JSON, etc);
- you can update numeric values within JSON, also keeping their types (and naturally keeping the width).

First column in the list must always be the `id` column. Rows are uniquely identified by document ids.

Other columns to update can either be regular attributes, or individual JSON keys, also just as with regular `UPDATE` queries. Here are a couple examples:

    BULK UPDATE test1 (id, price) VALUES (1, 100.00), (2, 123.45), (3, 299.99)
    BULK UPDATE test2 (id, json.price) VALUES (1, 100.00), (2, 123.45), (3, 299.99)

All value types (numerics, strings, JSON, MVA) are supported.

Bulk updates of existing values _must_ keep the type. This is a natural restriction for regular attributes, but it also applies to JSON values. For example, if you update an integer JSON value with a float, then that float will get converted (truncated) to the current integer type.

Compatible value type conversions will happen. Truncations are allowed.

Incompatible conversions will fail. For example, strings will _not_ be auto-converted to numeric values.

Attempts to update non-existent JSON keys will fail.

### KILL syntax

    KILL <thread_id>
    KILL SLOW <min_msec> MSEC

`KILL` lets you forcibly terminate long-running statements based either on thread ID, or on their current running time.

For the first version, you can obtain the thread IDs using the [`SHOW THREADS`](http://sphinxsearch.com/docs/sphinx2.html#sphinxql-threads) statement.

Note that forcibly killed queries are going to return almost as if they completed OK rather than raise an error. They will return a partial result set accumulated so far, and raise a “query was killed” warning. For example:

    mysql> SELECT * FROM rt LIMIT 3;
    +------+------+
    | id   | gid  |
    +------+------+
    |   27 |  123 |
    |   28 |  123 |
    |   29 |  123 |
    +------+------+
    3 rows in set, 1 warning (0.54 sec)

    mysql> SHOW WARNINGS;
    +---------+------+------------------+
    | Level   | Code | Message          |
    +---------+------+------------------+
    | warning | 1000 | query was killed |
    +---------+------+------------------+
    1 row in set (0.00 sec)

The respective network connections are not going to be forcibly closed.

At the moment, the only statements that can be killed are `SELECT`, `UPDATE`, and `DELETE`. Additional statement types might begin to support `KILL` in the future.

In both versions, `KILL` returns the number of threads marked for termination via the affected rows count:

    mysql> KILL SLOW 2500 MSEC;
    Query OK, 3 row affected (0.00 sec)

Threads already marked will not be marked again and reported this way.

There are no limits on the `<min_msec>` parameter for the second version, and therefore, `KILL SLOW 0 MSEC` is perfectly legal syntax. That specific statement is going to kill _all_ the currently running queries. So please use with a pinch of care.

### SELECT syntax

    SELECT <expr> [[AS] <alias>] [, ...]
    FROM <ftindex> [, ...]
        [{USE | IGNORE | FORCE} INDEX (<attr_index> [, ...]) [...]]
    [WHERE
        [MATCH('<text_query>') [AND]]
        [<where_condition> [AND <where_condition> [...]]]]
    [GROUP [<N>] BY <column> [, ...]
        [WITHIN GROUP ORDER BY <column> {ASC | DESC} [, ...]]
        [HAVING <having_condition>]]
    [ORDER BY <column> {ASC | DESC} [, ...]]
    [LIMIT [<offset>,] <row_count>]
    [OPTION <opt_name> = <opt_value> [, ...]]
    [FACET <facet_options> [...]]

`SELECT` is the main querying workhorse, and as such, comes with a rather extensive (and perhaps a little complicated) syntax. There are many different parts (aka clauses) in that syntax. Thankfully, most of them are optional.

Briefly, they are as follows:

- required `SELECT` columns list (aka items list, aka expressions list)
- required `FROM` clause, with the full-text index list
- optional `<hint> INDEX` clauses, with the attribute index usage hints
- optional `WHERE` condition clause, with the row filtering conditions
- optional `GROUP BY` clause, with the row grouping conditions
- optional `ORDER BY` clause, with the row sorting conditions
- optional `LIMIT` clause, with the result set size and offset
- optional `OPTION` clause, with all the special options
- optional `FACET` clauses, with a list of requested additional facets

The most notable differences from regular SQL are these:

- `FROM` list is **NOT** an implicit `JOIN`, but more like a `UNION`
- `ORDER BY` is always present, default is `ORDER BY WEIGHT() DESC, id ASC`
- `LIMIT` is always present, default is `LIMIT 0,20`
- `GROUP BY` always picks a specific “best” row to represent the group

#### Index hints clause

Index hints can be used to tweak query optimizer behavior and attribute index usage, for either performance or debugging reasons. Note that usually you should _not_ have to use them.

Multiple hints can be used, and multiple attribute indexes can be listed, in any order. For example, the following syntax is legal:

    SELECT id FROM test1
    USE INDEX (idx_lat)
    FORCE INDEX (idx_price)
    IGNORE INDEX (idx_time)
    USE INDEX (idx_lon) ...

All flavors of `<hint> INDEX` clause take an index list as their argument, for example:

    ... USE INDEX (idx_lat, idx_lon, idx_price)

Summarily, hints work this way:

- `USE INDEX` limits the optimizer to only use a subset of given indexes;
- `IGNORE INDEX` strictly forbids given indexes from being used;
- `FORCE INDEX` strictly forces the given indexes to be used.

`USE INDEX` tells the optimizer that it must only consider the given indexes, rather than _all_ the applicable ones. In other words, in the absence of the `USE` clause, all indexes are fair game. In its presence, only those that were mentioned in the `USE` list are. The optimizer still decides whether to actually to use or ignore any specific index. In the example above it still might choose to use `idx_lat` only, but it must never use `idx_time`, on the grounds that it was not mentioned explicitly.

`IGNORE INDEX` completely forbids the optimizer from using the given indexes. Ignores take priority, they override both `USE INDEX` and `FORCE INDEX`. Thus, while it is legal to `USE INDEX (foo, bar) IGNORE INDEX (bar)`, it is way too verbose. Simple `USE INDEX (foo)` achieves exactly the same result.

`FORCE INDEX` makes the optimizer forcibly use the given indexes (that is, if they are applicable at all) despite the query cost estimates.

For more discussion and details on attributes indexes and hints, refer to [“Using attribute indexes”](http://sphinxsearch.com/docs/sphinx3.html#using-attribute-indexes).

### SHOW INDEX AGENT STATUS syntax

    SHOW INDEX <distindex> AGENT STATUS [LIKE '...']

`SHOW INDEX AGENT STATUS` lets you examine a number internal per-agent counters associated with every agent (and then every mirror host of an agent) in a given distributed index.

The agents are numbered in the config order. The mirrors within each agent are also numbered in the config order. All timers must internally have microsecond precision, but should be displayed as floats and in milliseconds, for example:

    mysql> SHOW INDEX dist1 AGENT STATUS LIKE '%que%';
    +--------------------------------+-------+
    | Variable_name                  | Value |
    +--------------------------------+-------+
    | agent1_host1_query_timeouts    | 0     |
    | agent1_host1_succeeded_queries | 1     |
    | agent1_host1_total_query_msec  | 2.943 |
    | agent2_host1_query_timeouts    | 0     |
    | agent2_host1_succeeded_queries | 1     |
    | agent2_host1_total_query_msec  | 3.586 |
    +--------------------------------+-------+
    6 rows in set (0.00 sec)

As we can see from the output, there was just 1 query sent to each agent since `searchd` start, that query went well on both agents, and it took approx 2.9 ms and 3.6 ms respectively. The specific agents are addresses are intentionally not part of this status output to avoid clutter; they can in turn be examined using `DESCRIBE` statement:

    mysql> DESC dist1
    +---------------------+----------+
    | Agent               | Type     |
    +---------------------+----------+
    | 127.0.0.1:7013:loc1 | remote_1 |
    | 127.0.0.1:7015:loc2 | remote_2 |
    +---------------------+----------+
    2 rows in set (0.00 sec)

In this case (ie. without mirrors) the mapping is straightforward, we can see that we only have two agents, `agent1` on port 7013 and `agent2` on port 7015, and we now know what statistics are associated with which agent exactly. Easy.

### SHOW VARIABLES syntax

    SHOW [{GLOBAL | SESSION}] VARIABLES
        [{WHERE variable_name='<varname>' [OR ...] |
        LIKE '<varmask>'}]

`SHOW VARIABLES` statement serves two very different purposes:

- to provide compatibility with 3rd party MySQL clients;
- to examine the current status of `searchd` server variables.

Compatibility mode is required to support connections from certain MySQL clients that automatically run `SHOW VARIABLES` on connection and fail if that statement raises an error.

Optional `GLOBAL` or `SESSION` scope condition is for compatibility only at the moment, and the scope is ignored. All variables, both global and per-session, are always displayed.

`WHERE variable_name ...` condition is also for compatibility only, and also ignored.

`LIKE '<varmask>'` condition is supported and functional, for instance:

    mysql> show variables like '%comm%';
    +---------------+-------+
    | Variable_name | Value |
    +---------------+-------+
    | autocommit    | 1     |
    +---------------+-------+
    1 row in set (0.00 sec)

Most of the variables displayed in `SHOW VARIABLES` are mutable (ie. possible to change on the fly). Some are read-only. Some are constant.

    mysql> show variables;
    +--------------------------+-----------------------------+
    | Variable_name            | Value                       |
    +--------------------------+-----------------------------+
    | attrindex_thresh         | 1024                        |
    | autocommit               | 1                           |
    | character_set_client     | utf8                        |
    | character_set_connection | utf8                        |
    | collation_connection     | libc_ci                     |
    | log_debug_filter         |                             |
    | log_level                | info                        |
    | max_allowed_packet       | 8388608                     |
    | net_spin_msec            | 10                          |
    | qcache_max_bytes         | 0                           |
    | qcache_thresh_msec       | 3000                        |
    | qcache_ttl_sec           | 60                          |
    | query_log_format         | sphinxql                    |
    | query_log_min_msec       | 0                           |
    | siege                    | 0                           |
    | siege_max_fetched_docs   | 1000000                     |
    | siege_max_query_msec     | 1000                        |
    | sql_fail_filter          |                             |
    | sql_log_file             |                             |
    | version                  | 3.3.1-dev (commit fc5fb556) |
    +--------------------------+-----------------------------+
    20 rows in set (0.00 sec)

For instance, `log_level` is mutable; `max_allowed_packet` is read-only (you can change in `sphinx.conf` but with a restart); and `version` is constant.

Specific per-variable documentation can be found in the [“Server variables reference”](http://sphinxsearch.com/docs/sphinx3.html#server-variables-reference) section.

## Functions reference

This section should eventually contain the complete reference on functions that are supported in `SELECT` and other applicable places. If the function you’re looking for is not yet documented here, please refer to legacy [Sphinx v.2.x expressions reference](http://sphinxsearch.com/docs/sphinx2.html#expressions) document.

Here’s a complete list of builtin Sphinx functions.

- [ABS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-abs)
- [ALL](http://sphinxsearch.com/docs/sphinx2.html#expr-func-all)
- [ANY](http://sphinxsearch.com/docs/sphinx2.html#expr-func-any)
- [ATAN2](http://sphinxsearch.com/docs/sphinx2.html#expr-func-atan2)
- [BIGINT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-bigint)
- [BITCOUNT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-bitcount)
- [BITDOT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-bitdot)
- [BM25F](http://sphinxsearch.com/docs/sphinx2.html#expr-func-bm25f)
- [CEIL](http://sphinxsearch.com/docs/sphinx2.html#expr-func-ceil)
- [COALESCE](http://sphinxsearch.com/docs/sphinx2.html#expr-func-coalesce)
- [CONNECTION_ID](http://sphinxsearch.com/docs/sphinx2.html#expr-func-connection-id)
- [CONTAINS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-contains)
- [COS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-cos)
- [CRC32](http://sphinxsearch.com/docs/sphinx2.html#expr-func-crc32)
- [CURRENT_USER](http://sphinxsearch.com/docs/sphinx2.html#expr-func-current-user)
- [CURTIME](http://sphinxsearch.com/docs/sphinx2.html#expr-func-curtime)
- [DAY](http://sphinxsearch.com/docs/sphinx2.html#expr-func-day)
- [DOCUMENT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-document)
- [DOT](http://sphinxsearch.com/docs/sphinx3.html#dot-function)
- [DOUBLE](http://sphinxsearch.com/docs/sphinx2.html#expr-func-double)
- [EXIST](http://sphinxsearch.com/docs/sphinx2.html#expr-func-exist)
- [EXP](http://sphinxsearch.com/docs/sphinx2.html#expr-func-exp)
- [FACTORS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-factors)
- [FIBONACCI](http://sphinxsearch.com/docs/sphinx2.html#expr-func-fibonacci)
- [FLOOR](http://sphinxsearch.com/docs/sphinx2.html#expr-func-floor)
- [FVEC](http://sphinxsearch.com/docs/sphinx3.html#fvec-function)
- [GEODIST](http://sphinxsearch.com/docs/sphinx2.html#expr-func-geodist)
- [GEOPOLY2D](http://sphinxsearch.com/docs/sphinx2.html#expr-func-geopoly2d)
- [GREATEST](http://sphinxsearch.com/docs/sphinx2.html#expr-func-greatest)
- [HOUR](http://sphinxsearch.com/docs/sphinx2.html#expr-func-hour)
- [IDIV](http://sphinxsearch.com/docs/sphinx2.html#expr-func-idiv)
- [IF](http://sphinxsearch.com/docs/sphinx2.html#expr-func-if)
- [IN](http://sphinxsearch.com/docs/sphinx2.html#expr-func-in)
- [INDEXOF](http://sphinxsearch.com/docs/sphinx2.html#expr-func-indexof)
- [INTEGER](http://sphinxsearch.com/docs/sphinx2.html#expr-func-integer)
- [INTERVAL](http://sphinxsearch.com/docs/sphinx2.html#expr-func-interval)
- [LEAST](http://sphinxsearch.com/docs/sphinx2.html#expr-func-least)
- [LENGTH](http://sphinxsearch.com/docs/sphinx2.html#expr-func-length)
- [LN](http://sphinxsearch.com/docs/sphinx2.html#expr-func-ln)
- [LOG10](http://sphinxsearch.com/docs/sphinx2.html#expr-func-log10)
- [LOG2](http://sphinxsearch.com/docs/sphinx2.html#expr-func-log2)
- [MADD](http://sphinxsearch.com/docs/sphinx2.html#expr-func-madd)
- [MAX](http://sphinxsearch.com/docs/sphinx2.html#expr-func-max)
- [MIN](http://sphinxsearch.com/docs/sphinx2.html#expr-func-min)
- [MIN_TOP_SORTVAL](http://sphinxsearch.com/docs/sphinx2.html#expr-func-min-top-sortval)
- [MIN_TOP_WEIGHT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-min-top-weight)
- [MINUTE](http://sphinxsearch.com/docs/sphinx2.html#expr-func-minute)
- [MONTH](http://sphinxsearch.com/docs/sphinx2.html#expr-func-month)
- [MUL3](http://sphinxsearch.com/docs/sphinx2.html#expr-func-mul3)
- [NOW](http://sphinxsearch.com/docs/sphinx2.html#expr-func-now)
- [PACKEDFACTORS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-packedfactors)
- [POLY2D](http://sphinxsearch.com/docs/sphinx2.html#expr-func-poly2d)
- [POW](http://sphinxsearch.com/docs/sphinx2.html#expr-func-pow)
- [PP](http://sphinxsearch.com/docs/sphinx3.html#pp-function)
- [QUERY](http://sphinxsearch.com/docs/sphinx2.html#expr-func-query)
- [RAND](http://sphinxsearch.com/docs/sphinx2.html#expr-func-rand)
- [RANKFACTORS](http://sphinxsearch.com/docs/sphinx2.html#expr-func-rankfactors)
- [REMAP](http://sphinxsearch.com/docs/sphinx2.html#expr-func-remap)
- [SECOND](http://sphinxsearch.com/docs/sphinx2.html#expr-func-second)
- [SIN](http://sphinxsearch.com/docs/sphinx2.html#expr-func-sin)
- [SINT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-sint)
- [SLICEAVG](http://sphinxsearch.com/docs/sphinx3.html#slice-functions)
- [SLICEMAX](http://sphinxsearch.com/docs/sphinx3.html#slice-functions)
- [SLICEMIN](http://sphinxsearch.com/docs/sphinx3.html#slice-functions)
- [SQRT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-sqrt)
- [STRPOS](http://sphinxsearch.com/docs/sphinx3.html#strpos-function)
- [TIMEDIFF](http://sphinxsearch.com/docs/sphinx2.html#expr-func-timediff)
- [TO_STRING](http://sphinxsearch.com/docs/sphinx2.html#expr-func-to-string)
- [UINT](http://sphinxsearch.com/docs/sphinx2.html#expr-func-uint)
- [UTC_TIME](http://sphinxsearch.com/docs/sphinx2.html#expr-func-utc-time)
- [UTC_TIMESTAMP](http://sphinxsearch.com/docs/sphinx2.html#expr-func-utc-timestamp)
- [YEAR](http://sphinxsearch.com/docs/sphinx2.html#expr-func-year)
- [YEARMONTH](http://sphinxsearch.com/docs/sphinx2.html#expr-func-yearmonth)
- [YEARMONTHDAY](http://sphinxsearch.com/docs/sphinx2.html#expr-func-yearmonthday)
- [ZONESPANLIST](http://sphinxsearch.com/docs/sphinx2.html#expr-func-zonespanlist)

### `DOT()` function

    DOT(vector1, vector2)
    vector = {json.key | array_attr | FVEC(...)}

`DOT()` function computes a dot product over two vector arguments.

Vectors can be taken either from JSON, or from array attributes, or specified as constants using `FVEC()` function. All combinations should generally work.

The result type is always `float` for consistency and simplicity. (According to our benchmarks, performance gain from using `integer` or `bigint` for the result type, where applicable, is pretty much nonexistent anyway.)

Note that _internal_ calculations are optimized for specific input argument types anyway. For instance, `int8` vs `int8` vectors should be quite noticeably faster than `float` by `double` vectors containing the same data, both because integer multiplication is less expensive, and because `int8` would utilize 6x less memory.

So as a rule of thumb, use the narrowest possible type, that yields both better RAM use and better performance.

When one of the arguments is either NULL, or not a numeric vector (that can very well happen with JSON), or when both arguments are vectors of different sizes, `DOT()` returns 0.

### `FVEC()` function

    FVEC(const1 [, const2, ...])
    FVEC(json.key)

`FVEC()` function lets you define a vector of floats. Two current usecases are:

- to define a constant vector for subsequent use with [`DOT()`](http://sphinxsearch.com/docs/sphinx3.html#dot-function)
- to pass optimized float vectors stored in JSON to UDFs

**Constant vector form.**

In the first form, the arguments are a list of numeric constants. And note that there _can_ be a difference whether we use integers or floats here!

When both arguments to `DOT()` are integer vectors, `DOT()` can use an optimized integer implementation, and to define such a vector using `FVEC()`, you should only use integers.

The rule of thumb with vectors generally is: just use the narrowest possible type. Because that way, extra optimizations just might kick in. And the other way, they very definitely will not.

For instance, the optimizer is allowed to widen `FVEC(1,2,3,4)` from integers to floats alright, no surprise there. Now, in _this_ case it is also allowed to narrow the resulting `float` vector back to integers where applicable, because we can know that all the _original_ values were integers before widening.

And narrowing down from the floating point form like `FVEC(1.0, 2.0, 3.0, 4.0)` to integers is strictly prohibited. So even though the values actually are the same, in the first case additional integer-only optimization can be engaged, and in the second case they can’t.

**UDF argument wrapper form.**

In the second form, the only argument must be a JSON key, and the output is only intended for UDF functions (because otherwise this `FVEC()` wrapper should not be needed and you would just use the key itself). The associated value type gets checked, optimized float vectors get wrapped and passed to UDF, and any other types are replaced with a null vector (zero length and no data pointer) in the UDF call. The respective UDF type is `SPH_UDF_TYPE_FLOAT_VEC`.

Note that this case is intentionally designed as a fast accessor for UDFs that just passes `float` vectors to them, and avoids any data copying and conversion.

So if you attempt to wrap and pass anything else, null vector will be passed to the UDF. Could be a generic mixed vector with numeric values of differnt types, could be an optimized `int8` vector, could be a `double` vector - but in all these cases, despite the fact that they are compatible and _could_ technically be converted to some temporary `float` vector and then passed down, that kind of a conversion just does not happen. Intentionally, for performance reasons.

### `PP()` function

    PP(FACTORS())
    PP(jsoncol.key)
    PP(jsoncol.key)

`PP()` function pretty-prints JSON output (which by default would be compact rather than prettified). When applied to `FACTORS()` function, it will also automatically force JSON output. For example:

    mysql> select id, j from lj limit 1 \G
    *************************** 1. row ***************************
    id: 1
     j: {"gid":1107024,"urlcrc":2557061282}
    1 row in set (0.01 sec)

    mysql> select id, pp(j) from lj limit 1 \G
    *************************** 1. row ***************************
       id: 1
    pp(j): {
      "gid": 1107024,
      "urlcrc": 2557061282
    }
    1 row in set (0.01 sec)

    mysql> select id, factors() from lj where match('hello world')
        -> limit 1 option ranker=expr('1') \G
    *************************** 1. row ***************************
           id: 5332
    factors(): bm15=735, bm25a=0.898329, field_mask=2, doc_word_count=2,
    field1=(lcs=2, hit_count=2, word_count=2, tf_idf=0.517828, ...
    1 row in set (0.00 sec)

    mysql> select id, pp(factors()) from lj where match('hello world')
        -> limit 1 option ranker=expr('1') \G
    *************************** 1. row ***************************
           id: 5332
    pp(factors()): {
      "bm15": 735,
      "bm25a": 0.898329,
      "field_mask": 2,
      "doc_word_count": 2,
      "fields": [
        {
          "field": 1,
          "lcs": 2,
          "hit_count": 2,
          "word_count": 2,
          ...
    1 row in set (0.00 sec)

### Slice functions

    SLICEAVG(json.key, min_index, sup_index)
    SLICEMAX(json.key, min_index, sup_index)
    SLICEMIN(json.key, min_index, sup_index)

Function call example

Info

`SLICEAVG(j.prices, 3, 7)`

Computes average value in a slice

`SLICEMAX(j.prices, 3, 7)`

Computes minimum value in a slice

`SLICEMIN(j.prices, 3, 7)`

Computes maximum value in a slice

Slice functions (`SLICEAVG`, `SLICEMAX`, and `SLICEMIN`) expect a JSON array as their 1st argument, and two constant integer indexes A and B as their 2nd and 3rd arguments, respectively. Then they compute an aggregate value over the array elements in the respective slice, that is, from index A inclusive to index B exclusive (just like in Python and Golang). For instance, in the example above elements 3, 4, 5, and 6 will be processed, but not element 7. The indexes are, of course, 0-based.

The returned value is `float`, even when all the input values are actually integer.

Non-arrays and slices with non-numeric items will return a value of `0.0` (subject to change to `NULL` eventually).

### `STRPOS()` function

    STRPOS(haystack, const_needle)

`STRPOS()` returns the index of the first occurence of its second argument (“needle”) in its first argument (“haystack”), or `-1` if there are no occurrences.

The index is counted in bytes (rather that Unicode codepoints).

At the moment, needle must be a constant string. If needle is an empty string, then 0 will be returned.

## Server variables reference

`searchd` has a number of server variables that can be changed on the fly using the `SET GLOBAL var = value` statement. This section provides a reference on all those variables.

- [`attrindex_thresh`](http://sphinxsearch.com/docs/sphinx3.html#attrindex_thresh-variable)
- [`log_debug_filter`](http://sphinxsearch.com/docs/sphinx3.html#log_debug_filter-variable)
- [`log_level`](http://sphinxsearch.com/docs/sphinx3.html#log_level-variable)
- [`net_wait`](http://sphinxsearch.com/docs/sphinx3.html#net_wait-variable)
- [`qcache_max_bytes`](http://sphinxsearch.com/docs/sphinx2.html#qcache)
- [`qcache_thresh_msec`](http://sphinxsearch.com/docs/sphinx2.html#qcache)
- [`qcache_ttl_sec`](http://sphinxsearch.com/docs/sphinx2.html#qcache)
- [`query_log_format`](http://sphinxsearch.com/docs/sphinx3.html#query_log_format-variable)
- [`query_log_min_msec`](http://sphinxsearch.com/docs/sphinx3.html#query_log_min_msec-variable)
- [`siege`](http://sphinxsearch.com/docs/sphinx3.html#siege-mode)
- [`siege_max_fetched_docs`](http://sphinxsearch.com/docs/sphinx3.html#siege-mode)
- [`sql_fail_filter`](http://sphinxsearch.com/docs/sphinx3.html#sql_fail_filter-variable)
- [`sql_log_file`](http://sphinxsearch.com/docs/sphinx3.html#sql_log_file-variable)

### `attrindex_thresh` variable

    SET GLOBAL attrindex_thresh = 256

Minimum segment size required to enable building the [attribute indexes](http://sphinxsearch.com/docs/sphinx3.html#using-attribute-indexes), counted in rows. Default is 1024.

Sphinx will only create attribute indexes for “large enough” segments (be those RAM or disk segments). As a corollary, if the entire FT index is small enough, ie. under this threshold, attribute indexes will not be engaged at all.

At the moment, this setting seem useful for testing and debugging only, and normally you must not need to tweak it in production.

### `log_debug_filter` variable

    SET GLOBAL log_debug_filter = 'ReadLock'

Supresses debug-level log entries that start with a given prefix. Default is empty string, ie. do not suppress any entries.

This makes `searchd` less chatty at `debug` and higher `log_level` levels.

At the moment, this setting seem useful for testing and debugging only, and normally you must not need to tweak it in production.

### `log_level` variable

    SET GLOBAL log_level = {info | debug | debugv | debugvv}'

Sets the current logging level. Default (and minimum) level is `info`.

This variable is useful to temporarily enable debug logging in `searchd`, with this or that verboseness level.

At the moment, this setting seem useful for testing and debugging only, and normally you must not need to tweak it in production.

### `net_spin_msec` variable

    SET GLOBAL net_spin_msec = 30

Sets the poller spinning period in the network thread. Default is 10 msec.

The usual thread CPU slice is basically in 5-10 msec range. (For the really curious, a rather good starting point are the lines mentioning “targeted preemption latency” and “minimal preemption granularity” in `kernel/sched/fair.c` sources.)

Therefore, if a heavily loaded network thread calls `epoll_wait()` with even a seemingly tiny 1 msec timeout, that thread could occasionally get preempted and waste precious microseconds. According to an ancient internal benchmark that we can neither easily reproduce nor disavow these days (or in other words: under certain circumstances), that can result in quite a significant difference. More specifically, internal notes report ~3000 rps without spinning (ie. with `net_spin_msec = 0`) vs ~5000 rps with spinning.

Therefore, by default we choose to call `epoll_wait()` with zero timeouts for the duration of `net_spin_msec`, so that our “actual” slice for network thread is closer to those 10 msec, just in case we get a lot of incoming queries.

### `query_log_format` variable

    SET GLOBAL query_log_format = {plain | sphinxql}

Changes the search query logging format on the fly. Default is `plain`, and the other option is `sphinxql`.

### `query_log_min_msec` variable

    SET GLOBAL query_log_min_msec = 1000

Changes the minimum elapsed time threshold for the search queries to get logged. Default is 0 msec, ie. log all queries.

### `sql_fail_filter` variable

    SET GLOBAL sql_fail_filter = 'insert'

The “fail filter” is a simple early stage filter imposed on all the incoming SphinxQL queries. Any incoming queries that match a given non-empty substring will immediately fail with an error.

This is useful for emergency maintenance, just as [siege mode](http://sphinxsearch.com/docs/sphinx3.html#siege-mode). The two mechanisms are independent of each other, ie. both fail filter and siege mode can be turned on simultaneously.

As of v.3.2, the matching is simple, case-sensitive and bytewise. This is likely to change in the future.

To remove the filter, set the value to an empty string.

    SET GLOBAL sql_fail_filter = ''

### `sql_log_file` variable

    SET GLOBAL sql_log_file = '/tmp/sphinxlog.sql'

SQL log lets you (temporarily) enable logging all the incoming SphinxQL queries, in (almost) raw form. Compared to `query_log` directive, this logger:

- logs _all_ SphinxQL queries, not just searches;
- does _not_ log any SphinxAPI calls;
- does _not_ have any noticeable performance impact;
- is stopped by default.

Queries are stored as received. A hardcoded `; /* EOQ */` separator and then a newline are stored after every query, for parsing convenience. It’s useful to capture and later replay a stream of all client SphinxQL queries.

For performance reasons, SQL logging uses a rather big buffer (to the tune of a few megabytes), so don’t be alarmed when `tail` does not immediately display something after your start this log.

To stop SQL logging (and close and flush the log file), set the value to an empty string.

    SET GLOBAL sql_log_file = ''

We do _not_ recommend keeping SQL logging on for prolonged periods on loaded systems, as it might use a lot of disk space.

## Changes in 3.x

### Version 3.3.1, 06 jul 2020

New features:

- added [UDF call batching](http://sphinxsearch.com/docs/sphinx3.html#udf-call-batching) that enables UDFs to process multiple matched rows at a time
- added [`PP()`](http://sphinxsearch.com/docs/sphinx3.html#pp-function) pretty-printing function for `FACTORS()` and JSON values
- added multi-threaded index loading
- added [`KILL <tid>`](http://sphinxsearch.com/docs/sphinx3.html#kill-syntax) SphinxQL statement
- added [`SHOW INDEX <idx> AGENT STATUS`](http://sphinxsearch.com/docs/sphinx3.html#show-index-agent-status-syntax) SphinxQL statement, and moved per-agent counters there from `SHOW STATUS`

Minor new additions:

- added a number of runtime [server variables](http://sphinxsearch.com/docs/sphinx3.html#server-variables-reference) to [`SHOW VARIABLES`](http://sphinxsearch.com/docs/sphinx3.html#show-variables-syntax), namely
  - added `log_debug_filter`, `net_spin_msec`, `query_log_min_msec`, `sql_fail_filter`, and `sql_log_file`
  - moved `attrindex_thresh`, `siege_max_fetched_docs`, `siege_max_query_msec`, `qcache_max_bytes`, `qcache_thresh_msec`, and `qcache_ttl_sec` from `SHOW STATUS`
- added support for `SET GLOBAL server_var` in `sphinxql_state` startup script

Changes and improvements:

- removed `timestamp` columns support, use `uint` type instead (existing indexes are still supported; `timestamp` should automatically work as `uint` in those)
- removed `OPTION idf` and unified IDF calculations, see [“How Sphinx computes IDF”](http://sphinxsearch.com/docs/sphinx3.html#how-sphinx-computes-idf)
- changed `WEIGHT()` from integer to float
- changed `global_idf` behavior; now missing terms get local IDF instead of zero
- changed `OPTION cutoff` to properly account all processed matches
- changed directives deprecated in v.3.1 and earlier to hard errors
- optimized indexing a little (about 1-2% faster)
- optimized `DOT()` over `int8` vectors, upto 1.3x faster
- optimized query throughput on fast read-only queries upto 350+ Krps (various internal locking and performance changes, aka “highload optimizations”)
- improved float value formatting, mostly in SphinxQL output
- improved `UPDATE` handling, updates can now execute in parallel (again)
- improved index schema checks (more checks for invalid names, etc)
- increased `SHOW THREADS` query limit from 512 to 2048 bytes

Fixes:

- fixed UDF memory leak when using a `FACTORS()` argument, and optimized that case a little
- fixed `sql_log_file` race that caused (rare-ish) crashes under high query load
- fixed that facets with expressions could occasionally yield either missing or incorrect resulting rows
- fixed an overflow in docid hash (triggered on rather huge indexes)
- fixed that `CALL KEYWORDS` did not use normalized term on `global_idf` lookup
- fixed expression types issue when doing mixed int/float const promotion
- fixed that RAM segments did not account the docid hash size
- fixed that `INSERT` only checked RAM segments for duplicate docids
- fixed an internal error on `COUNT(*)` vs empty RT

### Version 3.2.1, 31 jan 2020

New features:

- added [term-OR operator](http://sphinxsearch.com/docs/sphinx3.html#term-or-operator) for proper query-level synonyms, for example `(red || green || blue) pixel`
- added [document-only wordforms](http://sphinxsearch.com/docs/sphinx3.html#using-wordforms), for example `!indexme => differently`
- added several [vector search](http://sphinxsearch.com/docs/sphinx3.html#searching-vector-searches) improvements
  - added int8/int/float fixed-width [array attributes](http://sphinxsearch.com/docs/sphinx3.html#using-array-attributes) support, for example `sql_attr_int8_array = myvec[128]`
  - added [`DOT()`](http://sphinxsearch.com/docs/sphinx3.html#dot-function) support for all those new array types
  - added int8 vectors support to JSON, and `int8[]` and `float[]` [JSON syntax extensions](http://sphinxsearch.com/docs/sphinx3.html#using-json)
  - added [`FVEC(json.field)`](http://sphinxsearch.com/docs/sphinx3.html#fvec-function) support to expressions, and the respective `SPH_UDF_TYPE_FLOAT_VEC` support to UDFs
- added [`BULK UPDATE`](http://sphinxsearch.com/docs/sphinx3.html#bulk-update-syntax) SphinxQL statement
- added attribute index reads for multi-GEODIST-OR queries, upto 15x+ speedup (see section on [geosearches](http://sphinxsearch.com/docs/sphinx3.html#searching-geosearches) for details)
- added [siege mode](http://sphinxsearch.com/docs/sphinx3.html#siege-mode), temporary global query limits with `SET GLOBAL siege`
- added `sum_idf_boost`, `is_noun_hits`, `is_latin_hits`, `is_number_hits`, `has_digit_hits` per-field ranking factors](#ranking-factors)
- added `is_noun`, `is_latin`, `is_number`, and `has_digit` per-term flags; added the respective `is_noun_words`, `is_latin_words`, `is_number_words`, and `has_digit_words` per-query ranking factors; and added query factors support to UDFs (see `sphinxudf.h`)
- added online query stream filtering with [`SET GLOBAL sql_fail_filter`](http://sphinxsearch.com/docs/sphinx3.html#sql_fail_filter-variable)
- added online query stream logging with [`SET GLOBAL sql_log_file`](http://sphinxsearch.com/docs/sphinx3.html#sql_log_file-variable)
- added [`SLICEAVG`, `SLICEMAX`, `SLICEMIN`](http://sphinxsearch.com/docs/sphinx3.html#slice-functions) functions, and [`STRPOS(str,conststr)`](http://sphinxsearch.com/docs/sphinx3.html#strpos-function) function

Minor new additions:

- added hash-comment support to `exceptions` files
- added `--dummy <arg>` switch to `searchd` (useful to quickly identify specific instances in the process list)
- added IDF info, term flags, and JSON format output to `CALL KEYWORDS` (for JSON output, call it with `CALL KEYWORDS(..., 1 AS json)`
- added `IS NULL` and `IS NOT NULL` checks to `ALL()` and `ANY()` JSON iterators
- added `last_good_id` to TSV indexing error reporting
- added `ram_segments` counter to `SHOW INDEX STATUS`, and renamed two counters (`ram_chunk` to `ram_segments_bytes`, `disk_chunks` to `disk_segments`)
- added `sql_query_kbatch` directive, deprecated `sql_query_killlist` directive
- added `<sphinx:kbatch>` support to XML source
- documented a few semi-hidden options (`net_spin_msec` for example)

Changes and improvements:

- improved parsing of long constant lists in expressions, requires much less `thread_stack` now
- improved `stopwords` handling, fixed the hash collisions issue
- improved `stopwords` directive, made it multi-valued
- improved `global_idf` handling, made global IDFs totally independent from per-index DFs
- improved `EXPLAIN`, ensured that it always reports real query plan and stats
- improved stats precision output for query times under 1 msec, and generally increased internal query timing precision
- improved argument types checking in expressions, and fixed a bunch of missed cases (issues on `GEODIST()` vs JSON, crash in `COALESCE()` args check, etc)
- improved `FACET` handling, single-search optimization must now always engage
- changed `indexer --nohup` to rename index files to `.new` on success
- changed `query_time` metric behaviour for distributed indexes, now it will account wall time
- removed “search all indexes” syntax leftovers that were possible via API
- removed umask on `searchd.log`

Major optimizations:

- optimized frequent 1-part and 2-part `ORDER BY` clauses, upto 1.1x speedup
- optimized full scan queries, upto 1.2x+ speedup
- optimized `DOT()` for a few cases like `int8` vectors, upto 2x+ speedup
- optimized facets, upto 1.1x speedup

Fixes:

- fixed that `ORDER BY RAND()` was breaking `WEIGHT()` (also, enabled it for grouping queries)
- fixed hash-comment syntax in wordforms
- fixed a couple races in wordforms
- fixed a couple deadlocks related to `ATTACH`
- fixes a few issues with `max_window_hits()` and `exact_order` factors
- fixed a rare B-tree crash when inserting duplicate values
- fixed a rare TSV indexing issue (well-formed file could fail indexing because of a very rare buffer boundary issue)
- fixed occasional crashes on distributed searches on some CPU and glibc combos (double release)
- fixed incorrect `SHOW META` after index-less `SELECT`
- fixed `ALL()` and `ANY()` vs optimized JSON vectors, and fixed optimized int64 JSON vector accessor
- fixed that `SHOW THREADS ... OPTION columns=X` limit permanently clipped the thread descriptions
- fixed `/searchd` HTTP endpoint error format
- fixed per-index query stats vs RT indexes
- fixed that query parser could occasionally fail on high ASCII codes
- fixed a few issues causing incorrect or unexpected handling of `cutoff` and other query limits
- fixed a few `json_packed_keys` issues
- fixed MVA64 values clipping on `INSERT`
- fixed occasional crashes and/or memory corruption on `UPDATE` and `INSERT`
- fixed `SNIPPET(field,QUERY())` case to some extent (we now filter out query syntax and treat `QUERY()` as a bag of words in this case)
- fixed that index reads on JSON in RT could erroneously disable other `WHERE` conditions from the query
- fixed a number of facets-related issues (occasionally non-working parallel execution, occasional crashes, etc)
- fixed a crash on empty index list via SphinxAPI
- fixed schema attributes order for XML/TSV/CSV sources
- fixed sticky `regexp_filter` vs `ATTACH`

### Version 3.1.1, 17 oct 2018

- added `indexer --dump-rows-tsv` switch, and renamed `--dump-rows` to `--dump-rows-sql`
- added initial `COALESCE()` function support for JSONs (beware that it will compute everything in floats!)
- added support for `!=`, `IN`, and `NOT IN` syntax to expressions
- added `prefix_tokens` and `suffix_tokens` options to `blend_mode` directive
- added `OPTION rank_fields`, lets you specify fields to use for ranking with either expression or ML (UDF) rankers
- added explicit duplicate documents (docids) suppression back into `indexer`
- added `batch_size` variable to `SHOW META`
- added `csvpipe_header` and `tsvpipe_header` directives
- added `sql_xxx` counters to `SHOW STATUS`, generally cleaned up counters
- added mixed codes indexing, available via `blend_mixed_codes` and `mixed_codes_fields` directives
- added `OPTION inner_limit_per_index` to explicitly control reordering in a nested sharded select
- added a hard limit for `max_matches` (must be under 100M)
- optimized Postgres indexing CPU and RAM use quite significantly
- optimized `FACET` queries with expressions and simple by-attribute (no aliases!) facets; multi-sort optmization now works in that case
- optimized `id` lookups (queries like `UPDATE ... WHERE id=123` should now be much faster)
- optimized result set aggregation vs nested sharded selects
- optimized `PACKEDFACTORS()` storage a lot (upto 60x speedup with `max_matches=50000`)
- improved UDF error handling, the error argument is now a message buffer instead of just a 1-char flag
- improved the nested sharded select reordering, less confusing now (by default, does _not_ scale the inner `LIMIT` anymore)
- improved `searchd --listen` switch, multiple `--listen` instances are now allowed, and `--console` is _not_ required anymore
- improved failed allocation reporting, and added huge allocation tracking
- removed legacy `@count`, `@weight`, `@expr`, `@geodist` syntax support
- removed legacy `SetWeights()`, `SetMatchMode()`, `SetOverride()`, `SetGeoAnchor()` calls, `SPH_MATCH_xxx` constants, and `SPH_SORT_EXPR` sorting mode from APIs
- removed legacy `spelldump` utility
- removed unused `.sha` index files
- removed extraneous “no extra index definitions” warning

Major fixes:

- fixed 9+ crashes caused by certain complex (and usually rare) conditions and/or settings combinations
- fixed 2 crashes caused by broken index data (in vrows and dictionaries)
- fixed plain index locking issues on Windows
- fixed JSON fields handling vs strings and NULLs (no more corner cases like NULL objects passing a test for json.col=0)
- fixed matches loss issue in positional (phrase/order/sentence etc) operators and modifiers under certain conditions
- fixed hashing-related hangups under certain (rather rare) occasions
- fixed several type inference issues in expressions when using JSON fields

Other fixes:

- fixed that `min_best_span_pos` was sometimes off
- fixed the behavior on missing `global_idf` file
- fixed `indextool --check` vs string attributes, and vs empty JSONs
- fixed blended vs multiforms behavior (works much more predictably now)
- fixed query parser vs wildcard-only tokens
- fixed that MySQL 8.0+ clients failed to connect
- fixed occasional semaphore races on startup
- fixed `OPTIMIZE` vs `UPDATE` race; `UPDATE` can now fail with a timeout
- fixed `indexer --merge --rotate` vs kbatches
- fixed occasional rotation-related deadlock
- fixed a few memory leaks

### Version 3.0.3, 30 mar 2018

- added `BITCOUNT()` function and bitwise-NOT operator, eg `SELECT BITCOUNT(~3)`
- made `searchd` config section completely optional
- improved `min_infix_len` behavior, required 2-char minimum is now enforced
- improved docs, added a few sections
- fixed binary builds performance
- fixed several crashes (related to docstore, snippets, threading, `json_packed_keys` in RT)
- fixed docid-less SQL sources, forbidden those for now (docid still required)
- fixed int-vs-float precision issues in expressions in certain cases
- fixed `uptime` counter in `SHOW STATUS`
- fixed query cache vs `PACKEDFACTORS()`

### Version 3.0.2, 25 feb 2018

- added `full_field_hit` ranking factor
- added `bm15` ranking factor name (legacy `bm25` name misleading, to be removed)
- optimized RT inserts significantly (upto 2-6x on certain benchmarks vs 3.0.1)
- optimized `exact_field_hit` ranking factor, impact now negligible (approx 2-4%)
- improved `indexer` output, less visual noise
- improved `searchd --safetrace` option, now skips `addr2line` to avoid occasional freezes
- improved `indexer` MySQL driver lookup, now also checking for `libmariadb.so`
- fixed rare occasional `searchd` crash caused by attribute indexes
- fixed `indexer` crash on missing SQL drivers, and improved error reporting
- fixed `searchd` crash on multi-index searches with docstore
- fixed that expression parser failed on field-shadowing attributes in `BM25F()` weights map
- fixed that `ALTER` failed on field-shadowing attributes vs `index_field_lengths` case
- fixed junk data writes (seemingly harmless but anyway) in certain cases
- fixed rare occasional `searchd` startup failures (threading related)

### Version 3.0.1, 18 dec 2017

- first public release of 3.x branch

## Changes since v.2.x

> WIP: the biggest change to rule them all is yet to come. The all new, fully RT index format is still in progress, and not yet available. Do not worry, ETL via `indexer` will _not_ be going anywhere. Moreover, despite being fully and truly RT, the new format is actually already _faster_ at batch indexing.

The biggest changes since Sphinx v.2.x are:

- added DocStore, document storage
  - original document contents can now be stored into the index
  - disk based storage, RAM footprint should be minimal
  - goodbye, _having_ to query Another Database to fetch data
- added new attributes storage format
  - arbitrary updates support (including MVA and JSON)
  - goodbye, sudden size limits
- added attribute indexes, with JSON support
  - … `WHERE gid=123` queries can now utilize A-indexes
  - … `WHERE MATCH('hello') AND gid=123` queries can now efficiently intersect FT-indexes and A-indexes
  - goodbye, _having_ to use fake keywords
- added compressed JSON keys
- switched to rowids internally, and forced all docids to 64 bits

Another two big changes that are already available but still in pre-alpha are:

- added “zero config” mode (`./sphinxdata` folder)
- added index replication

The additional smaller niceties are:

- added always-on support for xmlpipe, snowball stemmers, and re2 (regexp filters)
- added `blend_mode=prefix_tokens`, and enabled empty `blend_mode`
- added `kbatch_source` directive, to auto-generate k-batches from source docids (in addition to explicit queries)
- added `SHOW OPTIMIZE STATUS` statement
- added `exact_field_hit` ranking factor
- added `123.45f` value syntax in JSON, optimized support for float32 vectors, and `FVEC()` and `DOT()` functions
- added preindexed data in document storage to speed up `SNIPPETS()` (via `hl_fields` directive)
- changed field weights, zero and negative weights are now allowed
- changed stemming, keywords with digits are now excluded

A bunch of legacy things were removed:

- removed `dict`, `docinfo`, `infix_fields`, `prefix_fields` directives
- removed `attr_flush_period`, `hit_format`, `hitless_words`, `inplace_XXX`, `max_substring_len`, `mva_updates_pool`, `phrase_boundary_XXX`, `sql_joined_field`, `subtree_XXX` directives
- removed legacy id32 and id64 modes, mysqlSE plugin, and `indexer --keep-attrs` switch

And last but not least, the new config directives to play with are:

- `docstore_type`, `docstore_block`, `docstore_comp`, `docstore_cache_size` (per-index) let you generally configure DocStore
- `stored_fields`, `stored_only_fields`, `hl_fields` (per-index) let you configure what to put in DocStore
- `kbatch`, `kbatch_source` (per-index) update the legacy k-lists-related directives
- `updates_pool` (per-index) sets vrow file growth step
- `json_packed_keys` (`common` section) enables the JSON keys compression
- `binlog_flush_mode` (`searchd` section) changes the per-op flushing mode (0=none, 1=fsync, 2=fwrite)

Quick update caveats:

- if you were using `sql_query_killlist` then you now _must_ explicitly specify `kbatch` and list all the indexes that the k-batch should be applied to:

    sql_query_killlist = SELECT deleted_id FROM my_deletes_log
    kbatch = main

# or perhaps

# kbatch = shard1,shard2,shard3,shard4

## Copyrights

This documentation is copyright (c) 2017-2020, Andrew Aksyonoff. The author hereby grants you the right to redistribute it in a verbatim form, along with the respective copy of Sphinx it came bundled with. All other rights are reserved.
