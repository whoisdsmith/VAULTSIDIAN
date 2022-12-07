# A Context-based Information Refinding System-

## A Review

Abstract- In recent technological development people are  
experiencing unprecedentedly data explosion, reading, writing,  
and collecting different kinds of information from local  
computer and the global Web. As such most of the times  
during web search peoples revisit information that have ever  
been come across occasionally or intentionally. But in most of  
the cased users do not know enough information, while  
refinding is a more directed process as users have already  
seen the information before. A general way to support  
information refinding is to maintain access logs, recording  
what users have ever seen based on their revisit frequencies.  
This survey paper gives the different techniques for context  
based information refinding systems with intent to give the  
direction of the my project work with improved context based  
information refinding system.  
_Keywords: information refinding, context cue, refinding  
queries._

### I. Introduction

he World Wide has been dramatically increased  
due to the usage of internet. The web acts as a  
medium where large amount of information can be  
obtained at lower cost. Web mining can be defined as  
the discovery and analysis of useful information from the  
World Wide Web data. It is one of the data mining  
techniques to automatically extract the information from  
web documents. WWW provides a rich set of data for  
data mining. The web is dynamic and very high  
dimensionality. A web page contains three forms of  
data, structured, unstructured and semi structured data.  
Data sets available in the web can be very large and  
occupy ten to hundreds of terabytes, need a large farm  
of servers. The user are collecting different kinds of  
information from the global web for both read and  
writing purpose. In the global web, search is an  
important activity then only considered to an email.  
Tremendous growth of web, every second millions of  
information added in the global web. Users are finding  
and refinding the web information in the global web  
everyday \[9\]. People revisit the information that have  
ever been come across occasionally or intentionally.  
Refindng web pages is typically better than to initially  
finding the webpage. Achieving efficient and accurate  
information retrieval is a challenging task. Refinding is a  
common task is difficult when previously viewed  
information is modified, moved or removed. How

_Author α σ ρ: CMR Institute of Technology Hyderabad  
e-mail: riyazsidd@yahoo.co.in._

```
information refinding is different from information
finding? There is a uncertainty in the later process
because users do not know get enough information,
while information refinding is a more directed process as
users have already seen the information before.
Information refinding is not the process of finding again
[7]. A general way to support information refinding is to
maintain access log[10], recording what users have ever
seen based on their revisit frequencies. When refinding,
users might prefer to have a search the results
prioritized by pages that have been seen before. One
way to refinding the information using contextual cues
[3][2], inspired from the human memory approach.[8].
```

```
The people use lot of keywords to search the
information. To remember the keyword after a few
months ago what we have seen before it is difficult and
time consuming task. Because original queries were
wrongly remembered most of that time due to their loss
of memory. According to cognitive science literature,
human memory is predicted on contextual cues to
refinding the information.
To get the information for users query exactly
even a month or year ago hard to remember that
keyword. But the time, place and concurrent activity
associated with the happening of that access event may
leave a deeper impression. Contextual information could
helps as powerful clues to remember the key word.
Contextual clues helps to users have seen the already
viewed information.
Nivethitha (2014) suggested a query analysis for
efficient context-based information refinding and page
ranking system. Refinding what have done before is a
common behavior of human in real life. According to the
human natural recall characteristics, users allow to
refinding web pages which have seen before.
Psycological studies show under which information was
accessed can helps as a powerful cue for information
recall. Here context including time, place and concurrent
activity could serves as a useful information recall clues.
In this system not only considered finding the refinding
queries. But also implement feedback system, so that
webpage can be ranked by the multiple user feedback.
Deng et.al. (2013) have worked extensively and
suggested a effective method for refinding the
information fro m the web, they could not remember the
```

#### Global Journal of Computer Science and Technology Volume XIV Issue IV Version I

(^)  
1  
Year  
2014  
(^) (DDDDDDDD

#### )

```
G
```

#### Divya α,M.Janga Reddy σ^ &M.Riyajoddinρ

#### II. Relatedwork

#####

```
key word and their related information after a couple of
months. It based on the human recall characteristics,
allows user to refinding WebPages according to the
previous access context. The system was implemented
offering some contextual information on the query
results. Memory context is also considered in personal
information refinding. Based on Inspiration from human
memo ry mechanism, the context - based refinding
framework was developed.
Won et.al. (2009) experimented in their work and
identified that most modern web browsers offer web
history functionality few people use it to revisit previously
viewed web pages. In this paper they developed
Contextual Web history (CWH), which improves the
visibility of the history feature and greatly reduced the
time and effort required to find and revisit
webpage.CWH goal is to improve the usability and utility
of the history feature in web browsers. CWH provides a
richer set of clues about the content of the page,
including time of visit, visual appearance and text search
and quickly find previously visited web page again.
Revisiting is a key part of web browsing. Contextual web
History gives to understand the right set of basic
features to support the process of re-finding information
very fast.
```

```
Tasks Potential Memory Cues
```

```
Recall
```

```
color, structure, time visited,
logos , content, title, url of the web page
Rec ognition Size of the thumbnails
```

```
MacKay et.al.(2005) had done a detailed
analysis and present an extension to traditional
bookmarks called landmarks, a user-directed technique
that aid users in returning to specific content within a
previously visited webpage. The use of traditional
bookmarks allows users to return to a previously visited
page, it can be hard to re-find facts within that page.
Here we investigate the efficiency of land marks for
refinding of information on web-pages. Land mark allow
users to mark information on a webpage that they may
want to return to a later date by highlighting the text and
adding a landmark in the same fashion as they would a
favorite in IE. Land marks are not meant as a
replacement for the bookmarking facility but as an
enhancement that help users return directly to previously
visited information, giving context to the marked pages.
Hailpern et al. (2011) found that during recall
tasks, contextual cues are important component of
human memo ry. In this paper they present new
interaction technique, pivoting, that allows users to
search for contextually related activities and find target
piece of information. You Pivot demonstrates how
principles of human memo ry can be applied to
enhance the search of digital information. Contextual
cues could be one way to improve in formation recall in
```

```
our digital lives. You Pivot used the calendar entry’s
lifespan as the pivot time period. Time Marks allowing a
user to access all activity that was ongoing at a
particular moment.
Parsons et.al. (2009) extensively worked and
suggested a keyword-based information retrieval
technique and suggested that the performance can be
improved by re-ranking the results based on the context
provided by the surrounding terms. A baseline
technique was compared against two LSA techniques,
and an analysis of the retrieved documents indicated
that the re-ranking provided by the LSA techniques
significantly improved the efficiency of the retrieved list.
However, the participants’ performance was not altered
by the different techniques. Instead, the findings
suggest that, when dealing with a small number of
documents, participants will generally access all
documents retrieved in a systematic manner. It is
therefore hypothesised that the re-ranking technique
would be more useful in a significantly larger document
collection, where a thorough assessment of all
documents is impractical.
This study has also emphasized the importance
of assessing the impact of individual differences in any
information retrieval system. For example, it was found
that LSA did improve performance for participants with
lower scores on the comprehension test.
```

```
A Context-b ased Information Refinding System-A Review
```

##### 2

```
Year
```

```
2014
```

##### Global Journal of Computer Science and Technology Volume XIV Issue IV Version I

##### (

##### DDDDDDDD

##### )

```
G
```

```
Table : Comparison of Various Context-Based Re Finding Systems
```

Reference  
Number

```
Author Paper Title Issues Method Result
(Refinding)
```

```
Drawbacks
```

2 A.P. Nivethitha Efficient  
context based  
information re-

- finding and  
    page ranking

```
To build recall
based query
model to re-find
the information
using contextual
cues and feedback
visited by the user.
```

```
Re-finder
and page
ranking
```

```
Efficiently revisit of
the web page using
contextual cues and
multi user feedback.
```

```
All the user not
given the
feedback. So
cannot ranking
the webpage
properly.
```

3 Tangjian Deng,  
Liang Zhao, Hao  
Wang, Qingwei  
Liu, and Ling Feng

```
Refinder: A
context-based
information
refinding
system
```

```
To build query-by
context model,
Context are the
powerful cue
(place, time,
concurrent activity)
for information
refinding.
```

```
A context
based Re-
finder
```

```
On average 15.
seconds are needed
to refinder complete
the refinding request
and 84.42 seconds
with other existing
methods
```

```
In Refinder, not
implement user
feedback for
visited web
pages
```

4 S. Won, J. Jin, and  
J. Hong,

```
Contextual
Web History:
Using visual
and
contextual
cues to
improve Web
Browser
History
```

```
To develop
Contextual Web
History (CWH)
improves the
visibility of the
history feature
helps people find
previously visited
web pages.
```

```
Contextual
Web
History
```

```
Greatly reduced the
time and effort
required to refinding
the web pages.
```

```
In CWH, re-
finding a
webpage older
than x days too
many pages for
the user to
browse.
```

5 B. MacKay, M.  
Kellar, and C.  
Watters

```
An Evaluation
of Landmarks
for Re-finding
Information on
the Web
```

```
To implement
Landmark which is
an extension of
traditional
bookmarks.
Landmark is a
user-directed
technique that aids
users in returning
to specific content
within previously
visited webpage
```

```
Landmark Using Landmarks
revisit the webpage
significantly faster.
```

```
The users can
only make
landmarks for
textual
information, not
expand this
functionality to
include images
and other
media.
```

6 J. Hailpern, N.  
Jitkoff, A. Warr, R.  
Karahalios, K.  
Sesek, and N.  
Shkrob

```
You Pivot:
Improving
Recall with
Contextual
Search
```

```
To allow users to
search for
contextual related
activities (using
time marks) and
find a target piece
of digital
information.
```

```
You Pivot Using You Pivot
greatly improve the
quality and speed of
recall
```

```
Users own
contextual cues
is difficult to
design
```

7 Kathryn Parsons,  
Agata McCormac,  
Marcus Butavicius,  
Simon Dennis\*  
and Lael Ferguson

```
The Use of a
Context-
Based
Information
Retrieval
Technique
```

```
The aim of this
study was to
examine whether
the results
provided by a
keyword based
technique would
be improved
through the use of
two LSA
techniques.
```

```
Latent
Semantic
Analysis
(LSA)
```

```
This study therefore
highlights the
importance of
testing the influence
of individual
differences on any IR
system, and the
importance of
testing any IR tool on
a population
that closely reflects
the intended users
of the system.
```

```
LSA are unlikely
to be
necessary in
relatively small
document
collections
```

```
A Context-b ased Information Refinding System-A Review
```

##### Global Journal of Computer Science and Technology Volume XIV Issue IV Version I

(^)  
3  
Year  
2014  
(^) (DDDDDDDD

##### )

```
G
```

#### III. Conclusion

```
We have studied the comparison of various
papers of context based information refinding. The aim
of this study was how the results of the information
retrieval technique to efficiently refinding the web
information could be improved by contextual cues
shown in above table.
```

#### References Références Referencias

1. A.P. Nivethith, D. Kerana Hanirex, K.P. Kaliyamurthie  
    “ A Comparative Study of Context-Based  
    Information Refinding” COMPUSOFT, An  
    international journal of advanced computer  
    technology, 3 (4), April-2014 (Volume-III, Issue-IV).
2. A.P. Nivethitha “efficiently context-based information  
    re-finding and page ranking ”International  
    conference on electrical, communication and  
    computing, 2014.
3. Tangjian Deng, Liang Zhao, Hao Wang, Qingwei  
    Liu, and Ling Feng, “ReFinder: A Context-Based  
    Information Refinding System” IEEE transactions on  
    knowledge and data engineering, vol. 25, no. 9,  
    september 2013.
4. S. Won, J. Jin, and J. Hong, “Contextual Web  
    History: Using Visual and Contextual Cues to  
    Improve Web Browser History,” Proc. SIGCHI Conf.  
    Human Factors in Computing Systems (CHI), 2009.
5. B. MacKay, M. Kellar, and C. Watters, “An  
    Evaluation of Landmarks for Re-Finding Information  
    on the Web,” Proc. Extended Abstracts on Human  
    Factors in Computing Systems (CHI ’05 EA), 2005.
6. J. Hailpern, N. Jitkoff, A. Warr, R. Karahalios, K.  
    Sesek, and N. Shkrob, “You Pivot: Improving Recall  
    with Contextual Search,” Proc. SIGCHI Conf. Human  
    Factors in Computing Systems (CHI), 2011.
7. Kathryn Parsons, Agata Mc Cormac, Marcus  
    Butavicius, Simon Dennis\* and Lael Ferguson “ The  
    Use of a Context-Based Information Retrieval  
    Technique” Command, Control, Communications  
    and Intelligence Division Defense Science and  
    Technology Organization \*Ohio State University.
8. E. Adar, J. Teevan, and S.T. Dumais, “Large Scale  
    Analysis of Web Revisitation Patterns,” Proc. SIGCHI  
    Conf. Human Factors in Computing Systems (CHI),

9. R. Capra, M. Pinney, and M.A. Perez-Quinones,  
    “Refinding Is Not Finding Again,” technical report,  
    Aug. 2005.
10. Y. Chen and G. Jones, “Integrating Memory Context  
    into Personal Information Re-Finding,” Proc. Second  
    Symp. Future Directions in Information Access,

11. J. Teevan, “The Re: Search Engine: Simultaneous  
    Support for Finding and Re-Finding,” Proc. 20th  
    Ann. ACM Symp. User Interface Software and  
    Technology (UIST), 2007.  
    12. S.K. Tyler and J. Teevan, “Large Scale Query Log  
        Analysis of Re-Finding,” Proc. Third ACM Int’l Conf.  
        Web Search and Data Mining(WSDM), 2010.  
    13. Google Web History, [http://www.google.com/](http://www.google.com/)  
        history,

```
A Context-b ased Information Refinding System-A Review
```

##### 4

```
Year
```

```
2014
```

##### Global Journal of Computer Science and Technology Volume XIV Issue IV Version I

##### (

##### DDDDDDDD

##### )

```
G
```
