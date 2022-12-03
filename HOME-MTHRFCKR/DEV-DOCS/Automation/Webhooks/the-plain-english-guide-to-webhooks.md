# The Plain-English Guide to Webhooks

You have **2** free member-only stories left this month. 

![image showing how webhooks work server sending data automatically to user phone in contrast to request response cycle.](https://miro.medium.com/max/1188/1*_X8lkX31ovfPriBq-9akRA.png)

image showing an example of how webhooks work in contrast to a traditional request/response cycle.

Web-apps have increasingly become so interconnected through the use of APIs which are essential for sharing data across different web applications. They have also become essential especially for Software-as-a-service (SaaS) applications. Users want updates fast and regularly; to address this need developers have added webhooks to their APIs. Web-hooks is the process in which data from an API can be delivered without having to receive a request for each response. This post gives an overview of what web-hooks are, why you should include it in your web app and how to add it in your API.

**What are Web-hooks?**

A Webhook is a method for one app to update other applications with real-time information. Webhooks operate on the concept of _event reaction _(no need to call me, I’ll call you when I have something new), avoiding the need for the (user) client-side application making constant requests to the server for real-time data.

A more concise definition, for those who are of a more technical persuasion, is:

_“Webhooks are user-defined HTTP callbacks which are linked to a web app and are triggered by specific events.”_

A webhook delivers data to other applications in real-time so that data is received immediately. _What is an API?_ API stands for Application Programming Interface, but what does that mean? APIs can share data and functionality. For example, you might use Google Maps API to look for museums by location or name, pulling out a lot of data from each place. Then you can use that data and display it to your UI user interface.

Contrary to typical APIs where the user would need to make an action (request) to get data from the server. A request isn’t required for a webhook it just sends the data when it’s available. For example, when you subscribe to your bank you’ll get a push notification to your phone when you make a transaction on your card or if your balance is below a certain amount. This makes it a better experience for the user and developer because it reduces server costs and makes the web app more efficient.

This is the core concept of webhooks. To use a webhook, you need to register with a URL with whichever company that is providing the service. The URL is a place within your application that will accept that data and do something with it. When there’s some new information the webhook will send it to your URL. With webhooks, you can get push notifications when certain events happen on the server. For example, when you subscribe to your bank you’ll get a push notification to your phone when you make a transaction on your card or if your balance is below a certain amount.

The first step in using webhooks is given the webhook provider a URL where you deliver your requests to. This can be done by configuring your backend or API. This means that you need to set up a URL in your app that’s accessible from the web. The vast majority of webhooks will POST data as XML or JSON which is a form of data that you receive from the server.

_So what do webhooks look like?_

An API calls the server-side app which provides the client-side app with end-point URLs that the client can call. The server-side might expose the following API endpoint URLs for a simple chat application.
    
    
    POST /messages createNewMessage   
    GET /messages/{messageId} readMessage  
    POST /messages/{messageId}/comments postComment  
    GET /messages/{messageId}/comments/{commentsId} readComment
    
    If the client-side app wants to post a new message to the server, the client-side app makes a call to the server to _POST /messages_
    
    Also if the client-side app wants to read a comment that has been posted to a particular message on the server, the client-side application calls _GET/messages/{messageID}/comments/{commentsID}_
    
    The messages and comments are created and stored on the server’s database, and read from the server database, using the server-provided APIs (end-point URLs).
    
    Webhooks, it is the client-side application that provides the server-side application with a URL to call, and the server-side application calls that URL, whenever the server has been updated with some new information that needs to be sent to the user. _Essentially a webhook is just an end-point URL provided by the client-side application to the server-side application._ In the case of our simple chat app example it may look like this:
    
    { “newCommentWebhook” : “https://clientchat.com/webhook/newComment" }
    
    A webhook is nothing but a simple client-side provided end-point URL. This end-point URL has to be passed by the client-side application to the server-side application at some point before the webhook call by the server-side. If we want the server to notify the user whenever a new comment has been posted against a particular message. In this instance, whenever a new comment is posted to the database, the server-side application should (after posting the comment to the database) call the above webhook URL, to let the client-web app know that a new comment has become available.
    
    Using webhooks, the server can notify the client of new events that occur (i.e. a new message has been posted). The API needs to be configured in the API end-points such that there is a placeholder, that allows webhook URL to be passed from the client-side apps. This can be done through the server-side API by providing a parameter for webhook URLs. The server-side application should have some mechanism of storing the client provided webhook end-point so that it can be called by the server-side when required. Thus in our example the server-side API request the body should have some parameter, where the client-side application can include their webhook URL.
    
    Webhooks are an essential tool to include due to the ever-growing interconnectivity in our web apps. It is a way for users to receive updates immediately and saves server costs. If you want your web application to be more dynamic and flexible in serving the needs of today’s users than adding a webhook in your web app will be paramount.
    
    A monthly summary of the best stories shared in Level Up Coding [Take a look.](https://medium.com/gitconnected/newsletters/top-stories?source=newsletter_v3_promo--------------------------newsletter_v3_promo--------------)
    
    
    
    
    


___

#article #Webhooks