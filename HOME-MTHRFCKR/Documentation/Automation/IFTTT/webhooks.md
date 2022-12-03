# Webhooks (maker.ifttt.com) and CORS

![](https://www.redditstatic.com/desktop2x/img/renderTimingPixel.png)

.t3\_srqx8z .\_2FCtq-QzlfuN-SwVMUZMM3 { --postTitle-VisitedLinkColor: #edeeef; --postTitleLink-VisitedLinkColor: #6f7071; }

[

Miscellaneous

](https://www.reddit.com/r/ifttt/search?q=flair_name%3A%22Miscellaneous%22&restrict_sr=1)

Let's do a simple test.

-   Get your webhooks key by heading to the [Webhooks service page](https://ifttt.com/maker_webhooks) and clicking Documentation.
    
-   While on that SAME PAGE on [maker.ifttt.com/use/...](https://maker.ifttt.com/use/%2E%2E%2E) open up your browser console (usually Ctrl+Shift+J) and run this line of JavaScript:
    

  

```
fetch(`https://maker.ifttt.com/trigger/do_${prompt('What to do?','something')}/with/key/${prompt('Paste your key')}`).then(a=>a.text()).then(b=>alert(b))
```

If you pasted a valid key, you will get a success message. Furthermore, if the _do\_something_ event name was set up in a Webhook trigger on your account, that Applet would run. Cool !!

Now, navigate to ANY OTHER page on the entire Internet. Even [ifttt.com](https://ifttt.com) will do. Again, open the browser console and run the same JavaScript. What happens? Nothing? Not true!

If you pasted a valid key, the request goes to IFTTT as expected and if there exists a Webhook trigger with the given Event Name (i.e., _do\_something_), that trigger will fire. However, no response will be returned to our JavaScript; in fact no response will be returned to the browser. Instead we see an _Uncaught TypeError: Resource Failed to Fetch_, and if you dig deeper this is due to a missing response header for CORS:

> `request blocked Access-Control-Allow-Origin Missing Header`

So tell me, how is this a useful API if I can't get a success or failure response in my code? What is the sense to blindly send requests or wrap requests in a `try` block knowing it will always throw an error? Why would IFTTT go so long without addressing this?

It is also quite bewildering that a success response is sent as `"text/html"` (despite actually being _plain text)_ yet an error response is sent as `"application/json"` ... how am I supposed to build an interface to this service when I don't even know what content type to expect??

And IFTTT wants people to pay for this kind of sloppiness?