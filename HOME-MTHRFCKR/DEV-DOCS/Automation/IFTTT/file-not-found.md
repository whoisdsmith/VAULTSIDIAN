# File Not Found– [[IFTTT]]

---


-   [How to avoid the File not found image with filter code](https://help.ifttt.com/hc/en-us/articles/115010361748/#HowtoavoidtheFilenotfoundimagewithfiltercode)

The ubiquitous **File not found** image, explained:

![no_image_card.png](https://help.ifttt.com/hc/article_attachments/360041394694/no_image_card.png)

This image will appear when [[IFTTT]] is set up to post an image or a file, but we don't get the data as expected.

Here's an example to illustrate further. The Applet below is configured to [post a tweet with an image](https://ifttt.com/twitter/actions/post_new_tweet_with_image) each time you [add a Tumblr post](https://ifttt.com/tumblr/triggers/new_any_post). If this Applet is triggered by a Tumblr post _without_ an image, the **File not found** image will be used. 

![Tumblr_to_Twitter_Applet.png](https://help.ifttt.com/hc/article_attachments/4412083996699/Tumblr_to_Twitter_Applet.png)

If you're seeing this image often, we recommend switching to an action that is not expecting an image each time it runs, like [Twitter - Post a tweet](https://ifttt.com/twitter/actions/post_new_tweet).

## How to avoid the File not found image with filter code

You can skip an Applet's action when the **File not found** image is set to be used with the following [filter code](https://help.ifttt.com/hc/en-us/articles/4406412223771):

```
let imageURL = Tumblr.newAnyPost.PostImageUrl;let noImage = 'no_image_card.png';if ( imageURL.indexOf(noImage) !== -1 ) {     Twitter.postNewTweetWithImage.skip();}
```

Note that this code is specific to the Tumblr > Twitter Applet mentioned above. If you'd like to use this filter code in your Applet, `Tumblr.newAnyPost.PostImageUrl` and `Twitter.postNewTweetWithImage.skip()` will need to be replaced with your trigger's ImageURL ingredient and your action's skip code, respectively.