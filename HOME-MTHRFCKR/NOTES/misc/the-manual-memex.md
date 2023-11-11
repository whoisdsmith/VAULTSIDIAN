# The Manual Memex

```
David Alan Grier, Djaghe, LLC
```

## Here We Introduce a New Column that Explores

## Computer’s Contribution to the Computing

## Literature and how it is Laying the Foundation for

## The Future of Computer Science and Engineering

```
Digital Object Identif ier 10.1109/MC.2019.
Date of current version: 15 Januar y 2020
```

```
JANUARY 2020 79
```

### EDITOR DAVID ALAN GRIER

```
Djaghe, LLC; grier@gwu.edu
```

of the computing literature: the IEEE  
Computer Society Digital Library  
and IEEE Xplore as well as the digital  
libraries of the Association for Com-  
puting Machinery (ACM), Elsev ier,  
Oxford University Press, Springer,  
and the American Mathematics  
Society.  
As I found more of those articles, I  
speculated that it might be useful to  
write a column called “Exploring Our  
Digital Libraries,” but that idea seemed  
too unfocused. Few people go explor-  
ing without a clear goal, such as finding  
the Northwest Passage, discovering the  
gold mines of the Incas, or locating the  
Fountain of Youth. Instead, I thought it  
might be useful to implement a manual  
version of another old idea, Vannevar  
Bush’s Memex.^1  
The Memex was a speculative de-  
vice that Bush created to suggest how  
we might mechanize the problem of  
organizing knowledge, searching lit-  
eratures, and identifying ideas. It has  
rightly been identified as part of the in-  
spiration for the World Wide Web. But  
if we claim that it is a distant fount of  
web servers, uniform resource locators,  
and HTML, we slide back into that nar-  
row world in which we can only see our  
work and believe that everything leads  
to the point where we stand today.  
In fact, Bush had only a vague sense  
of how the Memex might work and  
could merely speculate about how we  
might build such a machine and feed  
the existing body of knowledge into it.  
However, he had a very clear sense of  
the problem the scientific community  
was facing. “The investigator is stag-  
gered by the findings and conclusions of  
thousands of other workers,” he wrote,  
“conclusions which he cannot find time  
to grasp, much less to remember, as they  
appear.” This problem, he noted, was  
caused by the trend toward specializa-  
tion, of the natural tendency for work-  
ers to limit the scope of their inquiry.  
Specialization “becomes increasingly

```
necessary for progress,” he added, “and
the effort to bridge between disciplines
is correspondingly superficial.”
So, in this column, I am going to
try to expand the bridge between
disciplines and widen the scope of our
horizons. I will going to look at the
some of the key contributions of Com-
puter and how they have shaped our
present landscape. The effort will not
be as broad as I might like, and it will
certainly be more manual activity than
Bush proposed, but it will strive to ex-
pand our understanding of the current
state of computer science, computer en-
gineering, and related fields. It should,
if I do it properly, also f ulf ill that goal
of my early editor, which was to get me
to predict the future. If we understand
the current state of the field, we will
be better able to peer a little way into
the future.
Our starting point for this first col-
umn will be the June 2019 issue on
quantum computing. It was one of the
best issues that we published last year.
The guest editor, Erik DeBenedictis, did
a terrific job of recruiting solid articles
on the subject and painting a very rich
picture of the state of quantum comput-
ing: what it could and couldn’t do and
the likely areas for progress. The issue
identified matters that may be prob-
lems for years to come, including noise
and leakage as well as scaling. It argued
that we should be able to see some suc-
cessful specialized processors, such as
the D-Wave, but that the prospects for
a general quantum computer were still
uncertain. If you have not read the issue,
I recommend it to you.
If we are looking to outline the field
of quantum computing, we jump to the
article that is generally identified as
the founding document, the 1985 work
by David Deutsch, “Quantum Theory,
the Church-Turing Principle, and the
Universal Quantum Computer.”^2 The
article is remarkably prescient and
outlines ideas that are still current in
```

```
the quantum literature. But if we cling
to it as the starting point of the field,
we are merely backing the origin of
our work. Papers on quantum comput-
ing didn’t start to appear in the IEEE
literature until approximately 1995 (or
1994, if you look at the ACM library).
One of these early papers is central
to the quantum-computing literature.
It is the article by Peter Shor on how
quantum computing would be able to
factor large numbers and, hence, might
provide a way of compromising pub-
lic-key cryptography.^3 As was common
in most of the early quantum literature,
the article appeared in a specialized
publication rather than Computer. The
specialized publications tend to get the
earliest papers in any field, and they are
edited by more coherent communities
that can best understand and evaluate
new work. By its nature, Computer is a
general-purpose professional publi-
cation. It is a member benefit to indi-
viduals who belong to the IEEE Com-
puter Society, and, hence, its content
needs to be accessible to a wide range of
professionals.
Perhaps Computer’s most important
early paper on quantum is the 2002
article “A Practical Architecture for Re-
liable Quantum Computers,” by Marc
Oskin, Frederic Chong, and Isaac Ch-
uang.^4 To date, it has been cited by 60
papers, 19 articles in IEEE publications,
and 41 articles from other publishers. In
addition, it has been cited by three pat-
ent applications.
Now, this is where we embrace the
manual aspect of our work and move
away from Bush’s efforts to mechanize
the organization of scientific litera-
ture. We have created many ways of
quantifying the importance of a sin-
gle article, and all of them are prob-
lematic. For example, one of the most
highly cited articles of the past half
century is Martin Fleischmann and
Stanley Pons’s “Electrochemically In-
duced Nuclear Fusion of Deuterium.”^5
```

**80 COMPUTER** WWW.COMPUTER.ORG/COMPUTER

## BODY OF KNOWLEDGE

That paper claimed to demonstrate  
that hydrogen atoms could be fused  
into helium at room temperature, an  
assertion that was quickly proven to  
be false. Hence, we will be misled if we  
read the large number of citations as  
evidence that the paper is important  
within the field of physics. It has been  
important but not in the way that the  
number of citations might suggest.  
The citations for “A Practical Archi-  
tecture for Reliable Quantum Comput-  
ers” show that the ideas from the article  
moved quickly into the computer-archi-  
tecture community. Most of the cita-  
tions are from conferences, which tend  
to be populated by active researchers.  
The citations suggest that the article  
opened a field of inquiry. In general,  
papers do one of four things. They open  
fields of research, redirect their fields,  
combine two fields, and close fields.  
Those that open fields articulate a series  
of ideas, concepts, and processes and,  
then, show how those elements can be  
used to solve problems.  
The lead author, Mark Oskin, re-  
ported that the field “was still novel”  
when he wrote the article. At the time,  
he was a young graduate student at the  
University of California, Davis, “more  
or less finished with my Ph.D. research  
but waiting for the academic job cycle  
to start.” He had seen an early quan-  
tum device, a bulk-spin computer built  
by Isaac Chuang from IBM. Chuang  
was a friend of his Oskin’s advisor,  
Fred Chong. The three would become  
coauthors of the article.  
Their work focused on the architec-  
ture that would lead to reliable quan-  
tum computers. “The nonlocalized  
properties of quantum states,” the pa-  
per noted, “means that localized errors  
on a few qubits can have a global im-  
pact on the exponentially large state  
space of many qubits.” The nature of  
this problem suggested that error cor-  
rection needed to be handled on a sys-  
tem-wide level. “Unlike classical sys-  
tems, which can perform brute-force,  
signal-level restoration error correction

```
in every transistor, quantum-state error
correction requires a subtle, complex
strategy.” The article concludes, “While
theoretically possible, quantum error
correction introduces overheads yet un-
heard of in the classical domain.”
For the most part, the article seems
to have had a positive reception. Oskin
recalled that much “to our surprise and
delight, it inspired other researchers
to take up the topic.” The fundamental
lesson of the article was that “quantum
error correction has enormous over-
heads when implemented in practice.”
It wasn’t going to have the capacity to
break public-key codes “anytime soon.”
Oskin did acknowledge that a few re-
viewers were not quite able to make sense
of the ideas in the article. He remembered
that a reviewer from one of the top archi-
tecture journals described it as “mediocre
science fiction, at best.” Reviewers can
regularly miss important ideas, especially
when a field is young. The three coauthors
took the criticism in stride. “We found the
review so hilarious we had T-shirts made
with that quote on it.”
We limit our understanding of early
papers if we just view them as merely
defining a basic set of ideas used by sub-
sequent authors. If we look at the papers
that cite “A Practical Architecture for
Reliable Quantum Computers,” we can
see the subtle inf luence that early pa-
pers wield. They give ideas that can be
used to solve problems, and they sug-
gest problems that might be interest-
ing to attack. “If you look at the recent
focus,” Oskin observed, “it has been
on algorithms that do not rely on error
correction and technologies that may
be more naturally error tolerant and/or
with lower overhead.” Such algorithms
are part of the substantial progress that
architecture has made in recent years.
“A Practical Architecture for Re-
liable Quantum Computers” is part
of the body of knowledge that Com-
puter has helped create. That corpus
has a distant foundation in a physics
journal, spreads across several archi-
tecture conferences, has important
```

```
contributions in processor and micro-
electronics journals, includes several
mathematics papers, and even has
a connection to Acta Astronautica, a
journal for articles about space explo-
ration. The digital libraries can guide
us through this literature and provide
some of the mechanical connections
that Bush desired to see. However, the
real body of knowledge is not made
of mechanical links. It consists of au-
thors like Oskin and coauthors, the
editors who review articles (including
editors who misunderstand the ideas),
all the readers who found something
useful in these articles.
```

```
REFERENCES
```

1. V. Bush, “As we may think,” Atl.  
    Mon., vol. 176, no. 1, p. 101, July 1945.
2. D. Deutsch, “Quantum theory, the  
    Church-Turing principle, and the  
    universal quantum computer,” Proc.  
    R. Soc. A Math. Phys. Eng. Sci., vol.  
    400, no. 1818, pp. 97–117, July 1985.  
    doi: 10.1098/rspa.1985.0070.
3. P. W. Shor, “Algorithms for quantum  
    computation: Discrete logarithms  
    and factoring,” in Proc. 35th Annu.  
    Symp. Foundations Computer Science,  
    Santa Fe, NM, 1994, p. 124. doi:  
    10.1109/SFCS.1994.365700.
4. M. Oskin, F. T. Chong, and I. L.  
    Chuang, “A practical architecture  
    for reliable quantum computers,”  
    Computer, vol. 33, no 1, pp. 79–87, Jan.
5. doi: 10.1109/2.976922.
6. M. Fleischmann and S. Pons,  
    “Electrochemically induced  
    nuclear fusion of deuterium,” J.  
    Electroanal. Chem., vol. 261, no.  
    2, pp. 301–308, Apr. 1989. doi:  
    10.1016/0022-0728(89)80006-3.

```
DAVID ALAN GRIER is a principal
with Djaghe, LLC. He is a Fellow
of the IEEE. Contact him at grier@
gwu.edu.
```
