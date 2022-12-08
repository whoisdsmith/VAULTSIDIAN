# IFTTT like a boss

Now i don’t know about you but when i’m choosing a smart device these days if it‘s not’ HomeKit compatible then it needs to have the [IFTTT](http://ifttt.com) badge on the box otherwise there’s no chance it will be coming home with me.

I’ve been using IFTTT applets for many years now to connect camera motion to security lights, tweets to slack, [flic buttons](https://flic.io) in my car to talk to my [particle mesh](https://www.particle.io/iot-hardware/) to control things like my garage door.

But one thing that it has really lacked is the ability to nest IFs or set conditions to the applets. A good example of this is the Flic button controlling the garage door, well anyone could press it if they gained access to my car and open the door unless you had some sort of condition that said “if **button pressed** toggle **Particle Photon** when **My iPhone is connected** to **my router**”.

Well now with the IFTTT Pro plan you can do that and i’m going to show you how.

![](https://miro.medium.com/max/2100/1*FTd-GTamMypgJJkCFDx3nA.png)

# Subscribe to IFTTT Pro

First you’re going to need to cough up some cash and subscribe to the [IFTTT Pro](https://ifttt.com/plans) plan at the moment you set the price from $1.99 USD to $9.99 USD in NZ that’s $15 which is too much and as a Yorkshireman i naturally went for the minimum.

![](https://miro.medium.com/max/2100/1*9nvoS43bT7Pg2cQgMwfEwg.png)

This gets you unlimited multi-step applets as apposed to the free version which is now limited to 3 applets and the classic single step.

# Create your applet

So let’s take my example and set up a button that opens my garage with some conditions that need to be met.

> Upon writing this tutorial it turns out [TP-Link](https://ifttt.com/tplink_router) have **discontinued** support of IFTTT which is the only reason i bought their Mesh Router >:( so that will be going back to the shop.

Inlight of this we’ll change our applet to be **time** dependent.

**Trigger service: **[Flic](https://ifttt.com/flic)  
**Trigger:** Outlander button is clicked

**Action service: **[Particle](https://ifttt.com/particle)  
**Action:** Toggle Open Close function

When you choose a trigger you’ll notice there are two new options available, **Add Query** and **Add Filter** the latter option is disabled until you choose your next action which is a little counter intuitive. The query lets you choose an additonal service that provides you parameters you can use in your filter.

> Adding a filter is a little more complex as you’ll need to write a little [Javascript](https://www.w3schools.com/js/) code

Adding a filter is a little more complex as you’ll need to write a little [Javascript](https://www.w3schools.com/js/) code again i think this is a little counter intuitive given the rest of it is point and click.

![](https://miro.medium.com/max/2100/1*xZCFS18nSqdfO1vtmLcYhA.png)

So I only want my button to work around the time I get home from work so we need to tell our applet to skip the action at all other times.

i.e if the current hour is earlier than 4pm (<16) or 6pm or later (> =18) then skip the proceeding action _which in my case is the particle call_.

Now we can publish our applet and when the time hits 4pm-6pm our button will work and any other time it won’t!

Happy creating (:


___

#article #ifttt