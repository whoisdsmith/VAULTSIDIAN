
# Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)

![](https://www.redditstatic.com/desktop2x/img/renderTimingPixel.png)

.t3\_zalgyb.\_2FCtq-QzlfuN-SwVMUZMM3 { --postTitle-VisitedLinkColor: #edeeef; --postTitleLink-VisitedLinkColor: #6f7071; --postBodyLink-VisitedLinkColor: #6f7071; }

[

Guide

](https://www.reddit.com/r/Piracy/search?q=flair_name%3A%22Guide%22&restrict_sr=1)OC

I'm using CloudFlare WARP+ VPN to access the internet right now, and just saw a VPN recommendation question when scrolling through this sub, Googled 'does warp support bittorrent' and [this ancient reddit post actually came up](https://www.reddit.com/r/CloudFlare/comments/de2908/experience_torrenting_on_warp/), people saying it works.

WARP's premium WARP+ plan to remove the basic plan's speed limits is 1GB data per 1 person invited, but the "invitation" can be scripted so essentially you get a free & quick VPN.

Can use it as just another VPN or torrent over it, note that for normal web browsing it *forwards your real IP address to sites*, but in [that reddit post](https://www.reddit.com/r/CloudFlare/comments/de2908/experience_torrenting_on_warp/) people said it changes your IP when torrenting, so use at your own risk

The steps to get free WARP+ traffic are as follows

Step 1: Install the WARP app from [https://1.1.1.1/](https://1.1.1.1/), and after opening it, find your device ID in app settings and copy it.

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/a7o06cj8ch3a1.jpg?width=2732&format=pjpg&auto=webp&v=enabled&s=2cc3bafa46713b9f969a61fbbd00cb4a9a52942d)](https://preview.redd.it/a7o06cj8ch3a1.jpg?width=2732&format=pjpg&auto=webp&v=enabled&s=2cc3bafa46713b9f969a61fbbd00cb4a9a52942d)

Device ID on iOS

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/10scdhngch3a1.png?width=1564&format=png&auto=webp&v=enabled&s=e54c23620374d95547d9630e9d9078e8693ee655)](https://preview.redd.it/10scdhngch3a1.png?width=1564&format=png&auto=webp&v=enabled&s=e54c23620374d95547d9630e9d9078e8693ee655)

Device ID on Mac and possibly also Windows/Linux, you need to check in Windows/Linux version's settings

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/gocgo24och3a1.jpg?width=1080&format=pjpg&auto=webp&v=enabled&s=59395dad8df466074cbc8506094213852a35faba)](https://preview.redd.it/gocgo24och3a1.jpg?width=1080&format=pjpg&auto=webp&v=enabled&s=59395dad8df466074cbc8506094213852a35faba)

On Android

Step 2: Register for a GitHub (alt) account, go to [https://github.com/navaneethkm004/warp-plus](https://github.com/navaneethkm004/warp-plus), and click Run on Replit button

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/4tvv2ieadh3a1.png?width=1702&format=png&auto=webp&v=enabled&s=ef5820bcd6bcc9513e5e432e5d0e2fbc06a229e1)](https://preview.redd.it/4tvv2ieadh3a1.png?width=1702&format=png&auto=webp&v=enabled&s=ef5820bcd6bcc9513e5e432e5d0e2fbc06a229e1)

https://github.com/navaneethkm004/warp-plus

Step 3: log in to Replit with your just created GH account, import using the default settings, now you should have a copy of the Repl under your account, open the Repl project

Step 4: in the ~console~ (console won't work for new Repls) Shell on right hand side, type python3 main.py

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/2w53up2rdh3a1.png?width=500&format=png&auto=webp&v=enabled&s=e7844072f98def8ac3b12a48caa46ff6118c411b)](https://preview.redd.it/2w53up2rdh3a1.png?width=500&format=png&auto=webp&v=enabled&s=e7844072f98def8ac3b12a48caa46ff6118c411b)

Step 5: in the next prompt, paste your device ID in

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/osto3717eh3a1.png?width=560&format=png&auto=webp&v=enabled&s=3603be7adb90adb47340486563960cd1665e37f6)](https://preview.redd.it/osto3717eh3a1.png?width=560&format=png&auto=webp&v=enabled&s=3603be7adb90adb47340486563960cd1665e37f6)

Step 6: Keep the browser tab with Replit running open, so your script won't get killed. The script will continuously spam "referrals" (trick CF to believe you referred a new user) so 1GBs continuously get added to your account. In the app settings you should now see "WARP+ data remaining" number getting higher and higher.

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/x1bqz70veh3a1.png?width=500&format=png&auto=webp&v=enabled&s=b6230e54d8f5de955c01e55338e7b97fe9068a54)](https://preview.redd.it/x1bqz70veh3a1.png?width=500&format=png&auto=webp&v=enabled&s=b6230e54d8f5de955c01e55338e7b97fe9068a54)

  

[![r/Piracy - Get free CloudFlare WARP+ VPN traffic (BT-over-WARP supported)](https://preview.redd.it/0nh32qoyeh3a1.png?width=1564&format=png&auto=webp&v=enabled&s=697ebeb92e003ac45608fd47bae4ccd8c532f12c)](https://preview.redd.it/0nh32qoyeh3a1.png?width=1564&format=png&auto=webp&v=enabled&s=697ebeb92e003ac45608fd47bae4ccd8c532f12c)

Step 7: Click the connect toggle! And then use this VPN to do anything you wanna, such as torrenting

22 comments

Award

share

save

Comment as [Iamthereaper85](https://www.reddit.com/user/Iamthereaper85/)

.public-DraftStyleDefault-block\[data-offset-key="15c070\_initial-0-0"\]::after { bottom: 0; color: var(--newCommunityTheme-actionIcon); content: 'What are your thoughts?'; cursor: text; left: 0; position: absolute; top: 0; }



![](https://www.redditstatic.com/desktop2x/img/renderTimingPixel.png)

[

![User avatar](https://styles.redditmedia.com/t5_hqlg9/styles/profileIcon_c3w92p9ffp091.jpg?width=256&height=256&crop=256:256,smart&v=enabled&s=606521cdf10891dc36fe66d75ee3678a37019d71)

](https://www.reddit.com/user/Ankororo/)

level 1

[Ankororo](https://www.reddit.com/user/Ankororo/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iym931j/?utm_source=reddit&utm_medium=web2x&context=3)

i've been using [this method](https://github.com/TheCaduceus/WARP-UNLIMITED-ADVANCED) is there any difference?

9

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_2tzknl/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYzhkM2EzYTgzYmRlNWRhZDA2ZDQzNjY5NGUzZTIyYWMzZTY0ZDU3N180ODk2MjQ5_rare_ea180fa3-81df-44df-8900-d59595d4f072-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=fb68d6011e83a953897db3bff19b2dc8b90e16a8)





](https://www.reddit.com/user/MCHerobrine/)

level 2

[MCHerobrine](https://www.reddit.com/user/MCHerobrine/)

Op · [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iymbaxi/?utm_source=reddit&utm_medium=web2x&context=3)

Pastafarian

no

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/Lxne2/)

level 1

[Lxne2](https://www.reddit.com/user/Lxne2/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyomauu/?utm_source=reddit&utm_medium=web2x&context=3)

Torrents

Doesn't work for me even though I did all the steps and quit the app multiple times. Any thoughts?

3

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/Slipsby/)

level 2

[Slipsby](https://www.reddit.com/user/Slipsby/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyouuhg/?utm_source=reddit&utm_medium=web2x&context=3)

patched?

2

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_4onb4d/styles/profileIcon_lgy6qrcdpyf71.png?width=256&height=256&crop=256:256,smart&v=enabled&s=22f5c3390cc9e1244ec0b1d6f2c12be1e6db20a8)

](https://www.reddit.com/user/ANUNEET/)

level 3

[ANUNEET](https://www.reddit.com/user/ANUNEET/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyqb9nw/?utm_source=reddit&utm_medium=web2x&context=3)

Nope, just use the updated version that I commented just now at place of this kanged version.

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_4onb4d/styles/profileIcon_lgy6qrcdpyf71.png?width=256&height=256&crop=256:256,smart&v=enabled&s=22f5c3390cc9e1244ec0b1d6f2c12be1e6db20a8)

](https://www.reddit.com/user/ANUNEET/)

level 1

[ANUNEET](https://www.reddit.com/user/ANUNEET/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyqb0sa/?utm_source=reddit&utm_medium=web2x&context=3)

Basically, this is the kanged (just created the fork & renamed the developer name) version of:

[https://github.com/ALIILAPRO/warp-plus-cloudflare](https://github.com/ALIILAPRO/warp-plus-cloudflare)

and its updated version is:

[https://github.com/TheCaduceus/WARP-UNLIMITED-ADVANCED](https://github.com/TheCaduceus/WARP-UNLIMITED-ADVANCED)

3

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/Lxne2/)

level 2

[Lxne2](https://www.reddit.com/user/Lxne2/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyrmhwc/?utm_source=reddit&utm_medium=web2x&context=3)

Torrents

First one doesn't work and the second one doesn't load.

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_31f89u/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYjljMDQyYzMyNzViYzQ5Nzk5Njg4ZWVhMWEyOWIxNDA1ZDAyOTQ2Yl8xMzA5MTQ_rare_b79c1c10-6508-45a6-805f-0f20300f75ba-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=22bcad83680fb102753f66a1d78d10bf2c22c9ee)





](https://www.reddit.com/user/Condition_Flimsy/)

level 2

[Condition\_Flimsy](https://www.reddit.com/user/Condition_Flimsy/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyuc6kf/?utm_source=reddit&utm_medium=web2x&context=3) · edited 2 mo. ago

Both of em dont work

Edit: They worked OP just forget to say you had to reset encryption keys to see them

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_2tzknl/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYzhkM2EzYTgzYmRlNWRhZDA2ZDQzNjY5NGUzZTIyYWMzZTY0ZDU3N180ODk2MjQ5_rare_ea180fa3-81df-44df-8900-d59595d4f072-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=fb68d6011e83a953897db3bff19b2dc8b90e16a8)





](https://www.reddit.com/user/MCHerobrine/)

level 3

[MCHerobrine](https://www.reddit.com/user/MCHerobrine/)

Op · [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyus6mm/?utm_source=reddit&utm_medium=web2x&context=3)

Pastafarian

On cell phone it gets automatically added and you get real-time "someone has accepted your referral" notifications but on PC you do have to reset the encryption keys or retype the same license key to refresh the amount.

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/Lxne2/)

level 4

[Lxne2](https://www.reddit.com/user/Lxne2/)

· [1 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/izzmlhz/?utm_source=reddit&utm_medium=web2x&context=3)

Torrents

how do I do this on pc? I can only find guides to do it on mobile.

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_31f89u/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYjljMDQyYzMyNzViYzQ5Nzk5Njg4ZWVhMWEyOWIxNDA1ZDAyOTQ2Yl8xMzA5MTQ_rare_b79c1c10-6508-45a6-805f-0f20300f75ba-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=22bcad83680fb102753f66a1d78d10bf2c22c9ee)



](https://www.reddit.com/user/Condition_Flimsy/)

level 1

[Condition\_Flimsy](https://www.reddit.com/user/Condition_Flimsy/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iypdbzp/?utm_source=reddit&utm_medium=web2x&context=3) · edited 2 mo. ago

Replit is saying the amount of GB being added to my account but when I check the account tab it only says WARP with no way of seeing data remaining

2

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_1ihab4/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfNjIyZDhmZWE0NjAzYmE5ZWRhZjEwODRiNDA3MDUyZDhiMGE5YmVkN180MDYwMjUy_rare_b6ffe563-e442-42d2-9cdf-0949b79b65f5-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=649adaa0954fe7e0119fb0b238e9ce1a201a2b2e)



](https://www.reddit.com/user/Sumethal/)

level 1

[Sumethal](https://www.reddit.com/user/Sumethal/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyz8ft0/?utm_source=reddit&utm_medium=web2x&context=3)

thanks man really helpfull

2

ReplyGive Award

Share

ReportSaveFollow

level 1

Comment deleted by user · [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iym7fuc/?utm_source=reddit&utm_medium=web2x&context=3)

[

![User avatar](https://styles.redditmedia.com/t5_3394an/styles/profileIcon_snoo6e66a007-715c-4efc-ae59-cf50060129ec-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=1676d23c5cec8bfce615d7b39347198582afb25f)





](https://www.reddit.com/user/BiggsBounds/)

level 2

[BiggsBounds](https://www.reddit.com/user/BiggsBounds/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iymamfb/?utm_source=reddit&utm_medium=web2x&context=3)

Uh.... Too late. It's on Reddit.

31

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/WG47/)

level 2

[WG47](https://www.reddit.com/user/WG47/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iymo1ea/?utm_source=reddit&utm_medium=web2x&context=3)

This sub has a million subscribers and probably several times as many lurkers. Posting it here is a good way to get it patched.

16

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_2tzknl/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYzhkM2EzYTgzYmRlNWRhZDA2ZDQzNjY5NGUzZTIyYWMzZTY0ZDU3N180ODk2MjQ5_rare_ea180fa3-81df-44df-8900-d59595d4f072-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=fb68d6011e83a953897db3bff19b2dc8b90e16a8)





](https://www.reddit.com/user/MCHerobrine/)

level 3

[MCHerobrine](https://www.reddit.com/user/MCHerobrine/)

Op · [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyn1irp/?utm_source=reddit&utm_medium=web2x&context=3)

Pastafarian

CloudFlare is alert of this exploit at least since May, they just don't bother changing the referral mechanism since they don't lack bandwidth to provide me some free service.

2

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/WG47/)

level 4

[WG47](https://www.reddit.com/user/WG47/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iyn6atr/?utm_source=reddit&utm_medium=web2x&context=3)

Sure, but the more people that jump on something like this, the faster it'll get patched.

7

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_5wwuqx/styles/profileIcon_snoo7e8fda85-7e61-4fff-9d20-051e47060b79-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=c58d7e1276df11a66ae89f1b2272ecc81926e03b)



](https://www.reddit.com/user/NightlyNate/)

level 1

[NightlyNate](https://www.reddit.com/user/NightlyNate/)

· [2 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/iz6lvxe/?utm_source=reddit&utm_medium=web2x&context=3)

This is helpful! Guides like these should be up-voted so more people can see them, not dumb memes.

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_4h14zb/styles/profileIcon_snoo8755919a-d263-4f19-b77e-98a7e718342d-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=4f2f6b48b73b0c641fbb99cd2d3605fa18c70633)



](https://www.reddit.com/user/tparavani/)

level 1

[tparavani](https://www.reddit.com/user/tparavani/)

· [1 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/izqpayl/?utm_source=reddit&utm_medium=web2x&context=3)

Not working anymore :(

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_33s59f/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYzhkM2EzYTgzYmRlNWRhZDA2ZDQzNjY5NGUzZTIyYWMzZTY0ZDU3N18yNTQzODc3_rare_c33694a3-9aa2-4d15-9514-3d427e84bf02-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=873094865af2bbd70487fe8311822a3ac64c4660)



](https://www.reddit.com/user/NZRTA/)

level 2

[NZRTA](https://www.reddit.com/user/NZRTA/)

· [11 days ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/j3qtk9a/?utm_source=reddit&utm_medium=web2x&context=3)

it's still working for me

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)

](https://www.reddit.com/user/Lxne2/)

level 1

[Lxne2](https://www.reddit.com/user/Lxne2/)

· [1 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/j0edx7g/?utm_source=reddit&utm_medium=web2x&context=3)

Torrents

I finally got it working. Does the plus version of this vpn work well with torrenting?

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_2tzknl/styles/profileIcon_snoo-nftv2_bmZ0X2VpcDE1NToxMzdfYzhkM2EzYTgzYmRlNWRhZDA2ZDQzNjY5NGUzZTIyYWMzZTY0ZDU3N180ODk2MjQ5_rare_ea180fa3-81df-44df-8900-d59595d4f072-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=fb68d6011e83a953897db3bff19b2dc8b90e16a8)



](https://www.reddit.com/user/MCHerobrine/)

level 2

[MCHerobrine](https://www.reddit.com/user/MCHerobrine/)

Op · [1 mo. ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/j0eo59z/?utm_source=reddit&utm_medium=web2x&context=3)

Pastafarian

According to [the linked post](https://www.reddit.com/r/CloudFlare/comments/de2908/experience_torrenting_on_warp/) it's good when it comes to torrenting

1

ReplyGive Award

Share

ReportSaveFollow

[

![User avatar](https://styles.redditmedia.com/t5_57jd4v/styles/profileIcon_snoo72b1900e-91b1-41a0-8745-1c9ba28f885b-headshot.png?width=256&height=256&crop=256:256,smart&v=enabled&s=1ff503e8a07969865e0135f47f7b41409fc63877)



](https://www.reddit.com/user/JohnOfJoe01/)

level 1

[JohnOfJoe01](https://www.reddit.com/user/JohnOfJoe01/)

· [17 days ago](https://www.reddit.com/r/Piracy/comments/zalgyb/comment/j2zmadh/?utm_source=reddit&utm_medium=web2x&context=3)

If your wondering why is it not updating, go to the settings in your Warp, click connection and click "Reset Encryption Keys". After that check your total amount left in the Account tab and Boom.
