### Architecture

###### Q: What is the best way to connect my existing API to IFTTT?

If you already have an existing API and don’t want to modify it, we recommend a “shim” server that sits between IFTTT and your API and acts as a translator between both APIs.

###### Q: How much traffic should my API expect to see?

It’s entirely dependent on how popular your service is. Polling interval will be variable if not using the Realtime API. This means that interval between each call is not guaranteed and you should always be ready for increases and decreases in traffic.

###### Q: Why does IFTTT use a polling architecture?

Take an Applet in the form of “IF Door Opened, THEN Add Row to Spreadsheet”.

If IFTTT or your API experienced a period of downtime, any events during that period could be missed and not logged to the spreadsheet. With a polling architecture, IFTTT can pick up where it left off by requesting a list of recent events that it might have missed.

To ensure a great Applet experience for your users, triggers are required to use the Realtime API if a user would expect its Applets to run in realtime.

###### Q: How often will IFTTT poll my server?

IFTTT polling for each Applet varies based on the past several times that Applet has run. This period can increase or decrease without notice and should never be considered guaranteed. If you want IFTTT to fetch new data from your service as it becomes available, you're encouraged to use the [Realtime API](https://ifttt.com/docs/api_reference#realtime-api).

###### Q: How often will IFTTT poll my user information endpoint?

IFTTT makes requests to the user information endpoint about once every seven days to verify that the user’s access token is still valid. If issues are detected with the access token, IFTTT will poll more frequently. If the issues continue after fifteen checks across a span of two weeks, that user's Applets will be disabled.

### Triggers

###### Q: Can you explain how triggers work with regards to my API?

A trigger’s response can be thought of as a timeline of events.

A trigger endpoint should return (by default) up to the 50 most recent _events_, regardless of whether or not we have seen them before. The number of returned items can be overriden by us by specifying a `limit` parameter in the request. Please do not limit the number of events returned except as specified by the `limit` parameter in the request. Events should remain on the timeline indefinitely and should not expire, although they may roll off the bottom of the list once the timeline exceeds 50 items.

You define the fields for this query (called trigger fields). Users supply values for these trigger fields when they create an Applet. At regular intervals, we contact your API and query you as if to ask, “which events have recently occurred for these trigger field values?” You return us an ordered list of recent events, and we’ll act upon any new events we see.

The logic of how you determine which events to return for a given query to your API is entirely up to you— IFTTT will simply look at your results and trigger an Applet if it sees anything it hasn’t seen before.

###### Q: My service fails the `returns at least three items` endpoint test. Why does IFTTT require three items?

We require three items during the testing phase to make sure your API behaves like a timeline of events, not a state engine.

This requirement might seem strange when you think of your integration with IFTTT as something that is entirely realtime in nature, like “IF Button Pressed, THEN Turn On Lights”— what good would come from anything but the current state of the button?

But what about the Applet “IF Button Pressed, THEN Log to Spreadsheet”? In this case it would be important to store and return multiple event items because there is no guarantee that we’ll call your API (even with the Realtime API) at the moment the event occurs.

By keeping and returning a list of events, IFTTT users are more assured they won’t miss a thing.

###### Q: When I return multiple events in my trigger endpoint, how does IFTTT know which ones are new?

When you implement your [trigger](https://ifttt.com/docs/api_reference#triggers) endpoint you send us a `meta.id` value with a unique ID for each event. IFTTT will keep track of which IDs it has seen in the past and only trigger for new IDs it hasn’t seen before.

###### Q: Is it possible for my API to know when an Applet is created or deleted?

Not quite, but it is possible to get extremely close by taking advantage of our [trigger identity](https://ifttt.com/docs/api_reference#trigger-identity) functionality. With every trigger request to your API we will include an identifier that uniquely identifies the contents of a trigger in an Applet. If it’s the first time you’ve seen this trigger identity, you can assume a user has created a new Applet with the given field values.

If a user deletes or disables an Applet and no other Applet shares the same trigger and field values, we will notify your API that the given trigger identity is no longer in use.

It’s important to note that a trigger identity doesn’t necessarily represent a single Applet (although it can), but rather represents every Applet that shares the same trigger and field values.

### Actions

###### Q: Are identical actions possible when using multiple actions?

When [creating an Applet](https://platform.ifttt.com/mkt/%2Fapplets%2Fnew), it's not currently possible to add multiple instances of the same action. Each action must be unique.

### Realtime API

###### Q: How does your realtime API work? How do I tell IFTTT what to trigger?

You call our [Realtime API](https://ifttt.com/docs/api_reference#realtime-api) with one or more user IDs or [trigger identities](https://ifttt.com/docs/api_reference#trigger-identity) and we’ll immediately poll your API for all relevant trigger events. If you provide a user id, we’ll poll for all of that user’s triggers; if you provide a trigger identity, we’ll only poll for the triggers that share that identity.

### Authentication

###### Q: Do I have to use OAuth2? I have an alternate strategy I’d like to use.

Currently OAuth2 is the only authentication mechanism we support. In the future we may support other methods, but there are currently no firm plans in place.

###### Q: Why does my API fail the ‘Ensure older refresh token does not expire immediately’ test?

The process of making the refresh token network request, waiting for the response and writing it to our database is inherently non-atomic.

To illustrate a scenario where this could be a problem: you receive our request, expire the token at that moment, but the token never makes it back to us. We now have a situation where the refresh token is invalid.

Because IFTTT users expect Applets to run in the background, it is difficult to notify them and ask to re-authenticate. By requiring that refresh tokens don’t expire immediately we allow ourselves a small window to re-request a new token if for some reason it doesn’t make it to our database.

### Reviews and Publishing

###### Q: What’s the review process with IFTTT?

IFTTT does an internal review process before a service can be pushed into production. This process can take anywhere from one to two weeks depending on when we receive your submission and how much feedback we have.

###### Q: My service has been approved — how do I publish?

Once your service has been approved, we'll send you an email asking you to fill out the prelaunch marketing form. In this form we'll ask for the date in which you'd like the service to be published on IFTTT. Before your service is published, we'll do a final review to make sure that the service's endpoint and authentication tests are passing, and that you have at least twelve published Applets available for users to add.

###### Q: What happens if I need to make changes to my service after it is published?

Some minor updates can be made directly in the platform. For example, you can update [your service description](https://platform.ifttt.com/mkt/general) at any time.

To make more substantial changes (ex. new queries, triggers, or actions), [clone your service](https://platform.ifttt.com/mkt/tools), make any necessary changes, and then submit that service for review.

Keep in mind that your production service should avoid major modifications during this process and that any potential breaking changes should be made to a separate development or staging service first.

###### Q: I've cloned my service to make some changes, I can see "staging" added on my service name and slug, should I remove this?

There is no need to remove staging from your service's name or slug. This will not be included in the migration once it is reviewed and completed. We will keep your production service name and slug intact.

###### Q: What happens if I change my OAuth configuration? Would the users be alerted?

After the service has been migrated and you've made changes to your authentication, users who have not yet authenticated with the new OAuth configuration will go offline. Affected users will get automated e-mail and push notification to re-authenticate the service.

### IFTTT Platform Plans

###### Q: What plans are available and what are the main differences between them?

IFTTT offers one free and three paid plans that provide tools to developers and businesses. Each plan unlocks additional features that provide greater flexibility, sophistication, exposure to the ecosystem, and insights than the previous.

The Free plan provides access to core IFTTT Platform developer tools so you can get started building services without an upfront commercial commitment. When you’re ready to publish your work and make it available to others, you’ll need to upgrade to one of the paid plans.

With the Developer plan, you may publish x1 branded service for the world to use. A service is an extension of your product’s API and can include triggers, actions, and queries for users, developers, and companies to interact with.

The main difference between the Developer plan and the Team and Enterprise plans is their ability to build, publish, and embed simple Applets or powerful connections directly into a mobile app, email, and website. The Developer plan does not allow you to publish Applets or embed connections using IFTTT SDKs.

The Enterprise plan is designed for companies with multiple products, enterprise service requirements, or in-depth data analysis and business insights for marketing teams.

###### Q: I’m on the Free plan. Why should I upgrade to the Developer plan?

IFTTT offers a Free plan for casual developers to create services and personal Applets, but you cannot publish them for users to discover and consume. Upgrade to the Developer plan or higher if you would like to publish your service on IFTTT.

###### Q: What are the limitations of the Developer plan?

The Developer plan does not allow you to publish Applets, connections, or embed IFTTT-powered features into your own applications, websites, or emails using IFTTT SDKs. The Developer plan also has limited analytical insights and customer support services.

[Upgrade to the Team or Enterprise plans](https://ifttt.com/plans) if you would like the ability to publish your service and embed branded connections for your customers to use.

###### Q: What happens if I downgrade or cancel my account?

Depending on which plan you downgrade to, your services and Applets may become inaccessible to your customers. We’ll work with you to help you plan accordingly. If you cancel your subscription entirely, your services and Applets will be archived and no longer available for anyone to consume.

###### Q: How do I know which plan is best for me?

[Please review the comparison chart](https://ifttt.com/plans) to help determine which plan you should subscribe to. Or you may [reach out to speak with us](https://ifttt.com/contact_sales) directly about your needs, your products, where your customers engage, and we’ll help determine the best fit for you.

---
#Ifttt 