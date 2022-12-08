https://medium.com/@gagarine/use-sci-hub-with-zotero-as-a-fall-back-pdf-resolver-cf139eb2cea7

[](https://medium.com/?source=---three_column_layout_nav----------------------------------)

[Get unlimited access](https://medium.com/plans?source=upgrade_membership---three_column_layout_nav----------------------------------)

[Open in app](https://rsci.app.link/?%24canonical_url=https%3A%2F%2Fmedium.com%2Fp%2Fcf139eb2cea7&%7Efeature=LoOpenInAppButton&%7Echannel=ShowPostUnderUser&%7Estage=mobileNavBar&source=---three_column_layout_nav----------------------------------)

[](https://medium.com/?source=---three_column_layout_nav----------------------------------)

[

Home





](https://medium.com/?source=---three_column_layout_nav----------------------------------)

[

Notifications







](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fmedium.com%2Fme%2Fnotifications&source=---three_column_layout_nav-----------------------notifications_sidenav-----------)[

Lists







](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fmedium.com%2Fme%2Flists&source=---three_column_layout_nav-----------------------lists_sidenav-----------)[

Stories







](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fmedium.com%2Fme%2Fstories%2Fdrafts&source=---three_column_layout_nav-----------------------stories_sidenav-----------)

---

[

Write







](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fmedium.com%2Fnew-story&source=---three_column_layout_nav-----------------------new_post_sidenav-----------)

[

![Simon](https://miro.medium.com/fit/c/96/96/1*4WOa4j6TXaAxO4sKDiubtg.jpeg)



](/?source=post_page-----cf139eb2cea7--------------------------------)

[Simon](/?source=post_page-----cf139eb2cea7--------------------------------)

Follow

Oct 29, 2018

·

3 min read

# How to configure Zotero to retrieve Publication’s PDF from Sci-Hub automatically

## Sci-Hub + Zotero = ❤PDF❤

[Zotero](http://zotero.org/) try to download the PDF of any publications you add to your collection. But, a lot of publications are behind paywall. Zotero can not download those publication automatically as access are blocked.

![](https://miro.medium.com/max/644/1*Ns0LNJSMVig6eXK53lAYeg.png)

SAGE, I do want to Full Text. Ok?

Let’s configure Zotero so when a publications is not publicly available we use [sci-hub](https://sci-hub.se/) to download it anyway automatically. To do that, we are going to add a [custom PDF resolver](https://www.zotero.org/support/kb/custom_pdf_resolvers). Don’t worry, it’s actually pretty simple and [certainly illegal in most country](https://engineuring.wordpress.com/2018/07/07/why-sci-hub-is-illegal-and-what-you-can-do-about-it/) (but we will use a secure connection, so nobody can know what you download from sci-hub).

You just have to follow those few steps:

1.  Open the preferences

![](https://miro.medium.com/max/1126/1*egXeSWKDO2h4yMX9AOFKlg.png)

2. Open the _Config Editor_ (say yes when it ask to be cautious)

![](https://miro.medium.com/max/1400/1*9RC6_8PSSWG8P8-6nMTvLQ.png)

3. Find the `extensions.zotero.findPDFs.resolvers` , right click and select _Modify_ (if you don’t know how to do a right click, you can also double click).

![](https://miro.medium.com/max/1338/1*z6m9ICWvupEoTwEltV2SeA.png)

4. In the text input, copy&past the following code (the text input should be empty or only have ‘[]’ that you can safely delete before pasting this code):

{  
    "name":"Sci-Hub",  
    "method":"GET",  
    "url":"[https://sci-hub.se/{doi](https://sci-hub.se/{doi)}",  
    "mode":"html",  
    "selector":"#pdf",  
    "attribute":"src",  
    "automatic":true  
}

Done. No need to restart Zotero.

Now when you add a publication from the browser plugin or directly from Zotero, it will always try to get the PDF from sci-hub when other resolver fail.

![](https://miro.medium.com/max/646/1*aBvcodBR2AupMLQAU0vE9w.png)

Their you go! Thanks sci-hub.

Yeah!

**Notes:**

I’m using the [https://sci-hub.se](https://sci-hub.se/{doi) domain as it is the only domain that do work properly trough a SSL connection right now. It may change in the future. If it breaks just [tweet me](http://twitter.com/gagarine) and I will update the code accordingly.

Sometimes sci-hub display a captcha. In this case this method will fail as Zotero can not show up the captcha to you. The captcha seem IP based, downloading a paper once using [sci-hub.se](https://sci-hub.se) with your standard browser should solve the problem.

If you are in police state like UK, , perhaps [https://sci-hub.se](https://sci-hub.se/) is blocked. In this case you need to use [https://www.torproject.org](https://www.torproject.org/) or a VPN. By default, Zotero will not connect trough Tor network if you use the tor browser. You need to route all connections trough the tor network. See [https://superuser.com/questions/539203/how-can-i-make-tor-route-all-my-traffic](https://superuser.com/questions/539203/how-can-i-make-tor-route-all-my-traffic?source=responses-----cf139eb2cea7---------------------respond_sidebar--------------) (I will put more details once I got some time to try it)

Last if you don’t know who is [Alexandra Elbakyan](https://en.wikipedia.org/wiki/Alexandra_Elbakyan), go check it.

--

--

12

## [More from Simon](/?source=post_page-----cf139eb2cea7--------------------------------)

Follow

[](https://medium.com/m/signin?actionUrl=%2F_%2Fapi%2Fsubscriptions%2Fnewsletters%2Fd38c39844ef5&operation=register&redirect=https%3A%2F%2Fgagarine.medium.com%2Fuse-sci-hub-with-zotero-as-a-fall-back-pdf-resolver-cf139eb2cea7&newsletterV3=28c8be942bf2&newsletterV3Id=d38c39844ef5&user=Simon&userId=28c8be942bf2&source=-----cf139eb2cea7---------------------subscribe_user-----------)

Love podcasts or audiobooks? Learn on the go with our new app.

[Try Knowable](https://knowable.fyi/?utm_source=medium&utm_medium=referral&utm_campaign=medium-post-footer&source=post_page-----cf139eb2cea7--------------------------------)

[](https://medium.com/?source=post_page-----cf139eb2cea7--------------------------------)

[About](https://medium.com/about?autoplay=1&source=post_page-----cf139eb2cea7--------------------------------)[Help](https://help.medium.com/hc/en-us?source=post_page-----cf139eb2cea7--------------------------------)[Terms](https://policy.medium.com/medium-terms-of-service-9db0094a1e0f?source=post_page-----cf139eb2cea7--------------------------------)[Privacy](https://policy.medium.com/medium-privacy-policy-f03bf92035c9?source=post_page-----cf139eb2cea7--------------------------------)

---

## Get the Medium app

[![A button that says 'Download on the App Store', and if clicked it will lead you to the iOS App store](https://miro.medium.com/max/270/1*Crl55Tm6yDNMoucPo1tvDg.png)](https://itunes.apple.com/app/medium-everyones-stories/id828256236?pt=698524&mt=8&ct=post_page&source=post_page-----cf139eb2cea7--------------------------------)

[![A button that says 'Get it on, Google Play', and if clicked it will lead you to the Google Play store](https://miro.medium.com/max/270/1*W_RAPQ62h0em559zluJLdQ.png)](https://play.google.com/store/apps/details?id=com.medium.reader&source=post_page-----cf139eb2cea7--------------------------------)

[Get started](https://medium.com/m/signin?operation=register&redirect=https%3A%2F%2Fgagarine.medium.com%2Fuse-sci-hub-with-zotero-as-a-fall-back-pdf-resolver-cf139eb2cea7&source=post_page---three_column_layout_sidebar-----------------------three_column_layout_nav-----------)

[

![Simon](https://miro.medium.com/fit/c/176/176/1*4WOa4j6TXaAxO4sKDiubtg.jpeg)



](/?source=---three_column_layout_sidebar----------------------------------)

[

## Simon

](/?source=---three_column_layout_sidebar----------------------------------)

136 Followers

Follow

[](https://medium.com/m/signin?actionUrl=%2F_%2Fapi%2Fsubscriptions%2Fnewsletters%2Fd38c39844ef5&operation=register&redirect=https%3A%2F%2Fgagarine.medium.com%2Fuse-sci-hub-with-zotero-as-a-fall-back-pdf-resolver-cf139eb2cea7&newsletterV3=28c8be942bf2&newsletterV3Id=d38c39844ef5&user=Simon&userId=28c8be942bf2&source=---three_column_layout_sidebar-----------------------subscribe_user-----------)

[

Help

](https://help.medium.com/hc/en-us?source=---three_column_layout_sidebar----------------------------------)

[

Status

](https://medium.statuspage.io/?source=---three_column_layout_sidebar----------------------------------)

[

Writers

](https://about.medium.com/creators/?source=---three_column_layout_sidebar----------------------------------)

[

Blog

](https://blog.medium.com/?source=---three_column_layout_sidebar----------------------------------)

[

Careers

](https://medium.com/jobs-at-medium/work-at-medium-959d1a85284e?source=---three_column_layout_sidebar----------------------------------)

[

Privacy

](https://policy.medium.com/medium-privacy-policy-f03bf92035c9?source=---three_column_layout_sidebar----------------------------------)

[

Terms

](https://policy.medium.com/medium-terms-of-service-9db0094a1e0f?source=---three_column_layout_sidebar----------------------------------)

[

About

](https://medium.com/about?autoplay=1&source=---three_column_layout_sidebar----------------------------------)

[

Knowable

](https://knowable.fyi/?source=---three_column_layout_sidebar----------------------------------)