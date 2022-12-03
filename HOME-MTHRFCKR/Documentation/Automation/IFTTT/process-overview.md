Before you begin building anything, you should first get acclimated with how IFTTT works to understand the user experience. Below is a short introduction and we'll cover these topics in more detail later on in this guide.

If you already know how IFTTT works, you can [skip ahead](https://ifttt.com/docs/process_overview#1-plan-your-integration).

### Services

Services are the basic building blocks of IFTTT. Some examples of services are [Amazon Alexa](https://ifttt.com/amazon_alexa), [Twitter](https://ifttt.com/twitter), [Dropbox](https://ifttt.com/dropbox), [Fitbit](https://ifttt.com/fitbit), and [ecobee](https://ifttt.com/ecobee). Each of your products will be represented on IFTTT as a service. Each of your services will have their own dedicated landing page on IFTTT, called a "service page."

![Service page example](https://web-assets.ifttt.com/packs/media/docs/service_page-f60d3224.png)

### Applets

We bring services together into Applets. An Applet is an automation workflow that connects two or more services together and allows users to do something that those services couldn't do on their own. For example, you could use an Applet to [turn on your Philips Hue lights when your Arlo security camera detects motion](https://ifttt.com/applets/eX6zn2mD) or [pause your iRobot vacuum before your Zoom meetings](https://ifttt.com/applets/HcyvXCPK).

Applets are composed of triggers, queries, and actions. Triggers tell an Applet to start, queries provide additional conditions, and actions are the result of an Applet run. Applets can be published by a service admin or users themselves.

![Applet example](https://web-assets.ifttt.com/packs/media/docs/applet_example-d3fa1c5a.png)

### Triggers, Actions, and Queries

Your product's API consists of various endpoints used to get, write, or send data. Each of your API's endpoints will map 1-to-1 to a trigger, action, or query that you want to add to your service. Your triggers will be sending data to IFTTT when something happens with your product (e.g. thermostat turned on). Queries are a way for IFTTT to request additional data from your product (e.g. List current temperature setting). Your actions will collect instructions that IFTTT sends you to do something with your product (e.g. turn on the device).

![Applet components](https://web-assets.ifttt.com/packs/media/docs/applet_components-716bc91b.jpg)

If you're new to IFTTT, we recommend [creating a free account](https://ifttt.com/) to experience a few Applets for yourself. Here are a few simple Applets worth trying to get the hang of it:

-   [Get a daily email with the weather report](https://ifttt.com/applets/Zv56ZXwR)
-   [Get a notification when the ISS passes over your house but only if it is clear skies and after dark](https://ifttt.com/applets/VDdNBmiE)

## 1\. Plan your integration

Now that you understand the IFTTT user experience, it's time to apply your product to these basic concepts. Think about how your users commonly experience and interact with your device, app, or service:

-   What are the most popular and useful features or functions?
-   Which of these are currently supported by your API?

This is the best place to start when thinking about how your IFTTT integration will work and what triggers, queries, and actions to include. Start with a handful of the most obvious triggers, queries, and actions and expand later.

Make sure to always keep in mind what the user experience will look like and what use cases your integration will support because of the triggers, queries, and actions that you have.

**_Pro tip: Learn from other similar services. If you need help figuring out what might be most useful to your users, you can browse our services catalog for similar products and use the triggers, queries, and actions they support as things to consider._**

Some of the best IFTTT integrations are the result of product managers, marketing teams, and engineers all working together. This teamwork will ensure that what you plan to build aligns with the user experiences you want to create and advertise.

As part of your planning, make sure to read through our guidelines and recommendations for [designing a successful IFTTT integration](https://ifttt.com/docs/guidelines).

## 2\. Build the integration

Building your IFTTT integration will be done in three stages:

### Development

#### Set up your environment

You'll first need to add an IFTTT compatibility layer to your API so that the IFTTT Platform can understand your endpoints and translate them into each trigger, query and action that you want to include as part of your service. We recommend two strategies for doing this:

-   **Most common:** Deploy a "shim app" that sits between your API and IFTTT. This app will translate resources from your API into responses IFTTT can understand.

![Architecture diagram](https://web-assets.ifttt.com/packs/media/docs/architecture_diagram-8e8dd23e.png)

-   Add IFTTT-specific endpoints directly to your API. These endpoints can source data from your existing API and serve them in responses IFTTT can understand.

If you don't have an API, our [documentation](https://ifttt.com/docs/api_reference) will guide you through its development with straightforward requirements.

#### Create your service on the IFTTT Platform

Once your API environment is properly configured to speak to IFTTT, you'll navigate to your Platform dashboard to create a new service. If you have multiple, uniquely different products (e.g. a thermostat, a dishwasher, and an air purifier), it is advised that you create a separate service for each of them.

You'll then begin to build the features of your integration in accordance with our [service design guide](https://ifttt.com/docs/guidelines) and [developer documentation](https://ifttt.com/docs/api_reference).

### Testing

You want to make sure that what you are building is working as intended. Therefore, it's strongly recommended that you test each component of your integration at every stage of its development.

The IFTTT Platform provides you with robust endpoint and authentication testing tools that will help you to rapidly develop your triggers, queries, and actions with the peace of mind that they're compatible with IFTTT.

#### End to end testing with Applets

As you near the completion of your development, set aside some time for testing your newly built IFTTT service end to end. Build and run Applets that use each trigger, query, and action from your service on IFTTT to ensure that everything works as intended and the user experience is as expected.

#### Invite others to test your integration

After you've tested your service on your own, show off what you've built and collect feedback by inviting others to try it out. Your service's dashboard includes an Invite URL that allows you to give up to 25 people special preview access to your service.

**_Note: Your invitees must first have their own IFTTT account in order to preview your service and test it with Applets. If they don't yet have an IFTTT account, they can create one for free from the Invite URL._**

It's a good idea to have a few ready-made Applets available for your invitees to easily enable. However, your invitees can still test your service by creating their own Applets with other services of their choosing. Make sure to first brief them on how to enable or create an Applet, then follow up to hear of their experiences and any feedback they might have.

### Submit your service for review

Once you've finished developing and testing your IFTTT integration and you're confident that your service will delight users, it's time to submit it for IFTTT to review.

You can find the submit link under the "Publish" tab on your service's dashboard. IFTTT does an internal review process before a service can be pushed into production. This process can take up to a week depending on when we receive your submission and how much feedback we have.

If our team has any feedback or concerns, we'll send you an email and you'll be able to view our comments on the review page next to each element. Feel free to re-submit the service once you've addressed the feedback and respond via the comments.

Below are common reasons for services not passing the review on the first try:

-   Applet logo is not a white vector image on transparent background.
-   Authentication or endpoint tests are not passing at the time of review.
-   Authentication flow does not mention IFTTT or does not include a consent message.
-   Support email is a personal address.
-   Service copy is incomplete, confusing, contains placeholders, styling, or grammar issues. This covers everything from service name and description to verbiage and helper text on individual triggers, queries, or actions.
-   A query you've built doesn't have a practical application.

Once your service has been approved, we'll send you an email asking you to fill out the pre-launch marketing form. In this form, we'll ask for the date on which you'd like the service to be published on IFTTT. Before your service is published, we'll do a final review to make sure that the service's endpoint and authentication tests are passing, and that you have at least twelve published Applets ready for users to begin their experience with.

## 3\. Launch and market your service

Once your service has been approved by IFTTT, it's time to publish and share it with the world! On your launch date, your integration will go live and ready for all to use.

Users already on IFTTT may discover your service organically, but to see the best adoption possible, you'll want to spread the word that you're now on IFTTT. Marketing your service effectively and often is the best way to guarantee it'll be a success.

Below is a blueprint for how to successfully market your service. Follow our [brand guidelines](https://ifttt.com/explore/brand-guidelines) where necessary.

### Landing page

Show off your service on your website. This is one of the most effective ways to showcase your new IFTTT integration to your users. We're happy to help with the details, but a landing page on your own website gives you the freedom to showcase your IFTTT service in your own style. You can use video, photos, and copy that make it clear that your IFTTT service is a natural extension of your brand.

From an SEO and discoverability perspective, these pages act as important top-of-the-funnel tools and help people learn more about the features of your service before they become customers. "Works with IFTTT" is a powerful badge — wear it with pride on your site!

![Philips hue landing page](https://web-assets.ifttt.com/packs/media/docs/landing_page_hue-e025d0e8.png)

### Works with IFTTT badges

Make sure to tell the world that you work with IFTTT on your packaging, website, digital properties, and trade show displays. Use badges in marketing material to promote your integrations, too. You may place next to other \_Works with \_or \_Download on \_badges like Google Play, App Store, Google Assistant, and Amazon Alexa.

![Example Works with IFTTT badges](https://web-assets.ifttt.com/packs/media/docs/example_badges-2e6fb79e.jpg)

On request, we can also create customized _Works with IFTTT_ badges that feature your service icon or logo.

![Custom Works with IFTTT badges](https://web-assets.ifttt.com/packs/media/docs/custom_badges-e4afcdae.jpg)

Shout about it! Social media is the perfect way to start a conversation. Post about your service's launch, of course. But don't stop there — share favorite Applets regularly along with the link to your service page on IFTTT. People follow you for a reason — they want to know more! Make sure to take advantage of this engaged audience that's opted-in to hear from you regularly.

This is also an opportunity to collect user feedback. Ask questions, and listen — which Applets do people want to see from you? What triggers or actions are you missing? The next game-changing idea may come to you in a Tweet.

Remember to tag @IFTTT in your posts so we can help spread the word — we've got an itchy RT finger!

![Social media example](https://web-assets.ifttt.com/packs/media/docs/social_media_example-7020c19b.png)

### Email campaigns

Subject: We're on IFTTT :-). When it comes to email marketing your IFTTT integration, we recommend a two-part approach:

1.  At launch time, send a one-off announcement to your user base, highlighting the new functionality and some amazing Applets.
    
2.  Include IFTTT in your on-boarding email or email campaign, so that new users can get up to speed on everything your service offers.
    

You'll also want to email users when you make improvements to your service, such as adding new triggers and actions or building an exciting Applet with a new partner.

![Email example](https://web-assets.ifttt.com/packs/media/docs/litter_robot_email-2c7980e8.png)

### Blog posts

Tell the story of your service. You may use your blog for major product updates, heartfelt user stories, tips, thought leadership, SEO — or for all of the above. Whatever your publishing criteria, there's a way to tell the story of your IFTTT service in a natural way. And you'll want to: a blog post is the perfect way to highlight the value of your new integration and link to must-have Applets.

It will help you control the story on launch day, and will always be a place where people can go to get more context, straight from the source.

The story shouldn't end at launch, either — if you make updates to your service or uncover interesting data from your IFTTT users, it may be time to write another post.

### Video

Your service is the star. Marketers have been investing in more video content year-over-year for one simple reason: it works. No need to hire Steven Spielberg — it's just about telling your story in an authentic way.

Highlight some Applets, demo the in-app integration — even a screen grab video can be engaging if it's showing the viewer something that will make their life better/easier/cooler. Still stuck on what to film? Mix this best practice with a contest and see if you can incentivize your users to create their own videos showing off your service.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/4CChLSXqS6k" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>

### Contests and giveaways

Harness your community's creativity. Run a contest or a giveaway to get people excited about your service. Ask for Applet ideas in exchange for the chance to win a product. Or ask people to spread the word about your new service with a specific hashtag or referral link in order to unlock a discount. You may be blown away by the creativity and enthusiasm hiding in your community!

We're happy to help co-market these campaigns with social or blog support.

### Co-marketing with IFTTT

We're invested in your success so we're happy to help promote your service and tell the world all about it. Contact our partnerships team at [partnerships@ifttt.com](mailto:partnerships@ifttt.com) to learn more.