# Reddit -> Guilded Webhooks Guide

![](https://www.redditstatic.com/desktop2x/img/renderTimingPixel.png)


[Tutorial](https://www.reddit.com/r/ifttt/search?q=flair_name%3A%22Tutorial%22&restrict_sr=1)

Intro

**Hello all,**

In this small tutorial, I will be showing you how you can get Reddit posts forwarded to Guilded text channels using webhooks.

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/dxddx59y6uh81.png?width=535&format=png&auto=webp&s=e5c52cca9e175d9c382a9a7bf1fc1ef7b44c04c3)](https://preview.redd.it/dxddx59y6uh81.png?width=535&format=png&auto=webp&s=e5c52cca9e175d9c382a9a7bf1fc1ef7b44c04c3)

Sample webhook embed

Steps to Take

**1.- Let's start by heading to** [**https://ifttt.com/explore**](https://ifttt.com/explore) **and creating a new applet.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/zkkj2m1h7uh81.png?width=1920&format=png&auto=webp&s=a90ee9889f7c4a13ebaf925165044d4f3256f49c)](https://preview.redd.it/zkkj2m1h7uh81.png?width=1920&format=png&auto=webp&s=a90ee9889f7c4a13ebaf925165044d4f3256f49c)

Applet creation screen

  

**2.- Click on the "If This" button. Then, search for the "Reddit" service.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/okxz57zw7uh81.png?width=1920&format=png&auto=webp&s=be2cf2eade4745d1685adfb26585ffeb9833fa4c)](https://preview.redd.it/okxz57zw7uh81.png?width=1920&format=png&auto=webp&s=be2cf2eade4745d1685adfb26585ffeb9833fa4c)

We will use this service integration

  

**3.- Choose trigger for the service.**

In this case, we will use the "New hot post in subreddit" option. Keep in mind that this particular step is up to personal preference, however, usually it might be best to filter out posts by only forwarding "hot" or "top" posts, as passing all new posts can quickly flood your channel.

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/hfhjtxek8uh81.png?width=1903&format=png&auto=webp&s=c8e12550cc0ae2b27ee8eb5b8df05c7c90094027)](https://preview.redd.it/hfhjtxek8uh81.png?width=1903&format=png&auto=webp&s=c8e12550cc0ae2b27ee8eb5b8df05c7c90094027)

This option will only forward hot posts from a particular subreddit

  

**4.- Specify the subreddit to be monitored, then, click on the "Create trigger" button.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/8gkbu34s8uh81.png?width=1920&format=png&auto=webp&s=aa58f018a49eab1a289d2a32450dc1921050bec0)](https://preview.redd.it/8gkbu34s8uh81.png?width=1920&format=png&auto=webp&s=aa58f018a49eab1a289d2a32450dc1921050bec0)

/r/Animewallpaper will be used as an example here

  

**5.- Click on the "Then - That" button.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/cygii2wbauh81.png?width=1920&format=png&auto=webp&s=dff545b40af96d2d3dfcd3eeeddd2d8523501abc)](https://preview.redd.it/cygii2wbauh81.png?width=1920&format=png&auto=webp&s=dff545b40af96d2d3dfcd3eeeddd2d8523501abc)

First module done, now comes the second one

**6.- Search for the "Webhooks" service.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/iv4f8afjauh81.png?width=1920&format=png&auto=webp&s=c37eb37725f76b965a35b87883189385cf7e251c)](https://preview.redd.it/iv4f8afjauh81.png?width=1920&format=png&auto=webp&s=c37eb37725f76b965a35b87883189385cf7e251c)

We need this service to make an HTTP request

**7.- Click on the "Make a web request" option.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/be0v9fiqauh81.png?width=1920&format=png&auto=webp&s=288c4670ac80de0a4a2909bef675ac42a5da8500)](https://preview.redd.it/be0v9fiqauh81.png?width=1920&format=png&auto=webp&s=288c4670ac80de0a4a2909bef675ac42a5da8500)

Only one option here, can't go wrong

  

**8.- Configure the action fields of the module.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/s4khxkej9uh81.png?width=1903&format=png&auto=webp&s=552160bbbbaf22b55ccade237fcdae1548c9ae6b)](https://preview.redd.it/s4khxkej9uh81.png?width=1903&format=png&auto=webp&s=552160bbbbaf22b55ccade237fcdae1548c9ae6b)

Configuration for this step is shown in the image

Fill the following fields with the necessary information:

-   URL - Fill this in with your Guilded webhook URL.
    
-   Method - Select "POST".
    
-   Content type - Select "application/json"
    
-   Body - Fill this in with your body of choice. A template will be given for identical results.
    

  

```
{
"embeds": [{
"title": "{{Title}}",
"url": "<<<{{PostURL}}>>>",
"description": "<<<{{Content}}>>>",
"image": {
"url": "{{ImageURL}}"
},
"footer": {
"text": "/u/<<<{{Author}}>>> | <<<{{PostedAt}}>>>"
}
}]
}
```

Once the action fields have been properly set up, click on the "Update action" button.

  

**9.- Name your applet and connect it. You are now done with the setup.**

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/beglkt0nbuh81.png?width=531&format=png&auto=webp&s=0021a8bd7335bf335ae7999cba085a6c4bf4040a)](https://preview.redd.it/beglkt0nbuh81.png?width=531&format=png&auto=webp&s=0021a8bd7335bf335ae7999cba085a6c4bf4040a)

Very creative

  

_**Let's take a look at some examples.**_

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/d259n9esbuh81.png?width=540&format=png&auto=webp&s=84d80eca435e5035b92161822866cd3bc671eaca)](https://preview.redd.it/d259n9esbuh81.png?width=540&format=png&auto=webp&s=84d80eca435e5035b92161822866cd3bc671eaca)

Sample 1

[![r/ifttt - Reddit -> Guilded Webhooks Guide](https://preview.redd.it/0q5jpcy2cuh81.png?width=506&format=png&auto=webp&s=eff5e4bb05e09c008231b01022a7c200f9961eb1)](https://preview.redd.it/0q5jpcy2cuh81.png?width=506&format=png&auto=webp&s=eff5e4bb05e09c008231b01022a7c200f9961eb1)

Sample 2

Looks pretty nice doesn't it?

Additional Considerations

-   You will find that posts grabbed from Reddit that _do not have an image (aka text-only posts)_ will instead have a 404 placeholder image.
    
-   Posts that contain either videos or GIFs are not supported (they will not be visible on the embed).
    
-   If you only want to forward text posts, it might be better to get rid of the image URL component of the embed or to use filter code in your applet.
    
-   This method works best for posts that contain static images (jpegs or png).