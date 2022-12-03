# When “if” is not enough: Superpowers for IFTTT
Integromat

[IFTTT](https://ifttt.com) is a wonderful tool and for those who understand how to use it, it quickly becomes an essential helper. The massive number of integrations with services (currently over 300) has turned it into an unique communication middleware for the cloud (also known as “glue” or “duct tape”).

But powerusers who are used to push the envelope and optimize their recipes might soon run into a limitation that is not obvious in the beginning: **You cannot combine the information from multiple channels to make smarter recipes.**

Let’s say you want to switch on the lights in your house if it gets dark and you are not home (for the purpose of keeping burglars away). Or you want to save energy and skip heating up your room early in the morning if the weather forecast expects a warm afternoon anyway.  
There is no way to make these kind of recipies on IFTTT today and many posted a feature request for this — because it can’t be so difficult to implement, right?

Wrong. What looks like an easy task at first turns out to be a bit complicated when you look closer. Here’s the thing: By nature, events on two IFTTT channels practically never occur at the same time. And since data on IFTTT is very short lived (it vanishes right after a recipe is finished) each recipe is isolated from the rest and has no clue what happened in the past.  
In short, IFTTT is missing two elementary concepts of programming languages in order to be able to combine multiple channels:  
1\. Persistence  
2\. Conditional statements with multiple conditions

## The Idea

When experimenting with some IoT-hardware I heard about the [IFTTT Webhooks Service](https://ifttt.com/maker_webhooks) (originally called “Maker Channel” back in the days) and started using it. Webhooks can be used in IFTTT applets like any other service. What makes it different from the rest is that it’s not tied to a specific cloud service but offers a generic webservice interface that can recieve and make HTTP requests.  
**Soon after, I had the idea to use the Webhooks to loop in not a device, but a web application which offers persistence and advanced conditional statements**— exactly what’s missing in IFTTT.

![](https://miro.medium.com/max/1400/1*UxawNCWN9WTNTkg4rZJFBA.png)

How Apilio integrates with IFTTT

## The Result

So I started a project and set out to create [apilio.io](http://apilio.io), which is online since a few months and has served me very well and reliably. I’m not sure which technical term describes it best, so I like to call it “Logic as a Service”.

_Editors note: A lot has happened since I wrote this article! To find out how the “project” developed since then, read the follow-up article __[4 years of smarter home automation thanks to Apilio_](/@pebneter/4-years-of-smarter-home-automation-thanks-to-apilio-33a148409a37)_._

The usage pattern of Apilio is twofold:

  * Setup phase: Use the apilio.io web interface to setup variables and conditional statemenets.
  * Usage phase: Set variable values and trigger evaluations of the conditional statements via the web API.

In the **setup phase** you use the web interface to build and test the conditional statements.

![](https://miro.medium.com/max/1400/1*4i0xxfdmhZX1gNimNE5uug.png)

The building blocks in Apilio to define conditional statements

In the **usage phase**, Apilio interacts a lot with the IFTTT Webhooks Service and can therefore interact with anything that connects to IFTTT. Thanks to this, you can now combine input from devices and services (that would not speak to each other otherwise), make smart decisions and trigger actions.

Apilio does for instance give me a hint in the morning when it is [wise to pick up the umbrella](http://www.apilio.io/umbrella-butler.html). I used it to build an simple [home security system with my Netatmo Weather Station](http://www.apilio.io/simple-home-security-system.html) (and I can activate it on my Apple Watch!). And most importantly: It helped me gaining the [Swarm](https://www.swarmapp.com) mayorship in my office be reminding me every workday if I forgot to check in :-).

## Your Turn

The possibilities are endless, since Apilio is a toolbox — like a very simple programming language. Many users use Apilio to automate the lights, to control the air conditioning or to close the garage door at night if it was left open.  
The downside of the flexibiliy: Apilio is not optimized for the non tech-savy users (but that will hopefully change sometime). Give [apilio.io](http://apilio.io) a try and send me your feedback. I’m looking forward to hear about your ideas!

_Updated January 5th 2018 to reflect the renaming of the “Maker Channel” to “Webhooks Service”._


___

#article 