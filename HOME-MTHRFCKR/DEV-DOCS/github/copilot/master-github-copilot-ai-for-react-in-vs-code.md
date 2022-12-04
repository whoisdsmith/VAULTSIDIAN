# Master Github Copilot AI for React in VS Code

---

![](https://miro.medium.com/max/1400/1*pWO8ioHkpjHz9_QU4Gbkvg.png)

---

## Is AI Pair Programming the Future?

---

A few weeks ago [Github](https://github.com/) announced a state-of-the-art, AI-based pair programmer beta extension for [VSCode](https://code.visualstudio.com/) which shook considerably the software development industry. While many were concerned this AI tool will take our jobs this is definitely not the case **yet**. This past month I’ve been testing [Github Copilot](https://copilot.github.com/) in many projects mainly JS and both on the frontend, backend, and also for other more uncanny tasks.

![](https://miro.medium.com/max/1400/1*Ck5ojjZYFPIqnkHB3DtxkQ.jpeg)

## 1. How It Works

---

Once you have registered for the beta program, you will get a notification you are eligible to test the extension and gain access to it via the [VSCode Extension Marketplace](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) after that you are pretty much good to go. Now, whenever we write some code the extension will give a suggestion on how to complete the line in a light gray tint and we can press `Tab` to accept it.

---

![](https://miro.medium.com/max/1400/0*qusI3NWFcdVZpOjG.png)

---

Another way to use the extension is by writing comments and having the [GPT-3](https://openai.com/blog/openai-api/) powered mammoth hog your resources to generate a common interview question solution such as how to invert a binary tree😋.

---

![](https://miro.medium.com/max/1004/0*cxadMaPGwQsoAg_f.png)

---

But what if we don’t like the suggestion, by pressing `CTRL + Enter` a tab with 10 complete suggestions (not one-liners) appears on the right side.

---

![](https://miro.medium.com/max/1400/0*U4BeFer7Q3IitlaZ.png)

---

It’s incredible how fast you are able to generate lines of code to solve simple tasks such as fundamental algorithms or even more specialised tasks.

## **2. What It Can Do**

---

We saw in the previous examples that it’s pretty great at responding to interview questions hopefully making them obsolete in the future since I still haven’t reversed a linked-list nor inverted a tree in production.

**Answer interview questions & solve simple algorithms**

Let’s test it with some [LeetCode](https://leetcode.com/) (an amazing platform for learning algorithms and getting ready for interviews) questions such as

> Merge two sorted lists (Easy)

![](https://miro.medium.com/max/1400/1*MhE_7g2RMJfUlSDJNaFjVw.png)

> Add two numbers (Medium)

![](https://miro.medium.com/max/1400/1*MhE_7g2RMJfUlSDJNaFjVw.png)

For hard difficulty questions, the copilot doesn’t always hit the home run but it does give some decent suggestions.

> We can say Github Copilot is great at algorithms

**Complete parentheses**

This may seem pretty hilarious but one use-case I found copilot really good at is at adding the final parentheses and brackets for map functions in JSX. Everyone loves React and all but the amount of brackets you have to handle sometimes is awful.

Who would have thought we would have an AI save us from bracket hell 👿.

![](https://miro.medium.com/max/1400/0*NETdzuWWXYlbgmdf.png)

> We can say Github Copilot is acceptable at ending lines

**Create API endpoints**

One thing to note is that Github Copilot like other AI-powered tools for code auto-completion ([Tabnine](https://www.tabnine.com/) & [Kite](https://www.kite.com/)) benefits from a larger codebase as it learns from it.

If we want a brand new server in [GO](https://golang.org/), (I always promised myself to learn this incredible performance and future proof language) we get this suggestion:

![](https://miro.medium.com/max/1400/1*3NSi_p1x-HeEKeQnTM75TQ.png)

I have no knowledge of GO yet but this looks like a good start for a simple server.

Let’s try this on a [Realworld implementation](https://github.com/lujakob/nestjs-realworld-example-app/tree/prisma) using [Nest.js](https://nestjs.com/) and [Prisma](https://www.prisma.io/) as ORM.

![](https://miro.medium.com/max/1400/0*16PAYBTLKQmkOfoG.png)

Copilot knows to use a deleteAll method from TagService (although it doesn’t exist). Let’s see if it suggest it if we go to TagService.ts

![](https://miro.medium.com/max/1400/0*z1Z8HEtIP-xqEM3N.png)

Not really but still a valid guess.

> We can say Github Copilot is decent at backend

**Generate Values**

I want to create an array with all states of the US to use in a dropdown. I’m very bad at geography and not native to the US and our AI friend comes to the rescue:

![](https://miro.medium.com/max/1400/1*EsY0ZYvw09oiS6-AWLUY7g.png)

Honestly, I have no idea if those are correct or not which is a general downside of Github Copilot as it doesn’t validate whether the code works or not or its source.

I have to write some placeholder values for a list of place cards since the API endpoint isn’t ready yet:

![](https://miro.medium.com/max/1400/1*2tz0ZymqDKvWImLRWla7kA.png)

> We can say Github Copilot is decent at generating values

**Generate SQL**

SQL is really tedious to write and designing a database sometimes requires a bit of imagination, what if we ask Github Copilot to design a database for a CryptoTrading platform since AI and blockchain should become friends as the top technologies of 2021.

![](https://miro.medium.com/max/1400/1*gx311pjwjMU4lMcs6RnLHQ.png)

This is a great first suggestion from Github Copilot. What if we ask him to add a Wallet and User tables to see if it uses a foreign key with the previous code.

![](https://miro.medium.com/max/1400/1*kD6J-iMcP47EeIDmn69YrQ.png)

Although it’s not finished it’s an unbelievable amount of decently well-designed fields in a crazy short span of time.

> *We can say Github Copilot is great at simple SQL*

**Write ‘good’ copy**

What if we want to write a blog post every day and we are really really bad or slow at writing.

![](https://miro.medium.com/max/1400/0*7Tjp7rrdw_pwI2Yn.png)

Damn this AI is really narcissistic but unfortunately not great at writing markdown, but it’s not at all what it was designed to do.

![](https://miro.medium.com/max/1400/0*32HLXklp-6Xx4DlN.png)

> We can say Github Copilot is not great at Blogging

## 3. Should You Use It

In my opinion, Github Copilot is a great tool to add to your productivity workflow although is far from complete and requires some performance improvements.

Many consider AI to be the bane of developer existence but it’s a long way until that even becomes a possibility, in the years to come even if AI becomes more and more competent at writing code this will not cause our jobs to become extinct but to evolve and change.

Right now it’s nothing more than a glorified autocompletion tool with extra ‘StackOverflow integration’ capabilities so there’s nothing to worry about.

My final advice is to use it as a fun tool not to depend on it, also there may be some legal issues due to the AI being trained on all public repositories no matter the license which is a rather sensible topic, so using it for production may be undesirable for the long term.

> I hope you enjoyed this tutorial of what Github Copilot can do and would love if you put a 💜 on it!

*More content at* [***plainenglish.io***](http://plainenglish.io/)
