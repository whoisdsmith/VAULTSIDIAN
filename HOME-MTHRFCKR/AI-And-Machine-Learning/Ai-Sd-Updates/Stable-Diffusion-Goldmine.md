# SD RESOURCE GOLDMINE

---

**Source Originally from Github: [questianon](https://github.com/questianon) All Credit Goes to Him**

## Preamble

This is a **curated** collection of up to date links and information. Everything else is put into one of the collections in [Archives](#archives) for archival or sorting purposes.

This collection is currently hosted on the [SD Goldmine rentry](https://rentry.org/sdgoldmine), the [SD Updates rentry (3)](https://rentry.org/sdupdates3), and [Github](https://github.com/questianon/sdupdates)

All rentry links are ended with a '.org' here and can be changed to a '.co'. Also, use incognito/private browsing when opening google links, else you lose your anonymity / someone may dox you

## Contact

If you have information/files not on this list, have questions, or want to help, please contact me with details

Socials:  
Trip: questianon !!YbTGdICxQOw  
Discord: malt#6065  
Reddit: u/questianon  
Github: https://github.com/questianon  
Twitter: https://twitter.com/questianon)

## How to Use This Resource

The goldmine is ordered from surface-level content to deep level content. If you are a newcomer to Stable Diffusion, it's highly recommended to use start from the beginning.

To prevent redundancies, all items on this list are listed only once. To make sure you find what you're looking for, please use 'Ctrl + F' ('Cmd + F' on macOS).

## Emoji

Items on this list with a 🥒 next to them represent my top pick for the category. This rating is entirely opinionated and represents what I have personally used and recommend, not what is necessarily "the best".

## Warnings

1. Ckpts/hypernetworks/embeddings and things downloaded from here are ==not== interently safe as of right now. They can be pickled/contain malicious code. Use your common sense and protect yourself as you would with any random download link you would see on the internet.

2. Monitor your GPU temps and increase cooling and/or undervolt them if you need to. There have been claims of GPU issues due to high temps.

## Updates

Don't forget to git pull to get a lot of new optimizations + updates. If SD breaks, go backward in commits until it starts working again

Instructions:

* If on Windows:

	1. navigate to the webui directory through command prompt or git bash  
		a. Git bash: right click > git bash here  
		b. Command prompt: click the spot in the "url" between the folder and the down arrow and type "command prompt".  
		c. If you don't know how to do this, open command prompt, type "cd [path to stable-diffusion-webui]" (you can get this by right clicking the folder in the "url" or holding shift + right clicking the stable-diffusion-webui folder)
	2. ```git pull```
	3. ```pip install -r requirements.txt```

* If on Linux: 

	1. go to the webui directory
	2. ```source ./venv/bin/activate```  
		a. if this doesn't work, run ```python -m venv venv``` beforehandww
	3. ```git pull```
	4. ```pip install -r requirements.txt```

## Localizations

French:

* https://rentry.org/stablediffusionfr (contains four localizations: Voldy, sdmodels, sdgoldmine, sdupdates3)

---

## Contents

- [Tutorial](#tutorial)
- [Getting Started](#getting-started)
	- [AMD](#amd)
	- [Linux](#linux)
	- [CPU](#cpu)
	- [Apple Silicon](#apple-silicon)
- [Troubleshooting](#troubleshooting)
- [Repositories](#repositories)
- [Prompting](#prompting)
	- [Documents](#documents)
	- [Prompt Database](#prompt-database)
	- [Tags](#tags)
		- [Tag Rankings](#tag-rankings)
		- [Tag Comparisons](#tag-comparisons)
	- [Artist Comparisons](#artist-comparisons)
		- [Images](#images)
		- [Sites](#sites)
	- [Other Comparisons](#other-comparisons)
	- [Tips](#tips)
	- [Negatives](#negatives)
	- [Extensions](#extensions)
	- [Wildcards](#wildcards)
		- [Collections](#collections)
		- [Text Files](#text-files)
- [Plugins for External Apps](#plugins-for-external-apps)
	- [Photoshop](#photoshop)
	- [Krita](#krita)
	- [GIMP](#gimp)
	- [Blender](#blender)
- [Downloads](#downloads)
	- [Models](#models)
	- [Dreambooth Models](#dreambooth-models)
	- [Embeddings](#embeddings)
	- [Hypernetworks](#hypernetworks)
	- [Misc](#misc)
		- [Aesthetic Gradients](#aesthetic-gradients)
		- [VAEs](#vaes)
		- [Dead/Missing](#deadmissing)
- [Training](#training)
- [Guides](#guides)
- [Alternatives]
	- [Browser](#browser)
- [FAQ](#faq)
- [Glossary](#glossary)

## Tutorial

Hypertextbook: https://rentry.org/sdhypertextbook This is a tutorial/commentary to guide a newcomer how to setup and use Stable Diffusion to its fullest. It's meant to be a supplementary to SD Goldmine: https://rentry.org/sdgoldmine, but can be used without it.  
Glossary (made by TheAlly#7211): https://theally.notion.site/The-Definitive-Stable-Diffusion-Glossary-1d1e6d15059c41e6a6b4306b4ecd9df9

## Getting Started

- NAI Speedrun: https://rentry.org/nai-speedrun 🥒 Easy to follow tutorial with pictures that gets you setup with a 1:1 recreation of NovelAI. Takes < 5 minutes (minus the download times)
- Official Guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-NVidia-GPUs Official AUTOMATIC1111 webui install guide for NVIDIA (Windows and Linux)
- Voldy: https://rentry.org/voldy In-depth tutorial that's been around for a few months. Can help if the speedrun doesn't work
- Emulate NovelAI: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017 A discussion that takes you through emulating NovelAI. Has troubleshooting in the comments

### AMD

AMD isn't as easy to setup as NVIDIA. I don't have an AMD so I don't know if these guides are good

- 🥒 OnnxDiffusersUI https://github.com/azuritecoin/OnnxDiffusersUI A compilation of guides. Contains another version of Stable Diffusion
- https://rentry.org/sd-amd-gfx803-gentoo Stable Diffusion with AMD RX580 on Gentoo (and possibly other RX4xx and RX5xx AMD cards)
- https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Install-and-Run-on-AMD-GPUs Guide from the official AUTOMATIC1111 webui wiki
- https://rentry.org/sdamd Seems to be similar to the one above
- https://rentry.org/sd-nativeisekaitoo 
- https://rentry.org/ayymd-stable-diffustion-v1_4-guide

### Linux

Honestly I don't know what goes here. I'll add a guide if I remember

### CPU

CPU is even less documented. I don't use my CPU for SD, so I don't know if this guide is good

- https://rentry.org/cputard

### Apple Silicon

- 🥒 Mochi-Diffusion, Run Stable Diffusion on Mac natively: https://github.com/godly-devotion/mochi-diffusion
	- If you're the author I accepted your message req on Discord but it bugged or something. Check DMs?
- 🥒 https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon

## Troubleshooting

- Asuka Euler: https://imgur.com/a/DCYJCSX
- Asuka Euler a: https://imgur.com/a/s3llTE5

Why are my outputs black? (Any card)

> Add " --no-half-vae " (remove the quotations) to your commandline args in webui-user.bat

Why are my outputs black? (16xx card)

> Add " --precision full --no-half " (remove the quotations) to your commandline args in webui-user.bat

## Repositories

These are repositories containing general AI knowledge

English:

- 🥒 /sdg/ https://boards.4channel.org/g/catalog#s=sdg
- 🥒 /hdg/ https://boards.4chan.org/h/catalog#s=hdg
- 🥒 /vt/ https://boards.4channel.org/vt/catalog#s=vtai
- 🥒 Stable Diffusion Reddit https://www.reddit.com/r/StableDiffusion/

Korean:

- Korean wiki: https://arca.live/b/aiart

## Prompting

### Documents

These are documents containing general prompting knowledge

English:

- English Grimoire: https://lunarmimi.net/freebies/novelai-anime-girl-prompt-guide/ An AI prompt guide by Lunar Mimi
- Prompt book: https://openart.ai/promptbook A prompt guide by PublicPrompts and OpenArt

Chinese:

- Chinese scroll collection: https://note.com/sa1p/
- Scroll 1: https://docs.qq.com/doc/DWHl3am5Zb05QbGVs

	* Site: https://aiguidebook.top/

	* Backup: https://www105.zippyshare.com/v/lUYn1pXB/file.html

	* translated + download (not sure if safe): https://mega.nz/folder/MssgiRoT#enJklumlGk1KDEY_2o-ViA

	* another backup? https://note.com/sa1p/n/ne71c846326ac

	* another backup: https://files.catbox.moe/tmvjd7.zip

- Scroll 2: https://docs.qq.com/doc/DWGh4QnZBVlJYRkly
- Scroll 3 (spooky): https://docs.qq.com/doc/DWEpNdERNbnBRZWNL
- Tome: https://docs.qq.com/doc/DSHBGRmRUUURjVmNM
- Tome 2 (missing link)
- Spellbook: https://docs.qq.com/doc/DWHFOd2hDSFJaamFm

	* https://www.bilibili.com/read/cv19903596

	* https://www.bilibili.com/read/cv19903680

Japanese:

- Japenese wiki: https://seesaawiki.jp/nai_ch/
- Scroll: https://p1atdev.notion.site/021f27001f37435aacf3c84f2bc093b5?p=f9d8c61c4ed8471a9ca0d701d80f9e28

	* author: https://twitter.com/p1atdev_art/

Korean:

- Korean 1: https://arca.live/b/aiart/60392904
- Korean 2: https://arca.live/b/aiart/60466181

### Prompt Database

- Anon's prompt collection for characters from anime series: https://mega.nz/folder/VHwF1Yga#sJhxeTuPKODgpN5h1ALTQg
- 🥒 Hololive (1): https://rentry.org/3y56t Anon's prompt collection to create Hololive girls
- Hololive (2): https://rentry.org/q8x5y Another anon's prompt collection to create Hololive girls
- Krea AI prompt database: https://github.com/krea-ai/open-prompts
- Prompt search (1): https://www.ptsearch.info/home/
- Prompt search (2): http://novelai.io/
- 4chan sdg prompt search: https://desuarchive.org/g/search/text/masterpiece/
- 4chan hdg prompt search: https://archived.moe/_/search/text/masterpiece/
- 4chan vt prompt search: https://archive.alice.al/vt/search/text/masterpiece/
- PublicPrompts: https://publicprompts.art/ Database of prompts and dreambooth models
	- Discord: https://discord.com/invite/jvQJFFFx26

### Tips

- Usage of spoken squiggle: https://twitter.com/AI_Illust_000/status/1588838369593032706

### Negatives

- Big negative: https://pastes.io/x9crpin0pq
- Fat negative: https://www.reddit.com/r/WaifuDiffusion/comments/yrpovu/img2img_from_my_own_loose_sketch/
- Big negative prompt that's apparently pretty good: https://files.catbox.moe/gaarzy.png

## Tags

- 🥒 Danbooru tags: https://danbooru.donmai.us/wiki_pages/tag_groups
- Danbooru artist tags: https://danbooru.donmai.us/artists

### Tag Rankings

- 🥒 General tag effects on img: https://pastebin.com/GurXf9a4
- Prompt rankings: https://files.catbox.moe/hqs4yf.pdf (reupload from https://docs.google.com/document/d/1Vw-OCUKNJHKZi7chUtjpDEIus112XBVSYHIATKi1q7s/edit?usp=sharing)
- Ranked and classified danbooru tags, sorted by amount of pictures, and ranked by type and quality (WD): https://cdn.discordapp.com/attachments/1029235713989951578/1038585908934483999/Kopi_af_WAIFU_MASTER_PROMPT_DANBOORU_LIST.pdf

### Tag Comparisons

- Emoji/emoticon comparisons: https://docs.google.com/spreadsheets/d/1aTYr4723NSPZul6AVYOX56CVA0YP3qPos8rg4RwVIzA/edit#gid=1453378351
	- Emojis are one character that can portray multiple concepts
	- 🕊💥😱😲😶🙄 leads to https://files.catbox.moe/biy755.png
	- 🌷🕊🗓👋😛👋 leads to https://files.catbox.moe/7khxe0.png
- Class comparison: https://files.catbox.moe/c1yfvf.jpg (MASSIVE IMAGE)
	- Smaller: https://files.catbox.moe/vntwk1.jpg, https://files.catbox.moe/t8teqj.jpg
	- Prompts: https://pastebin.com/SEb876pq
- Clothing comparison: https://files.catbox.moe/z3n66e.jpg
- "Punk" Comparison: https://files.catbox.moe/se3533.png
- NAI tag experiments (has artists): https://zele.st/NovelAI/
- Pre-modern art: https://www.artrenewal.org/Museum/Search#/
- View what SD thinks is a tag: https://dict.latentspace.observer/

## Comparisons

### Artists

#### Images

- 🥒 Comparison (1): https://imgur.com/a/hTEUmd9
	- Alt: https://i.redd.it/llok0ydfhsu91.jpg (https://reddit.com/r/NovelAi/comments/y879x1/i_made_an_experiment_with_different_artists_here/)
	- Alt: https://files.catbox.moe/9wgqx9.jpg
- Comparison (2): https://files.catbox.moe/kulo8m.jpg
	- OCR to get the artists: https://pastebin.com/JB9QcnLZ
- Comparison (3): https://files.catbox.moe/y6bff0.rar
- Comparison (4) (Stable Diffusion v1.5, Waifu Diffusion v1.3, Trinart): https://imgur.com/a/ADPHh9q
- Comparison (5) (3gb, 90x90 different artist combinations on untampered WD v1.3.)
	- One image: https://mega.nz/file/ACtigCpD#f9zP9h1AU_0_4DPsBnvdhnUYdQmIJMb4pyc6PJ4J-FU
	- Individual images: https://mega.nz/file/YPsT1TDJ#XAayj1jYmRSIyzJ-A1pKB8HyxeDib4a4xuo2lxMx7oA
- Comparison (6) (Berry Mix, Clip 2): https://imgur.com/a/zzXqLPc
- Comparison (7) (Berry Mix, Clip 1): https://imgur.com/a/TDGBAlc
- Comparison (8) of using and not using "by artist [first name] [last name]": https://drive.google.com/drive/folders/1qATxaaOb97fxgm5QY8MXIoMAX3FI6WZ0?usp=sharing 
	- https://www.reddit.com/r/StableDiffusion/comments/yiny15/by_artist_firstname_lastname_really_does_makes_a/
- Comparisons (9) of 421 different artists in different models.
	- Berry Mix: https://mega.nz/file/8OlUkapK#4XpOm4kOcw3LOJZeSuSZbO89tRrAuRO_RSfmu_RqzWA
	- SD v1.5 (CLIP 1): https://mega.nz/file/dDU2WB5B#wFsVS0RUX6YK2IJiOtQ5nI7sMMrWEqZg2r3fZrCQ4OI
	- SD v1.5 (CLIP 2): https://mega.nz/file/lS1iyQCT#zJhV6URsT01QJpYdqbf3Jubhyi09rXn8FFT-HaXvgd0

#### Sites

- Big Titty Anon's List of Artists (contains some notes): https://rentry.org/anime_and_titties 
- 🥒 Study (1) (SD 1.4): https://rentry.org/artists_sd-v1-4
	- Anon's analysis of artists: https://rentry.org/oadb5
- Study (2): https://www.urania.ai/top-sd-artists
- Study (3) (SD 1.5): https://docs.google.com/spreadsheets/d/1SRqJ7F_6yHVSOeCi3U82aA448TqEGrUlRrLLZ51abLg/htmlview#
- Study (4): https://sdartists.app/
- Study (5) (has multiple views): https://proximacentaurib.notion.site/e28a4f8d97724f14a784a538b8589e7d?v=ab624266c6a44413b42a6c57a41d828c
- Study (6): https://mpost.io/midjourney-and-dall-e-artist-styles-dump-with-examples-130-famous-ai-painting-techniques/
- Study (7): https://sgreens.notion.site/sgreens/4ca6f4e229e24da6845b6d49e6b08ae7
- Study (8): https://arthive.com/artists
- Study (9): https://artiststostudy.pages.dev/
- Study (10) (414 artists, Berry Mix): https://mega.nz/file/MX00jb6I#sWbvlt8AhH0B2CZTJJVmfz-LTZIB9O0sLYqjoWbvwN0
- Study (11) (558 artists recognized by SD): https://decentralizedcreator.com/list-of-artists-supported-by-stable-diffusion/

### Other Comparisons

- 🥒 The MegaGrid by mcmonkey#6666, an X/Y grid of every core setting in SD + explanations: https://sd.mcmonkey.org/megagrid/
- 🥒 Anything v3 (all samplers and clip skip, nsfw): https://ikaridevgit.github.io/Clip-skip_sampler-sd-anything-comparison/
- 🥒 Anythingv3 comparison 2 (all samplers and clip skip, sfw): https://ikaridevgit.github.io/sampler-sd-anything-comparison/
- SD 1.4 vs 1.5: https://postimg.cc/gallery/mhvWsnx
- NAI vs Anything: https://www.bilibili.com/read/cv19603218
- Model merge (1): https://files.catbox.moe/rcxqsi.png
- Model merge (2): https://files.catbox.moe/vgv44j.jpg
- Samplers vs Steps (1): https://files.catbox.moe/csrjt5.jpg
- Samplers vs Steps (2): https://i.redd.it/o440iq04ocy91.jpg (https://www.reddit.com/r/StableDiffusion/comments/ynt7ap/another_new_sampler_steps_comparison/)
- Samplers vs Steps (3): https://i.redd.it/ck4ujoz2k6y91.jpg (https://www.reddit.com/r/StableDiffusion/comments/yn2yp2/automatic1111_added_more_samplers_so_heres_a/)
- Samplers vs Steps (4): https://files.catbox.moe/u2d6mf.png
- Samplers vs Steps (5): https://www.reddit.com/r/StableDiffusion/comments/xmwcrx/a_comparison_between_8_samplers_for_5_different/
- Samplers vs Steps (6): https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/4363
- Samplers: https://files.catbox.moe/5hfl9h.png
- VAEs (none, SD, WD, Anything, NAI): https://i.4cdn.org/g/1669056754991690.png
- Clip Skip comparison for Anything.ckpt (missing)

### Extensions

Extensions are searchable through AUTOMATIC1111's extension browser

### Wildcards

#### Collections

- Collection (1): https://rentry.org/sdWildcardLists
	- https://desuarchive.org/g/thread/89006003#89007479
- Collection (2): https://cdn.lewd.host/EtbKpD8C.zip
- Collection (3): https://github.com/Lopyter/stable-soup-prompts/tree/main/wildcards
- Collection (4): https://github.com/Lopyter/sd-artists-wildcards 
	- Artist wildcard text files split by category according to Automatic1111's csv file.
- Collection (5): https://github.com/jtkelm2/stable-diffusion-webui-1/tree/master/scripts/wildcards
- 🥒 Collection (6): https://rentry.org/NAIwildcards
	- Zipped Collection: https://files.catbox.moe/s7expb.7z
- 🥒 Collection (7): https://files.catbox.moe/ipqljx.zip 483 txt files, huge dump (for Danbooru trained models)
	- old 329 version: https://files.catbox.moe/qy6vaf.zip
	- old 314 version: https://files.catbox.moe/11s1tn.zip
- Collection (8): https://www.mediafire.com/file/iceamfawqhn5kvu/wildcards.zip/file
- Collection (9): https://files.catbox.moe/88s7bf.zip Clothing
- 🥒 Collection (10): https://files.catbox.moe/qyybik.zip
- Collection (11): https://cdn.lewd.host/4Ql5bhQD.7z
- 🥒 Collection (12): https://files.catbox.moe/hz5mom.zip Danbooru tag group wildcard dump organized into folders
- Collection (13): https://github.com/jtkelm2/stable-diffusion-webui-1/tree/main/scripts/wildcards

#### Text Files

- faces https://rentry.org/pu8z5
- focus https://rentry.org/rc3dp
- poses https://rentry.org/hkuuk
- times https://rentry.org/izc4u
- views https://rentry.org/pv72o
- Clothing: https://pastebin.com/EyghiB2F
- 316 colors list: https://pastebin.com/s4tqKB8r
- 82 colors list: https://pastebin.com/kiSEViGA
- Backgrounds: https://pastebin.com/FCybuqYW
- More clothing: https://pastebin.com/DrkG1MRw
- Styles: https://pastebin.com/71HTfsML
- Word list (small): https://cdn.lewd.host/EtbKpD8C.zip 
- Emotions/expressions: https://pastebin.com/VVnH2b83
- Clothing: https://pastebin.com/cXxN1fJw
- Cum: https://rentry.org/hoom5
- Locations: https://pastebin.com/R6ugwd2m
- Clothing/outfits: https://pastebin.com/Xhhnyfvj
- Locations: https://pastebin.com/uyDJMnvC
- Clothes: https://pastebin.com/HaL3rW3j
- Color (has nouns): https://pastebin.com/GTAaLLnm
- Artists: https://pastebin.com/1HpNRRJU
- Animals: https://pastebin.com/aM4PJ2YY
- Food: https://pastebin.com/taFkYwt9
- Characters: https://files.catbox.moe/xe9qj7.txt
- Backgrounds: https://pastebin.com/gVue2q8g 
- Outfits: https://files.catbox.moe/y75qda.txt
- Settings + Minerals: https://pastebin.com/9iznuYvQ
- Hairstyles: https://pastebin.com/X39Kzxh7
- Hairstyles 2: https://pastebin.com/bRWu1Xvv
- Danbooru Poses: https://pastebin.com/RgerA8Ry
- Outfits: https://pastebin.com/Z9aHVpEy
- Poses: https://rentry.org/m9dz6
- Clothes: https://pastebin.com/4a0BscGr
- sex positions: https://files.catbox.moe/tzibuf.txt
- Angles: https://pastebin.com/T8w8HEED
- Poses: https://pastebin.com/bgkunjw2
- Hairstyles: https://pastebin.com/GguTseaR
- Actresses: https://raw.githubusercontent.com/Mylakovich/SD-wildcards/main/wildcards/actress.txt
- Punks: https://pastebin.com/rw2fPSHe
- Curated RPG Character classes (based on TTRPG character class names): https://pastebin.com/6ujb7NNe
- Hairstyle: https://pastebin.com/Ux6SdTdp

- wildcardNames.txt generation script: https://files.catbox.moe/c1c4rx.py
- Another script: https://files.catbox.moe/hvly0p.rar
- Script: https://gist.github.com/h-a-te/30f4a51afff2564b0cfbdf1e490e9187
- UMI AI: https://www.patreon.com/posts/umi-ai-official-73544634
	- Check the presets folder for a lot of dumps

## Plugins for External Apps

I didn't check the safety of these plugins, but you can check the open-source ones yourself

### Photoshop

- Defuser: https://internationaltd.github.io/defuser/ Photoshop/Krita, free, features listed inside
	- https://github.com/internationalTD/defuser
- IvyPhotoshopDiffusion: https://github.com/Invary/IvyPhotoshopDiffusion Photoshop, free, features listed inside
- AestusAi: Photoshop, free, closed source (might change later), website wip
	- https://twitter.com/AestusAi
	- https://discord.gg/U6DG9zthvJ
- FlyingDog: https://www.flyingdog.de/sd/ Photoshop, paid, closed source 

### Krita

- 🥒 auto-sd-paint-ext: https://github.com/Interpause/auto-sd-paint-ext Free, features listed inside
- FlyingDog: https://www.flyingdog.de/sd/en/ free
	- Github: https://github.com/imperator-maximus/stable-diffusion-krita

### GIMP

- Gimp Stable Diffusion: https://github.com/blueturtleai/gimp-stable-diffusion free, open source, features listed inside

### Blender

- Dream Textures: https://github.com/carson-katri/dream-textures Free, Stable Diffusion built-in to the Blender shader editor
- AI Render: https://github.com/benrugg/AI-Render Free, Stable Diffusion in Blender
***
***
***

everything past here is UNSORTED

Prompt word/phrase collection: https://huggingface.co/spaces/Gustavosta/MagicPrompt-Stable-Diffusion/raw/main/ideas.txt

* Anon says that "8k, 4k, (highres:1.1), best quality, (masterpiece:1.3)" leads to nice details

According to an anon, the vae seems to be provide saturation/contrast and some line thickness (vae-ft-ema-56000-ema-pruned, https://huggingface.co/stabilityai/sd-vae-ft-ema-original/blob/main/vae-ft-ema-560000-ema-pruned.ckpt). Example (left with 56k, right with anything vae): https://i.4cdn.org/h/1669086238979897s.jpg

Japanese prompt generator: https://magic-generator.herokuapp.com/  
Build your prompt (chinese): https://tags.novelai.dev/  
NAI Prompts: https://seesaawiki.jp/nai_ch/d/%c8%c7%b8%a2%a5%ad%a5%e3%a5%e9%ba%c6%b8%bd/%a5%a2%a5%cb%a5%e1%b7%cf  
Prompt similarity tester: https://gitlab.com/azamshato/simula

* Apparently a good subwiki: https://seesaawiki.jp/nai_ch/d/%c7%ed%a4%ae%a5%b3%a5%e9%a5%c6%a5%af

Multilingual study: https://jalonso.notion.site/Stable-Diffusion-Language-Comprehension-5209abc77a4f4f999ec6c9b4a48a9ca2

Aesthetic value (imgs used to train SD): https://laion-aesthetic.datasette.io/laion-aesthetic-6pls  
Clip retrieval (text to CLIP to search): https://rom1504.github.io/clip-retrieval/

Aesthetic scorer python script: https://github.com/grexzen/SD-Chad  
Another scorer: https://github.com/christophschuhmann/improved-aesthetic-predictor  
Supposedly another one?: https://developer.huawei.com/consumer/en/hiai/engine/aesthetic-score  
Another Aesthetic Scorer: https://github.com/tsngo/stable-diffusion-webui-aesthetic-image-scorer

NAI to webui translator (not 100% accurate): https://seesaawiki.jp/nai_ch/d/%a5%d7%a5%ed%a5%f3%a5%d7%a5%c8%ca%d1%b4%b9

Prompt editing parts of image but without using img2img/inpaint/prompt editing guide by anon: https://files.catbox.moe/fglywg.JPG

Tip Dump: https://rentry.org/robs-novel-ai-tips  
Tips: https://github.com/TravelingRobot/NAI_Community_Research/wiki/NAI-Diffusion:-Various-Tips-&-Tricks  
Info dump of tips: https://rentry.org/Learnings  
Outdated guide: https://rentry.co/8vaaa  
Tip for more photorealism: https://www.reddit.com/r/StableDiffusion/comments/yhn6xx/comment/iuf1uxl/

* TLDR: add noise to your img before img2img

NAI prompt tips: https://docs.novelai.net/image/promptmixing.html  
NAI tips 2: https://docs.novelai.net/image/uifunctionalities.html

Masterpiece vs no masterpiece: https://desuarchive.org/g/thread/89714899#89715160

DPM-Solver Github: https://github.com/LuChengTHU/dpm-solver

> Prompt: 1girl, pointy ears, white hair, medium hair, ahoge, hair between eyes, green eyes, medium:small breasts, cyberpunk, hair strand, dynamic angle, cute, wide hips, blush, sharp eyes, ear piercing, happy, hair highlights, multicoloured hair, cybersuit, cyber gas mask, spaceship computers, ai core, spaceship interior  
> Negative prompt: lowres, bad anatomy, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, animal ears, panties
> 
> Original image:  
> Steps: 50, Sampler: DDIM, CFG scale: 11, Seed: 3563250880, Size: 1024x1024, Model hash: cc024d46, Denoising strength: 0.57, Clip skip: 2, ENSD: 31337, First pass size: 512x512  
> NAI/SD mix at 0.25

Deep Danbooru: https://github.com/KichangKim/DeepDanbooru  
Demo: https://huggingface.co/spaces/hysts/DeepDanbooru

Embedding tester: https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer

Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

Euler vs. Euler A: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017#discussioncomment-4021588

* Euler: https://cdn.discordapp.com/attachments/1036718343140409354/1036719238607540296/euler.gif

* Euler A: https://cdn.discordapp.com/attachments/1036718343140409354/1036719239018590249/euler_a.gif

According to anon: DPM++ should converge to result much much faster than Euler does. It should still converge to the same result though.

(info by anon) According to https://arxiv.org/pdf/2211.01095.pdf, the M samplers are better than the S samplers

Seed hunting: 

* By nai speedrun asuka imgur anon:

	> made something that might help the highres seed/prompt hunters out there. this mimics the "0x0" firstpass calculation and suggests lowres dimensions based on target higheres size. it also shows data about firstpass cropping as well. it's a single file so you can download and use offline. picrel.  
	> https://preyx.github.io/sd-scale-calc/  
	> view code and download from  
	> https://files.catbox.moe/8ml5et.html  
	> for example you can run "firstpass" lowres batches for seed/prompt hunting, then use them in firstpass size to preserve composition when making highres. 

Script for tagging (like in NAI) in AUTOMATIC's webui: https://github.com/DominikDoom/a1111-sd-webui-tagcomplete  
Danbooru Tag Exporter: https://sleazyfork.org/en/scripts/452976-danbooru-tags-select-to-export  
Another: https://sleazyfork.org/en/scripts/453380-danbooru-tags-select-to-export-edited  
Tags (latest vers): https://sleazyfork.org/en/scripts/453304-get-booru-tags-edited  
Basic gelbooru scraper: https://pastebin.com/0yB9s338  
Scrape danbooru images and tags like fetch.py for e621 for tagging datasets: https://github.com/JetBoom/boorutagparser  
UMI AI: https://www.patreon.com/klokinator

* Discord: https://discord.gg/9K7j7DTfG2

* Author is looking for help filling out and improving wildcards

	* Ex: https://cdn.discordapp.com/attachments/1032201089929453578/1034546970179674122/Popular_Female_Characters.txt

	* Author: Klokinator#0278

	* Looking for wildcards with traits and tags of characters

* Code: https://github.com/Klokinator/UnivAICharGen/

Random Prompts: https://rentry.org/randomprompts  
Python script of generating random NSFW prompts: https://rentry.org/nsfw-random-prompt-gen  
Prompt randomizer: https://github.com/adieyal/sd-dynamic-prompting  
Prompt generator: https://github.com/h-a-te/prompt_generator

* apparently UMI uses these?

http://dalle2-prompt-generator.s3-website-us-west-2.amazonaws.com/  
https://randomwordgenerator.com/  
funny prompt gen that surprisingly works: https://www.grc.com/passwords.htm  
Unprompted extension released: https://github.com/ThereforeGames/unprompted

* HAS ADS

StylePile: https://github.com/some9000/StylePile  
script that pulls prompt from Krea.ai and Lexica.art based on search terms: https://github.com/Vetchems/sd-lexikrea  
randomize generation params for txt2img, works with other extensions: https://github.com/stysmmaker/stable-diffusion-webui-randomize

Ideas for when you have none: https://pentoprint.org/first-line-generator/  
Colors: http://colorcode.is/search?q=pantone

* Image editor for SD for inpainting/outpainting/txt2img/img2img: https://github.com/BlinkDL/Hua

* https://www.painthua.com/ - New GUI focusing on Inpainting and Outpainting

* https://www.reddit.com/r/StableDiffusion/comments/ygp0iv/painthuacom_new_gui_focusing_on_inpainting_and/

* To use it with webui add this to webui-user.bat:  --api --cors-allow-origins=https://www.painthua.com 

* Vid: https://www.bilibili.com/video/BV16e4y1a7ne/

* CLIPSeg (text-based inpainting): https://huggingface.co/spaces/nielsr/text-based-inpainting

External masking for inpainting (no more brush or WIN magnifier): https://github.com/dfaker/stable-diffusion-webui-cv2-external-masking-script  
anon: theres a commanda rg for adding basic painting, its '--gradio-img2img-tool'

Script collection: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Custom-Scripts  
Prompt matrix tutorial: https://gigazine.net/gsc_news/en/20220909-automatic1111-stable-diffusion-webui-prompt-matrix/  
Animation Script: https://github.com/amotile/stable-diffusion-studio  
Animation script 2: https://github.com/Animator-Anon/Animator  
Video Script: https://github.com/memes-forever/Stable-diffusion-webui-video  
Masking Script: https://github.com/dfaker/stable-diffusion-webui-cv2-external-masking-script  
XYZ Grid Script: https://github.com/xrpgame/xyz_plot_script  
Vector Graphics: https://github.com/GeorgLegato/Txt2Vectorgraphics/blob/main/txt2vectorgfx.py  
Txt2mask: https://github.com/ThereforeGames/txt2mask  
Prompt changing scripts:

* https://github.com/yownas/seed_travel

* https://github.com/feffy380/prompt-morph

* https://github.com/EugeoSynthesisThirtyTwo/prompt-interpolation-script-for-sd-webui

* https://github.com/some9000/StylePile

Interpolation script (img2img + txt2img mix): https://github.com/DiceOwl/StableDiffusionStuff

* https://www.reddit.com/r/StableDiffusion/comments/ycgfgo/interpolate_script/

img2tiles script: https://github.com/arcanite24/img2tiles  
Script for outpainting: https://github.com/TKoestlerx/sdexperiments  
Img2img animation script: https://github.com/Animator-Anon/Animator/blob/main/animation_v6.py

* Can use in txt2img mode and combine with https://film-net.github.io/ for content aware interpolation

Google's interpolation script: https://github.com/google-research/frame-interpolation

Deforum guide: https://docs.google.com/document/d/1RrQv7FntzOuLg4ohjRZPVL7iptIyBhwwbcEYEW2OfcI/edit  
Animation Guide: https://rentry.org/AnimAnon#introduction  
Rotoscope guide: https://rentry.org/AnimAnon-Rotoscope

Prompt travel: https://github.com/Kahsolt/stable-diffusion-webui-prompt-travel

* Example (30 min, 5k steps, 124 images): https://i.4cdn.org/g/1668879797247188.webm

More animation guide: https://www.reddit.com/r/StableDiffusion/comments/ymwk53/better_frame_consistency/  
Animation guide + example for face: https://www.reddit.com/r/StableDiffusion/comments/ys434h/animating_generated_face_test/  
Something for aninmation: https://github.com/nicolai256/Few-Shot-Patch-Based-Training

Animating faces by anon: 

* https://github.com/yoyo-nb/Thin-Plate-Spline-Motion-Model

* How to Animate faces from Stable Diffusion!

``` python
workflow looks like this:
>generate square portrait (i use 1024 for this example)
>create or find driving video
>crop driving video to square with ffmpeg, making sure to match the general distance from camera and face position(it does not do well with panning/zooming video or too much head movement)
>run thin-plate-spline-motion-model
>take result.mp4 and put it into Video2x (Waifu2x Caffe)
>put into flowframes for 60fps and webm

>if you don't care about upscaling it makes 256x256 pretty easily
>an extension for webui could probably be made by someone smarter than me, its a bit tedious right now with so many terminals

here is a pastebin of useful commands for my workflow
https://pastebin.com/6Y6ZK8PN
```

Another person who used it: https://www.reddit.com/r/StableDiffusion/comments/ynejta/stable_diffusion_animated_with_thinplate_spline/

Img2img megalist + implementations: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2940

Runway inpaint model: https://huggingface.co/runwayml/stable-diffusion-inpainting

* Tutorial from their github: https://github.com/runwayml/stable-diffusion#inpainting-with-stable-diffusion

Inpainting Tips: https://www.pixiv.net/en/artworks/102083584  
Rentry version: https://rentry.org/inpainting-guide-SD

Extensions:  
Artist inspiration: https://github.com/yfszzx/stable-diffusion-webui-inspiration

* https://huggingface.co/datasets/yfszzx/inspiration

* delete the 0 bytes folders from their dataset zip or you might get an error extracting it

History: https://github.com/yfszzx/stable-diffusion-webui-images-browser  
Collection + Info: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Extensions  
Deforum (video animation): https://github.com/deforum-art/deforum-for-automatic1111-webui

* Math: https://docs.google.com/document/d/1pfW1PwbDIuW0cv-dnuyYj1UzPqe23BlSLTJsqazffXM/edit

	* https://www.desmos.com/calculator/njw3uckjlo

	* https://www.desmos.com/calculator/5nizby2zbn

* Blender camera animations to deforum: https://github.com/micwalk/blender-export-diffusion

* Tutorial: https://www.youtube.com/watch?v=lztn6qLc9UE

* Diffusion_cadence variation value comparison: https://www.reddit.com/r/StableDiffusion/comments/yh3dno/diffusion_cadence_variation_testing_values_to/

Auto-SD-Krita: https://github.com/Interpause/auto-sd-paint-ext

ddetailer (object detection and auto-mask, helpful in fixing faces without manually masking): https://github.com/dustysys/ddetailer  
Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients  
Autocomplete Tags: https://github.com/DominikDoom/a1111-sd-webui-tagcomplete  
Prompt Randomizer: https://github.com/adieyal/sd-dynamic-prompting  
Wildcards: https://github.com/AUTOMATIC1111/stable-diffusion-webui-wildcards/  
Wildcard script + collection of wildcards: https://app.radicle.xyz/seeds/pine.radicle.garden/rad:git:hnrkcfpnw9hd5jb45b6qsqbr97eqcffjm7sby  
Symmetric image script (latent mirroring): https://github.com/dfaker/SD-latent-mirroring

* Comparisons: 

	* No mirroring - https://files.catbox.moe/blbnwt.png (embed)

	* Alternate Steps - Roll Channels - fraction 0.2 - https://files.catbox.moe/dprlxr.png (embed)

	* Alternate Steps - Roll Channels - fraction 0.3 - https://files.catbox.moe/7az24b.png

macOS Finder right-click menu extension: https://github.com/anastasiuspernat/UnderPillow  
Search danbooru for tags directly in AUTOMATIC1111's webui extension: https://github.com/stysmmaker/stable-diffusion-webui-booru-prompt

* Supports post IDs and all the normal Danbooru search syntax

Clip interrogator: https://colab.research.google.com/github/pharmapsychotic/clip-interrogator/blob/main/clip_interrogator.ipynb  
2 (apparently better than AUTO webui's interrogate): https://huggingface.co/spaces/pharma/CLIP-Interrogator, https://github.com/pharmapsychotic/clip-interrogator

Enchancement Workflow with SD Upscale and inpainting by anon: https://pastebin.com/8WVyDxt9

Upscaling + detail with SD Upscale: https://www.reddit.com/r/StableDiffusion/comments/xkjjf9/upscale_to_huge_sizes_and_add_detail_with_sd/?context=3

Inpainting a face by anon:

> send the picture to inpaint  
> modify the prompt to remove anything related to the background  
> add (face) to the prompt  
> slap a masking blob over the whole face  
> mask blur 10-16 (may have to adjust after), masked content: original, inpaint at full resolution checked, full resolution padding 0, sampling steps ~40-50, sampling method DDIM, width and height set to your original picture's full res  
> denoising strength .4-.5 if you want minor adjustments, .6-.7 if you want to really regenerate the entire masked area  
> let it rip

* AUTOMATIC1111 webui modification that "compensates for the natural heavy-headedness of sd by adding a line from 0 -> sqrt(2) over the 0 -> 74 token range (anon)" (evens out the token weights with a linear model, helps with the weight reset at 75 tokens (?))

	* https://rentry.org/wkk37

**VAEs**

Tutorial + how to use on ALL models (applies for the NAI vae too): https://www.reddit.com/r/StableDiffusion/comments/yaknek/you_can_use_the_new_vae_on_old_models_as_well_for/

* SD 1.4 Anime styled: https://huggingface.co/hakurei/waifu-diffusion-v1-4/blob/main/vae/kl-f8-anime.ckpt

	* https://twitter.com/haruu1367/status/1579286947519864833

* Stability AI's VAE: https://huggingface.co/stabilityai 

	* Comparisons: https://huggingface.co/stabilityai/sd-vae-ft-mse-original

	* an anon recommended vae-ft-mse-840k-ema-pruned: https://huggingface.co/stabilityai/sd-vae-ft-mse-original/resolve/main/vae-ft-mse-840000-ema-pruned.ckpt, https://huggingface.co/stabilityai/sd-vae-ft-mse-original/tree/main

* Trinart's vae (the autencoder fix): https://huggingface.co/naclbit/trinart_characters_19.2m_stable_diffusion_v1

**Booru tag scraping:**

* https://sleazyfork.org/en/scripts/451098-get-booru-tags 

	* script to run in browser, hover over pic in Danbooru and Gelbooru

* https://rentry.org/owmmt 

	* another script 

* https://pastecode.io/s/jexs5p9c

	* another script, maybe pickle

	* press tilde on dan, gel, e621 

* https://textedit.tools/

	* if you want an online alternative

* https://github.com/onusai/grab-booru-tags

	* works with e621, dev will try to get it to work with rule34.xxx

	* https://pastecode.io/s/jexs5p9c

* https://pastecode.io/s/61owr7mz

	* Press ] on the page you want the tags from

* Another script: https://pastecode.io/s/q6fpoa8k

* Another: https://pastecode.io/s/t7qg2z67

* Github for scraper: https://github.com/onusai/grab-booru-tags 

* Tag copier: https://greasyfork.org/en/scripts/453443-danbooru-tag-copier

**Creating fake animes:**

* https://rentry.org/animedoesnotexist

* Prompt tag comparisons: https://i.4cdn.org/h/1668114368781212.jpg, https://i.4cdn.org/h/1668119420557795.jpg, https://i.4cdn.org/h/1668126729971806.jpg

Reduce bias of dreambooth models: https://www.reddit.com/r/StableDiffusion/comments/ygyq2j/a_simple_method_explained_in_the_comments_to/?utm_source=share&utm_medium=web2x&context=3

Landscape tutorial: https://www.reddit.com/r/StableDiffusion/comments/yivokx/landscape_matte_painting_with_stable_diffusion/

* https://preview.redd.it/18v93697u8x91.jpg?width=1000&format=pjpg&auto=webp&s=d31fb3efae70ec5e7c9f02befa04a94371b1bbf6

Img2img rotoscoping tutorial by anon:

``` python
1. extract image sequence from video
2. testing prompt by using the 1st photo from the batch
3. find the suitable prompt that you want, the pose/sexual acts should be the same as the original to prevent weirdness
4. CFG Scale and Denoising Strength is very important
> Low CFG Scale will make your image less follow your prompt and make it more blurry and messy (i use 9-13)
> Denoising Strength determines the mix between your prompt and your image: 0 = Original input 1 = Only Prompt, nothing resemble of the input except the colors.
the interesting thing that i've noticed from Denoising strength is not linear, its behave more exponential ( my speculation is 0-0.6 = still reminds of the original 0.61-0.76 = starting to change 0.77-1 = change a lot )
5. sampler:
> Euler-a is quite nice, but lack of consistency between the step, adding/lower 1 step can change the entire photo
> Euler is better than euler-a in terms of consistency but requires more steps = longer generation time between each image
> DPM++ 2S a Karras is the best in quality (for me) but it is very slow, good for generate single image
> DDIM is the fastest and very useful for this case, 20-30 steps can produces a nice quality anime image.
6. test prompting into a batch of 4-6 to choosing a seed
7. Batch img2img
8. Assembling the generated images into video, i don't want to use eveyframes so i rendered into 2 frame steps and half the frame rate
9. Use Flowframes to interpolate the inbetween frame to match the original video frame rate.
```

Ex: https://files.catbox.moe/e30szo.mp4

File2prompt (I think it's multiple generations in a row?): https://rentry.org/file2prompt

## Models, Embeddings, and Hypernetworks

* Open source SD model based on chinese text and images: https://huggingface.co/IDEA-CCNL/Taiyi-Stable-Diffusion-1B-Chinese-v0.1

!!! Downloads listed as "sus" or "might be pickled" generally mean there were 0 replies and not enough "information" (like training info). or, the replies indicated they were suspicious. I don't think any of the embeds/hypernets have had their code checked so they could all be malicious, but as far as I know no one has gotten pickled yet 

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

### **Models***

Model pruner: https://github.com/harubaru/waifu-diffusion/blob/bc626e8/scripts/prune.py

🥒 CivitAI, an art-focused model repo alternative to HF: https://civitai.com/  
🥒 HuggingFace, the standard model repo: https://huggingface.co/models?pipeline_tag=text-to-image&sort=downloads  
Collection of potentially dangerous models: https://bt4g.org/search/.ckpt/1

* V1 repo: https://github.com/CompVis/stable-diffusion

* V2 repo: https://github.com/Stability-AI/stablediffusion

``` python
Direct Downloads (no login needed)
https://huggingface.co/stabilityai/stable-diffusion-2/resolve/main/768-v-ema.ckpt
https://huggingface.co/stabilityai/stable-diffusion-2-base/resolve/main/512-base-ema.ckpt
https://huggingface.co/stabilityai/stable-diffusion-2-depth/resolve/main/512-depth-ema.ckpt
https://huggingface.co/stabilityai/stable-diffusion-2-inpainting/resolve/main/512-inpainting-ema.ckpt
https://huggingface.co/stabilityai/stable-diffusion-x4-upscaler/resolve/main/x4-upscaler-ema.ckpt

License: https://huggingface.co/stabilityai/stable-diffusion-2/raw/main/LICENSE-MODEL

Torrent for the 2.0 release by anon. License text included so that it's okay to distribute.

magnet:?xt=urn:btih:f193c9cb1e542f5ea264dfcaeb014635ddf4b25b&dn=stable-diffusion-2&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

Other:

magnet:?xt=urn:btih:cce6f4ee630efadd365fe4f1655c733e0551d50f&dn=stable-diffusion-2-base&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

magnet:?xt=urn:btih:ceeb6f68b3b08a4bf6216330a01cecb648ace936&dn=stable-diffusion-2-depth&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

magnet:?xt=urn:btih:844341921a40b2202a0d97eb17f749281f6566ec&dn=stable-diffusion-2-inpainting&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

magnet:?xt=urn:btih:ab224077b6f04012f1bc5527ef08e50bab1fb1d5&dn=stable-diffusion-x4-upscaler&tr=udp%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce

"You can check that I didn't pickle these torrents by comparing the .ckpt file's hash against the SHA256 hashes on the official repo. No login needed."

https://huggingface.co/stabilityai/stable-diffusion-2/blob/main/768-v-ema.ckpt
```

* anything.ckpt (v3 6569e224; v2.1 619c23f0), a Chinese finetune/training continuation of NAI, is released: https://www.bilibili.com/read/cv19603218

	* Huggingface: https://huggingface.co/Linaqruf/anything-v3.0/tree/main

	* Torrent: https://rentry.org/sdmodels#anything-v30-38c1ebe3-1a7df6b8-6569e224

	* Supposed ddl, I didn't check these for pickles: https://rentry.org/NAI-Anything_v3_0_n_v2_1

	* instructions to download from Baidu from outside China and without SMS or an account and with speeds more than 100KBps: 

		> Download a download manager that allows for a custom user-agent (e.g. IDM)  
			> If you need IDM, contact me  
		> Go here: https://udown.vip/#/  
		> In the "在线解析" section, put 'https://pan.baidu.com/s/1gsk77KWljqPBYRYnuzVfvQ' into the first prompt box and 'hheg' in the second (remove the ')  
		> Click the first blue button  
		> In the bottom box area, click the folder icon next to NovelAI  
		> Open your dl manager and add 'netdisk;11.33.3;' into the user-agent section (remove the ')  
		> Click the paperclip icon next to the item you want to download in the bottom box and put it into your download manager
		> 
		> To get anything v3 and v2.1: first box:https://pan.baidu.com/s/1r--2XuWV--MVoKKmTftM-g, second box:ANYN  
			* another link that has 1 letter changed that could mean it's pickled: https://pan.baidu.com/s/1r--2XuWV--MVoKKmTfyM-g

	* seems to be better (e.g. provide more detailed backgrounds and characters) than NAI, but can overfry some stuff. Try lowering the cfg if that happens

	* Passes AUTOMATIC's pickle tester and https://github.com/zxix/stable-diffusion-pickle-scanner, but there's no guarantee on pickle safety, so it still might be ccp spyware

	* Use the vae or else your outputs will have a grey filter

	* Windows Defender might mark this as a virus, it should be a false positive

```

from: https://bt4g.org/magnet/689c0fe075ab4c7b6c08a6f1e633491d41186860

another magnet on https://rentry.org/sdmodels from the author

* Mixed SFW/NSFW Pony/Furry V2 from AstraliteHeart: https://mega.nz/file/Va0Q0B4L#QAkbI2v0CnPkjMkK9IIJb2RZTegooQ8s6EpSm1S4CDk

* Mega mixing guide (has a different berry mix): https://rentry.org/lftbl
	* Model showcases from lftbl: https://rentry.co/LFTBL-showcase

* Cafe Unofficial Instagram TEST Model Release
	* Trained on ~140k 640x640 Instagram images made up of primarily Japanese accounts (mix of cosplay, model, and personal accounts)
	* Note: While the model can create some realistic (Japanese) Instagram-esque images on its own, for full potential, it is recommended that it be merged with another model (such as berry or anything)
	* Note: Use CLIP 2 and resolutions greater than 640x640

* Artstation Models (by WD dev): https://huggingface.co/hakurei/artstation-diffusion
	* Prebuilt ckpt (not sure if safe): https://huggingface.co/NoCrypt/artstation-diffusion/tree/main

* Nitro Diffusion (Multi-style model trained on three artstyles, archer style, arcane style, and modern disney style): https://huggingface.co/nitrosocke/Nitro-Diffusion

* High quality anime images (eimisanimediffusion): https://huggingface.co/eimiss/EimisAnimeDiffusion_1.0v

*Hrrzg style 768px: https://huggingface.co/TheLastBen/hrrzg-style-768px

* Ghibli Diffusion (tokens: ghibli style): https://huggingface.co/nitrosocke/Ghibli-Diffusion

- Pokemono Diffusers: https://huggingface.co/lambdalabs/sd-pokemon-diffusers/tree/main

* Animus's premium models got leaked (not sure if safe): https://rentry.org/animusmixed
	- Drive links pass the pickle test
	- Linked directly from his patreon: https://www.patreon.com/posts/all-of-my-free-74510576

**MODEL MIXES**

Raspberry mix download by anon (not sure if safe): https://pixeldrain.com/u/F2mkQEYp
Strawberry Mix (anon, safety caution): https://pixeldrain.com/u/z5vNbVYc

``` python
magnet:?xt=urn:btih:eb085b3e22310a338e6ea00172cb887c10c54cbc&dn=cafe-instagram-unofficial-test-epoch-9-140k-images-fp32.ckpt&tr=udp%3A%2F%2Ftracker.openbittorrent.com%3A80&tr=udp%3A%2F%2Fopentor.org%3A2710&tr=udp%3A%2F%2Ftracker.ccc.de%3A80&tr=udp%3A%2F%2Ftracker.blackunicorn.xyz%3A6969&tr=udp%3A%2F%2Ftracker.coppersurfer.tk%3A6969&tr=udp%3A%2F%2Ftracker.leechers-paradise.org%3A6969
```

ThisModel:

1. (Weighted Sum 0.05) Anything3 + SD1.5 = Temp1
2. (Add Difference 1.0) Temp1 + F222 + SD1.5 = Temp2
3. (Weighted Sum 0.2) Temp2 + TrinArt2_115000 = ThisModel

Anon's model for vampires(?):

``` python
My steps

Step 1:
>A : Anything-V3.0
>B : trinart2_step115000.ckpt [f1c7e952]
>C : stable-diffusion-v-1-4-original

A from https://huggingface.co/Linaqruf/anything-v3.0/blob/main/Anything-V3.0-pruned.ckpt
B from https://rentry.org/sdmodels#trinart2_step115000ckpt-f1c7e952
C from https://huggingface.co/CompVis/stable-diffusion-v-1-4-original/blob/main/sd-v1-4.ckpt

and I "Add Difference" at 0.45, and name as part1.ckpt

Step 2:
>A : part1.ckpt (What I made in Step 1)
>B: Cafe Unofficial Instagram TEST Model [50b987ae]

B is from https://rentry.org/sdmodels#cafe-unofficial-instagram-test-model-50b987ae

and I "Weighted Sum" at 0.5, and name it TrinArtMix.ckpt
```

* Samdoesbimbos (sandoesart dreambooth dehydrated from original model and hydrated into thepit bimbo dreambooth): https://mega.nz/file/xpECiaAI#_KeDMAvxAnyOkLlo82IP09BHc1KBZoUfT-0jFaDhF3c

	* One recommended merge: f222@0.12 and sd15wd12@0.2

	* Another is F222 SD15 WD12 SxDv0.8 at low ratios (0.1-0.4)

Antler's Mix (didn't check for pickles)  
https://mega.nz/file/nZtz0LZL#ExSHp7icsZedxOH_yRUOKAliPGfKRsWiOYHqULZy9Yo

Alternate mix, apparently? (didn't check for pickles)

> ((anything_0.95 + sd-1.5_0.05) + f222 - sd-1.5)_0.75 + trinart2_115000_0.25 

RandoMix2 (didn't check for pickles)  
magnet:?xt=urn:btih:AB6A6C3F6AA0858030B9B85D28B243A4FF9F5935&dn=RandoMix2.zip&tr=udp%3A%2F%2Ftracker.torrent.eu.org%3A451%2Fannounce&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce

RaptorBerry (didn't check for pickles)  
magnet:?xt=urn:btih:166c9caf38801ba4e10912b5c91ccaaec585534c&dn=RaptorBerry%20Final%20Mix.ckpt&tr=http%3a%2f%2ftracker.opentrackr.org%3a1337%2fannounce&tr=http%3a%2f%2ftracker.openbittorrent.com%3a80%2fannounce&tr=udp%3a%2f%2fopentracker.i2p.rocks%3a6969%2fannounce&tr=udp%3a%2f%2fopen.stealth.si%3a80%2fannounce&tr=udp%3a%2f%2ftracker.torrent.eu.org%3a451%2fannounce

NAI+SD+Trinart characters+Trinart+F222 (weighted sum, values less than 0.3): https://mega.nz/file/JblSFKia#n8JNfYWXaMeeQEstB-1A1Ju5u3m9I-u-n3WcmVpz2lo

```
"Ben Dover Mix"©®™ is my mix
if you're interested
follow this guide https://rentry.org/lftbl#berrymix
The mix is done exactly the same way as berrymix
but with anythingv3 instead of nai
f222 instead of f111
and sd v1.5 instead of sd v1.4
```

https://rentry.org/ben_dover

AloeVera mix: https://mega.nz/file/4bEzxB6Q#j3QwgNxHiYOmT8Y4OgHP9mlzvFbCkEK1DUepMoIBI50

Nutmeg mix:

``` python
0.05 NAI + SD1.5
0.05 mix + f222
0.05 mix + r34
0.05 mix + SF
0.3 Anything + mix
```

Hyper-versatile SD model: https://huggingface.co/BuniRemo/Redshift-WD12-SD14-NAI-FMD_Checkpoint_Merger_-_Hyper-Versatile_Stable_Diffusion_Model

* Made from Redshift Diffusion, Waifu Diffusion 1.2, Stable Diffusion 1.4, Novel AI, Yiffy, and Zack3D_Kinky-v1; capable of rendering humans, furries, landscapes, backgrounds, buildings, Disney style, painterly styles, and more

Hassan (has a few mixes, not sure if the dls are safe): https://rentry.org/sdhassan

* An anon recommended the Hassan1.3 if you do 3DPD

* 1.4 ex: https://imgur.com/a/TUWkJmh

Anonmix: 

> Weighted Sum @ 0.05 to make tempmodel1
> 
> A: Anything.V3, B: SD1.5, C: null
> 
> Add Difference @ 1.0 to make tempmodel2
> 
> A: tempmodel1, B: Zeipher F222, C: SD1.5
> 
> Weighted Sum @ 0.25 to make tempmodel3
> 
> A: tempmodel2, B: r34_e4, C: Null
> 
> Weighted Sum @ 0.20 to make FINAL MODEL
> 
> A: tempmodel3, B: NAI

SquidwardBlendv2: https://mega.nz/file/r9MzkQxb#QeiM9HJf0wAw68yg-q9RtrbGucB7h712yu-EpvFX3n0

- "generates consistent quality realistic painterly tasteful nudes"
- Ex: https://i.4cdn.org/g/1669218820252711.png
- https://www.reddit.com/r/sdnsfw/comments/z1ymul/squidwardblendv2/

Big collection of berry mixes: https://rentry.org/dbhhk (https://archived.moe/h/thread/6984678/#q6985842)

Super duper mixing cookbook from hdg (most updated): https://rentry.org/hdgrecipes

### **EveryDream Trainer**

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

Download + info + prompt templates: https://github.com/victorchall/EveryDream-trainer

* by anon: allows you to train multiple subjects quickly via labelling file names but it requires a normalization training set of random labelled images in order to preserve model integrity

* Made in Abyss: https://drive.google.com/drive/u/0/folders/1FxFitSdqMmR-fNrULmTpaQwKEefi4UGI

	* https://old.reddit.com/r/StableDiffusion/comments/ylroyp/made_in_abyss_dreambooth_model_i_am_working_on/

	* Download reply: https://old.reddit.com/r/StableDiffusion/comments/ylroyp/made_in_abyss_dreambooth_model_i_am_working_on/iv3w5b3/

### **Dreambooth Models:**

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

Links:

* https://huggingface.co/waifu-research-department

* https://huggingface.co/jinofcoolnes

	* For preview pics/descriptions:

		* https://www.reddit.com/user/jinofcool/

		* https://www.patreon.com/Rahmel

* https://huggingface.co/nitrosocke

* Toolkit anon: https://huggingface.co/demibit/

* https://rentry.org/sdmodels

* Big collection: https://publicprompts.art/

* Big collection of sex models (Might be a large pickle, so be careful): https://rentry.org/kwai

* Collection: https://cyberes.github.io/stable-diffusion-dreambooth-library/

* /vt/ collection: https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ/folder/L2AmBRZC

* Big collection: https://publicprompts.art/

* Chinese collection of Dreambooth models: https://docs.qq.com/sheet/DTVZEd3VqSWhDTXNY?tab=BB08J2

	* Website: https://aimodel.subrecovery.top/

	* Main download: https://www.aliyundrive.com/s/62ha51rH6Uw

		* Apparently, most of the exes from the aliyundrive site are self-extracting, so it might be a miner, virus, etc.

* Nami: https://mega.nz/file/VlQk0IzC#8MEhKER_IjoS8zj8POFDm3ZVLHddNG5woOcGdz4bNLc

* https://huggingface.co/IShallRiseAgain/StudioGhibli/tree/main

* Jinx: https://huggingface.co/jinofcoolnes/sksjinxmerge/tree/main

	* Another: https://drive.google.com/drive/folders/1-Gz7R9X8tSZV7D8oyxqY0zo-BFcXN1_X

	* https://twitter.com/Rahmeljackson/status/1580244475649007616?s=20&t=PNe7aQsh1k1cXsjVyKSeaQ

* Arcane Vi: https://huggingface.co/jinofcoolnes/VImodel/tree/main

* Lucy (Edgerunners): https://huggingface.co/jinofcoolnes/Lucymodel/tree/main

	* https://www.patreon.com/posts/73414085

	* https://twitter.com/Rahmeljackson/status/1582019346867441666?s=20&t=3K2kJ2zQna4a24-AoVJWpw

* Gundam (full ema, non pruned): https://huggingface.co/Gazoche/stable-diffusion-gundam

* Starsector Portraits: https://huggingface.co/Severian-Void/Starsector-Portraits

* Evangelion style: https://huggingface.co/crumb/eva-fusion-v2

* Robo Diffusion: https://huggingface.co/nousr/robo-diffusion/tree/main/models

* Arcane Diffusion: https://huggingface.co/nitrosocke/Arcane-Diffusion

* Archer: https://huggingface.co/nitrosocke/archer-diffusion

* Wikihow style: https://huggingface.co/jvkape/WikiHowSDModel

	* 60 Images. 2500 Steps. Embedding Aesthetics + 40 Image Embedding options

	* Their patreon: https://www.patreon.com/user?u=81570187

* Lain girl: https://mega.nz/file/VK0U0ALD#YDfGgOu8rquuR5FbFxmzKD5hzxO1iF0YQafN0ipw-Ck

* Wikiart: https://huggingface.co/valhalla/sd-wikiart-v2/tree/main/unet

	* diffusion_pytorch_model.bin, just rename to whatever.ckpt

* Megaman zero: https://huggingface.co/jinofcoolnes/Zeromodel/tree/main

	* https://www.patreon.com/posts/zero-model-73763667?utm_medium=clipboard_copy&utm_source=copyLink&utm_campaign=postshare_creator

	* https://twitter.com/Rahmeljackson/status/1584947512573448197?s=20&t=wVbTLod2aV_uaQdqejNFfg

* Cyberware: https://huggingface.co/Eppinette/Cyberware/tree/main

* taffy (keyword: champi): https://drive.google.com/file/d/1ZKBf63fV1Zm5_-a0bZzYsvwhnO16N6j6/view?usp=sharing

	* https://arca.live/b/hypernetworks/60931350?category=%EA%B3%B5%EC%9C%A0&p=2

* Disney (3d?): https://huggingface.co/nitrosocke/modern-disney-diffusion/

* El Risitas (KEK guy): https://huggingface.co/Fictiverse/ElRisitas

* Cyberpunk Anime Diffusion: https://huggingface.co/DGSpitzer/Cyberpunk-Anime-Diffusion

* Kurzgesagt (called with "kurzgesagt! style"): https://drive.google.com/file/d/1-LRNSU-msR7W1HgjWf8g1UhgD_NfQjJ4/view?usp=sharing

	* SHA-256: d47168677d75045ae1a3efb8ba911f87cfcde4fba38d5c601ef9e008ccc6086a

* Robodiffusion (good outputs for "meh" prompting): https://huggingface.co/nousr/robo-diffusion

* 2D Illustration style: https://huggingface.co/ogkalu/hollie-mengert-artstyle

	* https://www.reddit.com/r/StableDiffusion/comments/yaquby/2d_illustration_styles_are_scarce_on_stable/

* Rebecca (edgerunners, by booru anon, info is in link): https://huggingface.co/demibit/rebecca

* Kiwi (by booru anon): https://huggingface.co/demibit/kiwi

* Ranni (Elden Ring): https://huggingface.co/bitspirit3/SD-Ranni-dreambooth-finetune

* Cloud: https://huggingface.co/jinofcoolnes/cloud/tree/main

	* https://twitter.com/Rahmeljackson/status/1586037466548551681?s=20&t=F9mU9uOFEDGKYTVl00DzUg

	* https://www.patreon.com/posts/73899634?pr=true

* Comics: https://huggingface.co/ogkalu/Comic-Diffusion

* Modern Disney style (modi, mo-di): https://huggingface.co/nitrosocke/mo-di-diffusion/

* Silco: https://huggingface.co/jinofcoolnes/silcomodel/tree/main

	* https://www.patreon.com/posts/silco-model-73477832?utm_medium=clipboard_copy&utm_source=copyLink&utm_campaign=postshare_creator

	* https://twitter.com/Rahmeljackson/status/1582515393381662720?s=20&t=K1tuYmsK4Xo9RBLcqooD-A

* Lara: https://huggingface.co/jinofcoolnes/Oglaramodel/tree/main

	* https://twitter.com/Rahmeljackson/status/1583297706457329664?s=20&t=91YzDUX-fE1dOXehK5Oe-g

	* https://www.patreon.com/posts/73578982

* theofficialpit bimbo (26 pics for 2600 steps, Use "thepit bimbo" in prompt for more effect): https://mega.nz/file/wSdigRxJ#WrF8cw85SDebO8EK35gIjYIl7HYAz6WqOxcA-pWJ_X8

* DCAU (Batman_the_animated_series): https://huggingface.co/IShallRiseAgain/DCAU/blob/main/DCAUV1.ckpt

	* https://www.reddit.com/r/StableDiffusion/comments/yf2qz0/initial_version_of_dcau_model_im_making/

	* hand captioning 782 screencap, 44,000 steps, training set for the regularization images

* NSFW: https://megaupload.nz/N7m7S4E7yf/Magnum_Opus_alpha_22500_steps_mini_version_ckpt

	* Dataset: https://megaupload.nz/wep7S7E0y3/magnum_opus_training_data_set_zip

* Hardcore: https://pixeldrain.com/u/Stk98vyH

	* Trained on 3498 images and around 250K steps

		* porn, sex acts of all sorts: anal sex, anilingus, ass, ass fingering, ball sucking, blowjob, cumshot, cunnilingus, dick, dildo, double penetration, exposed pussy, female masturbation, fingering, full nelson, handjob, large ass, large tits, lesbian kissing, massive ass, massive tits, o-face, sixty-nine, spread pussy, tentacle sex (try also oral/anal tentacle sex and tentacle dp), tit fucking, tit sucking, underboob, vaginal sex, long tongue, tits

	* Example grid from training (single shot batch): https://cdn.discordapp.com/attachments/1010982959525929010/1035236689850941440/samples_gs-995960_e-000046_b000000.png

* disney 2d (classic) animation style: https://huggingface.co/nitrosocke/classic-anim-diffusion

	* https://www.reddit.com/r/StableDiffusion/comments/yhikn3/new_dreambooth_model_classic_animation_styles/

* Kim Jung Gi: https://drive.google.com/drive/folders/1uL-oUUhuHL-g97ydqpDpHRC1m3HVcqBt

	* https://twitter.com/bg_5you/status/1578146498768175105

* Pyro's Blowjob Model: https://rentry.org/pyros-sd-model

	* https://anonfiles.com/6123m6F6y9/pyros-bj-v1-0_ckpt

	* https://mega.nz/file/lLtjCLwb#KgXPDzbTotcb0_quzzBMm6DaDCuSFIaF8CXxw1WsEs8

	* Examples: https://www.reddit.com/gallery/yhuymu

	* Examples: https://old.reddit.com/r/sdnsfw/comments/yhuymu/ill_never_need_any_porn_site_ever_again/

* Pixel Art Sprite Sheet (stardew valley): https://huggingface.co/Onodofthenorth/SD_PixelArt_SpriteSheet_Generator

	* 4 different angles

	* Examples + Reddit post: https://www.reddit.com/r/StableDiffusion/comments/yj1kbi/ive_trained_a_new_model_to_output_pixel_art/

* WLOP: https://huggingface.co/SirVeggie/wlop

* corporate memphis A.I model (infographics): https://huggingface.co/jinofcoolnes/corporate_memphis/tree/main

	* https://twitter.com/Rahmeljackson/status/1588435864769925121?s=20&t=j2jCYpS7HW8WjgK15Hg7BA

	* https://www.patreon.com/posts/74213085?pr=true

* Tron: https://huggingface.co/dallinmackay/Tron-Legacy-diffusion

	* https://www.reddit.com/r/StableDiffusion/comments/yi3nty/my_tronstyle_dreambooth_model_available_to/

* Superhero: https://huggingface.co/ogkalu/Superhero-Diffusion

	* https://www.reddit.com/r/StableDiffusion/comments/yl3ug8/superhero_diffusion_new_dreambooth_model/

* Chicken (trained on images from r/chickens): https://huggingface.co/fake4325634/chkn

	* https://www.reddit.com/r/StableDiffusion/comments/ylmcov/chicken_diffusion_dreambooth_model/

* 1.5 based model created from the Spede images (not too sure if this is Dreambooth): https://mega.nz/file/mdcVARhL#FUq5TL2xp7FuzzgMS4B20sOYYnPZsyPMw93sPMHeQ78

* Redshift Diffusion (High quality 3D renders): https://huggingface.co/nitrosocke/redshift-diffusion

	* https://www.reddit.com/r/StableDiffusion/comments/ynz33f/dreambooth_model_release_redshift_diffusion_high/

* Cats: https://huggingface.co/dallinmackay/Cats-Musical-diffusion

* Van Gogh: https://huggingface.co/dallinmackay/Van-Gogh-diffusion

	* https://www.reddit.com/r/StableDiffusion/comments/ymtud0/my_van_gogh_style_loving_vincent_dreambooth_model/

* Rouge the Bat (44 SFW images of Rouge the Bat for 1600 or 2400 steps, keyword: 'rkugasebz'): https://huggingface.co/ChanseyIsForeverAI/Rouge-the-bat-dreambooth

	* Examples: https://i.imgur.com/X12W59D.png  
				https://i.imgur.com/Lpul7Pf.png  
				https://i.imgur.com/r0bc6i8.png  
				https://i.imgur.com/gkEW0w0.png  
				https://i.imgur.com/Zj8PtZC.png

* Made in Abyss (MIA 1-6 V2): https://drive.google.com/drive/folders/1FxFitSdqMmR-fNrULmTpaQwKEefi4UGI?usp=sharing

	* Uploader note: I was hesitant to share this one because I have been having a lot of problems with the new captioning format. With the new format essentially we have much better multiple character flexibility and outfits. You can generate 2 characters in completely separate outfits with a high percentage of no blending. However, my new captioning was causing everything to train significantly slower, so some side characters don't look as good as they did in the original 1-6 model. There is also a strict captioning format I used, so I also uploaded a prompt readme to the folder which contains all the information needed to best use this model 

* Gyokai/onono imoko/@_himehajime: https://mega.nz/folder/HzYT1T7L#H9TWVVYowA0cX8Eh6x_H3g

	* use term 'gyokai' under class '1girl' e.g 'illustration of gyokai 1girl' + optionally 'multicolored hair, halftone, polka dot'

	* Img: https://i.4cdn.org/h/1667881224238388.jpg

* Amano: https://huggingface.co/RayHell/Amano-Diffusion

* Midjourney: https://huggingface.co/prompthero/midjourney-v4-diffusion

* Borderlands (training info in reddit):  
https://www.reddit.com/r/StableDiffusion/comments/yong77/borderlands_model_works_for/

	* https://publicprompts.art/borderlands-dreambooth-model/

* Pixel art model: https://publicprompts.art/all-in-one-pixel-art-dreambooth-model/

	* https://www.reddit.com/r/stablediffusion/comments/yqtm3k

* Satania (has two iterations of the model, 500 step has more flexibility but 1k can look nicer if you want base Satania, link will expire soon): https://i.mmaker.moe/sd/mmkr-greatmosu-satania.7z

* Pokemon: https://huggingface.co/justinpinkney/pokemon-stable-diffusion

* final fantasy tactics: https://huggingface.co/jinofcoolnes/FinalfantasyTactics/tree/main

	* https://twitter.com/Rahmeljackson/status/1590401243641368576

	* https://www.patreon.com/posts/final-fantasy-74440534

* smthdssmth: https://huggingface.co/Marre-Barre/smthdssmth

* A model I found on /vt/, not too sure what it is of: https://drive.google.com/file/d/1iR9wVI1wm4M6ZTJgJR_i3TZPAQBDB0Bk/view?usp=share_link

* Anmi: https://drive.google.com/drive/folders/1YFzJKQNVhCRgu0EnkVYgSQ5v63i_LBa4

* Samdoesart (merged model using the original, chewtoy's model, and Chris(orginalcode)'s model): https://huggingface.co/jinofcoolnes/sammod/tree/main

	* Uploader note: all training credit goes to the 3 model maker this merge made from, thank you to them! 

* CopeSeetheMald (samdoesart) (Both were trained with the same dataset. 204 images @ 20.4k steps, 1e-6 learning rate. It's just the base model that differs):

	* berry-based model: https://mega.nz/folder/1a1xkQQK#4atlB1cJqI35InXxlxyA7A

	* blossom-based model: https://mega.nz/folder/ZG0UnRBJ#jykESWBUCr7hjOoNVTXwLw

	* Comparison: https://i.4cdn.org/g/1668068841516679.png

* CopeSeetheMald v2 (10k CHINAI (anything.ckpt)): https://mega.nz/file/xT9jVToK#Sj1S76kl-PC-zCRwJ2FWen6DS0NHY0IXFFAkXhm03eo

	* Ref: https://i.4cdn.org/g/1668113783214478.png

* SOVLFUL original Xbox/PS2/2006 PC era (jaggy92500): https://mega.nz/file/0SER2YpC#_MRc6p_sG9cSWqihpt33jpOWyMR8bCZrUaVkh4z5kGE

	* Sample: https://i.4cdn.org/g/1668129506591557s.jpg

	* Discord: https://discord.com/channels/1038249716149928046/1038283286046322819/1040413218000097280 (from https://discord.gg/Xz8CBFCT)

* Midna (wip): https://mega.nz/folder/E18R2SwC#jHBFsK7zCSuVemOsU4UZ9Q

	* dreambooth midna training config: https://pastebin.com/5EWnMJEz

	* Tagging tool in "Datasets:" section 

* Pepe (word: pepestyle): https://mega.nz/file/NbUShTDR#bZpcYFlv--VqpqUfgDnU95duQlr3wFhRZ4m26WK-Qts 

* Pepe continued: https://huggingface.co/SpiteAnon/Pepestyle

	* https://mega.nz/file/ECchBQRI#u_ySb56NVvANZGY0y6NsS9-ZYSaF1tQCh78OoBuw3IA

* Gigachad: https://huggingface.co/SpiteAnon/gigachad-diffusion

	* https://mega.nz/file/8ecQGJRD#dHe2Ar9e1AN9-wcNrP1qpBjHqk9UtlgO2UtiXlZJHpQ

* y2k (by JF#8026): https://mega.nz/file/hT0mgTqR#d8g133APl30UtDwsNmzV73_ZESi_kTa5pmQgJoxomn0

	* ykgl.ckpt. It does cgi girls from the y2k era. Trained for 40k steps.

	* You call on them with (ykgl cgi_girl), or (ykgl cgi_girls), or just (ykgl girl), and then maybe with , cgi_artstyle.

* dbmai (model by 火柴人之父L): https://rentry.org/3en6a

	* https://drive.google.com/drive/folders/1MUtM5MTXM35fid5TE3tUSKXAqPP7oysz

	* https://tieba.baidu.com/p/8136937175

* Vulcan (from Star Trek): https://huggingface.co/mitchtech/vulcan-diffusion

* DND: https://huggingface.co/0xJustin/Dungeons-and-Diffusion

* Complex Lineart: https://huggingface.co/Conflictx/Complex-Lineart

* More Abmayo (has model and imgs): https://mega.nz/folder/l5NxwTKa#9fA_tn_OZxWm3kHjdA9TPg

* Yuzuki Yukari: https://mega.nz/folder/8hNEiSSC#fYPUNzazZQ04dSizcjmhcg

* Samdoesartv2: https://huggingface.co/kijaw/samdoesarts_v2

	* Ex: https://imgur.com/a/5StuU4G

* Nadanainone (created and trained on their own art, 1076 images (including flipped copies), 10k steps, 1e-6 learning rate): https://huggingface.co/nadanainone/istolemyownart

* Pop n Music: https://huggingface.co/nadanainone/popnm

* Heaven burns red artstyle: https://gofile.io/d/3q5WO3

	* use hbrs as a prompt

	* highly recommand to use 1girl and portrait as those were trained on those the most

* Samus enjoying tentacles + Dataset: https://mega.nz/folder/ls10yJBK#WsnlUfHkcle4FEc_jXS6eA

* CModel: https://huggingface.co/jinofcoolnes/cmodel/tree/main

	* https://www.patreon.com/posts/cmodel-74660500

	* https://twitter.com/Rahmeljackson/status/1592400206733115393

	* Reported to work with NAI hypernets well

* heavy paint style from the same author of dbmai: https://drive.google.com/drive/folders/1ssyBg5Fw8O80_T6nvTrzcnluXEx0YD0I

	* use lastmodel 

	* source: https://tieba.baidu.com/p/8147386385

* Kurzgesagt (another?): https://huggingface.co/questcoast/SD-Kurzgesagt-style-finetune

* Rei and Liduke (not sure if safe): https://rentry.org/eeayv

	* Rei: https://pixeldrain.com/u/Sruc4DDk

	* Liduke: https://pixeldrain.com/u/4T3oBcRy

* Mikasa + Dataset: https://mega.nz/folder/x9FRkAzC#zPs19Nhx7ASZQwauj0PiyA

	* Note: You have to get a bit creative with the prompt since I didn't clean up the tags, you often need to combine a ton of redundant tags to get the effect you want. Example images included along with a list of all tags for experimentation. If you merge the checkpoint with something else the visuals improve dramatically. The artist tags in the list will guide it towards a particular aesthetic.

* Ranma (replicates late '80s early '90s anime, specifically the Ranma 1/2 anime): https://huggingface.co/tashachan28/ranma_diffusion

* VRass (based on Anytthing V3, trained on free VRoid clothing, good for img2img, supports high denoising (0.6-0.8), token: vrass): https://huggingface.co/Abysz/Img2Ass_VRass1.1

	- https://www.reddit.com/r/StableDiffusion/comments/z09inh/img2ass_3d_cloth_generator/  
	Use:

    Export the png of the VRoid asset (or use whatever you want)  
    Place it in img2img. Use the "vrass" token and the style of clothing you want.  
    Experiment!  
    Upscale 4x (Recommended)  
    Import and enjoy!

* Hapu: https://mega.nz/file/xWdTAbzI#TVaq9Fgds2V43IWai09NdoLDSJHx6FMy_14UTWL1HEQ

* AISee (made from 3k artworks from some website, more info in the link): https://huggingface.co/grinman/AIsee

* BTD6 monkeys (not sure if dreambooth): https://huggingface.co/Junglerally/Stable-BTD6

* Kobo (kbknr): https://huggingface.co/cntfcknwrtvwls/kbknr

	* Alternate download: https://mega.nz/folder/jUQ20ZwC#15bhNyCG9SjgQYe5X_E5JA

* Yoji Shinkawa's artwork (47 images, 4k): https://civitai.com/models/1051

* An experimental Dreambooth model trained on individual frames of looping 3D animations that were then laid out on a 4x4 grid. Generates sprite sheets that can create very interesting abstract animations: https://huggingface.co/Avrik/abstract-anim-spritesheets

	- Use the token AbstrAnm spritesheet. Size must be set at 512x512 or your outputs may not work properly

### **Embeddings**

!!! info If an embedding is >80mb, I mislabeled it and it's a hypernetwork

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

You can check .pts here for their training info using a text editor

* Text Tutorial: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Textual-Inversion

	* Make sure to use pictures of your subject in varied areas, it gives more for the AI to work with

* Tutorial 2: https://rentry.org/textard

* Another tutorial: https://imgur.com/a/kXOZeHj

	* https://i.imgur.com/yv3TrrC.jpeg

* Test embeddings: https://huggingface.co/spaces/sd-concepts-library/stable-diffusion-conceptualizer

* Collection: https://huggingface.co/sd-concepts-library

* Collection 2: https://mega.nz/folder/fVhXRLCK#4vRO9xVuME0FGg3N56joMA

* Collection 3: https://cyberes.github.io/stable-diffusion-textual-inversion-models/

* **Korean megacollection:**

	* https://arca.live/b/hypernetworks?category=%EA%B3%B5%EC%9C%A0

		* Link scrape: https://pastebin.com/p0F4k98y

	* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948

	* Original: https://arca.live/b/hypernetworks/60930993

	* **Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw**

* Large Vtuber collection dump (not sure if pickled, even linker anon said to be careful, but a big list anyway): https://rentry.org/EmbedList

* Waifu Diffusion collection: https://gitlab.com/cattoroboto/waifu-diffusion-embeds

* Collection of curated embeds that aren't random junk/test ones from HF's Stable Diffusion Concept library (Updated to Nov 10): https://mega.nz/file/58tRlZDQ#Xbs7kYRC-bot1FIDdkJcz_chJpVrdghrGYMO9POPq9U

	* contains two folders, one for the top liked list and one for the entire library (excluding top liked)

Found on 4chan:

* Embeddings + Artists: https://rentry.org/anime_and_titties (https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A)

* Random embedding I found: https://ufile.io/c3s5xrel

* Embeddings: https://rentry.org/embeddings

* Anon's collection of embeddings: https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A

* Collection: https://gitgud.io/ZeroMun/stable-diffusion-tis/-/tree/master/embedding

* Collection: https://gitgud.io/sn33d/stable-diffusion-embeddings

* Collection from anon's "friend" (might be malicious): https://files.catbox.moe/ilej0r.7z

* Collection from anon: https://files.catbox.moe/22rncc.7z

* Collection: https://gitlab.com/rakurettocorp/stable-diffusion-embeddings/-/tree/main/

* Collection: https://gitlab.com/mwlp/sd 

* Senri Gan: https://files.catbox.moe/8sqmeh.rar

* Collection: https://gitgud.io/viper1/stable-diffusion-embeddings

* Repo for some: https://git.evulid.cc/wasted-raincoat/Textual-Inversion-Embeds/src/branch/master/simonstalenhag

* automatic's secret embedding list: https://gitlab.com/16777216c/stable-diffusion-embeddings

* Collection of /vt/ embeds in 0-Embeds folder: https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ

* Henreader embedding, all 311 imgs on gelbooru, trained on NAI: https://files.catbox.moe/gr3hu7.pt

* Henreader (a different one, made for SD 1.4 or WD 1.2 with a small dataset): https://mega.nz/folder/7k0R2arB#5_u6PYfdn-ZS7sRdoecD2A/folder/Go9CRRoC

* Kantoku (NAI, 12 vectors, WD 1.3): https://files.catbox.moe/j4acm4.pt

* Asanagi (NAI): https://files.catbox.moe/xks8j7.pt

	* Asanagi trained on 135 images augmented to 502 for 150296 steps on NAI Anime Full Pruned with 16 vectors per token with init word as voluptuous

	* training imgs: https://litter.catbox.moe/2flguc.7z

* DEAD LINK Asanagi (another one): https://litter.catbox.moe/g9nbpx.pt

* Imp midna (NAI, 80k steps): mega.nz/folder/QV9lERIY#Z9FXQIbtXXFX5SjGf1Ba1Q

* imp midna 2 (NAI_80K): mega.nz/file/1UkgWRrD#2-DMrwM0Ph3Ebg-M8Ceoam_YUWhlQWsyo1rcBtuKTcU

* inverted nipples: https://anonfiles.com/300areCby8/invertedNipples-13000_zip (reupload)

	* Dead link: https://litter.catbox.moe/wh0tkl.pt

* Takeda Hiromitsu Embedding 130k steps: https://litter.catbox.moe/a2cpai.pt

* Takeda embedding at 120000 steps: https://filebin.net/caggim3ldjvu56vn

* Nenechi (momosuzu nene) embedding: https://mega.nz/folder/E0lmSCrb#Eaf3wr4ZdhI2oettRW4jtQ

* Touhou Fumo embedding (57 epochs): https://birchlabs.co.uk/share/textual-inversion/fumo.cpu.pt

	* https://twitter.com/Birchlabs/status/1579937213617680385

* Abigail from Great Pretender (24k steps): https://workupload.com/file/z6dQQC8hWzr 

* Naoki Ikushima (40k steps): https://files.catbox.moe/u88qu5.pt

* Abmayo: https://files.catbox.moe/rzep6d.pt

* Gigachad: https://easyupload.io/nlha2m

* Kusada Souta (95k steps): https://files.catbox.moe/k78y65.pt

* Yohan1754: https://files.catbox.moe/3vkg2o.pt

* Niro: https://take-me-to.space/WKRY9IE.pt

* Kaneko Kazuma (Kazuma Kaneko): https://litter.catbox.moe/6glsh1.pt

* Senran Kagura (850 CGs, deepdanbooru tags, 0.005 learning rate, 768x768, 3000 iterations): https://files.catbox.moe/jwiy8u.zip

* Abmayo (miku) (14.7k): https://www.mediafire.com/folder/trxo3wot10j41/abmono

	* https://www.mediafire.com/file/id2uh4gkzvavsbc/abmono-14700.pt/file

	* https://mega.nz/file/u11GTAKK#QKG2uIYd9ccDggC_2YzprsqWvqTVwvYgvbYQ19ouq9M

* Aroma Sensei (86k, "aroma"): https://files.catbox.moe/wlylr6.pt

* Zun (75:25 weighted sum NAI full:WD): https://www.fluffyboys.moe/sd/zunstyle.pt

* Kurisu Mario (20k): https://files.catbox.moe/r7puqx.pt

	* creator anon: "I suggest using him for the first 40% of steps so that the AI draws the body in his style, but it's up to you. Also, put speech_bubble in the negative prompt, since the training data had them"

* ATDAN (33k): https://files.catbox.moe/8qoag3.pt

	* Mirror: https://litter.catbox.moe/6valfk.pt

* Valorant (25k): https://files.catbox.moe/n7i9lq.pt

	* Mirror: https://files.catbox.moe/n7i9lq.pt

* Takifumi (40k, 153 imgs, NAI): https://freeufopictures.com/ai/embeddings/takafumi/

	* for competition swimsuit lovers

* 40hara (228 imgs, 70k, 421 after processing): https://freeufopictures.com/ai/embeddings/40hara/

* Tsurai (160k, NAI): https://mega.nz/file/bBYjjRoY#88o-WcBXOidEwp-QperGzEr1qb8J2UFLHbAAY7bkg4I

* jtveemo (150k): https://a.pomf.cat/kqeogh.pt

	* Creator anon: "I didn't crop out any of the @jtveemo stuff so put twitter username in the negatives."

	* 150k steps, 0.005 LR, art from exhentai collection and processed with mirror and autocrop, deepdanbooru

* Nahida (Genshin Impact): https://files.catbox.moe/nwqx5b.zip

* Arcane (SD 1.4): https://files.catbox.moe/z49k24.pt

	* People say this triggered the pickle warning, so it might be pickled.

* Gothica: https://litter.catbox.moe/yzp91q.pt

* Mordred: https://a.pomf.cat/ytyrvk.pt

* 100k steps tenako (mugu77): https://www.mediafire.com/file/1afk5fm4f33uqoa/tenako-mugu77-100000.pt/file

* erere-26k (fuckass(?)): https://litter.catbox.moe/cxmll4.pt

* Great Mosu (44k): https://files.catbox.moe/6hca0u.pt

* no idea what this embedding is, apparently it's an artist?: https://files.catbox.moe/2733ce.pt

* Dohna Dohna, Rance remakes (305 images (all VN-style full-body standing character CGs). 12000 steps): https://files.catbox.moe/gv9col.pt

	* trained only on dohna dohna's VN sprites

	* Onono imoko

* Raita: https://files.catbox.moe/mhrvmk.pt

* Senri Gan: https://files.catbox.moe/8sqmeh.rar

	* 2 hypernetworks and 5 TI

	* Anon: "For the best results I think using hyper + TI is the way. I'm using TI-6000 and Hyper-8000. It was trained on CLIP 1 Vae off with those rates 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000."

* om_(n2007): https://files.catbox.moe/gntkmf.zip

	* https://files.catbox.moe/x0aueo.pt

* Kenkou Cross: https://mega.nz/folder/ZYAx3ITR#pxjhWOEw0IF-hZjNA8SWoQ

* Baffu (~47500 steps): https://files.catbox.moe/l8hrip.pt

	* Biased toward brown-haired OC girl (Hitoyo)

* Danganronpa: https://files.catbox.moe/3qh6jb.pt

* Hifumi Takimoto: https://files.catbox.moe/wiucep.png 

	* 18500 steps, prompt tag is takimoto_hifumi. Trained on NAI + Trinart2 80/20, but works fine using just NAI

* Power (WIP): https://files.catbox.moe/bzdnzw.7z

* shiki_(psychedelic_g2): https://files.catbox.moe/smeilx.rar

	* https://files.catbox.moe/btxd4r.rar

* Akari: https://files.catbox.moe/b7jdng.pt

* Embeddings using the old version of TI

	* jtveemo: https://www.mediafire.com/file/re9q1l1xwgriscm/jtveemo-style.bin/file

	* kenshin187: https://www.mediafire.com/file/fap4yuiyvqt7dkl/kenshin187.bin/file

* Takeda Hiromitsu reupload: https://www.mediafire.com/file/ljemvmmtz0dqy0y/takeda_hiromitsu.pt/file

* Takeda Hiromitsu (another reupload): https://a.pomf.cat/eabxqt.pt

* Pochi: https://files.catbox.moe/7vegvg.rar

	* Author's notes: Smut version was trained on a lot of doujins and it looks more like her old style from the start of smut version of Ane doujin (compare to chapter 1 and you can see that it worked). 200k version is looking a bit more like her recent style but I can see it isn't going to work the way I hoped. 

	* By accident I started with 70 pics where half of them were doujins to give reference for smut. Complete data is 200 with again those same 35 doujins for smut. I realized that I used half smut instead of full set so I went back to around 40k steps and then gave it complete 200 picture set hoping it would course correct since non smut is more recent art style. Now it looks like it didn't course correct and will never do that. On the other hand recent iterations are less horny.

* Power (Chainsaw Man): https://files.catbox.moe/c1rf8w.pt

* ooyari:

	* 70k (last training): https://litter.catbox.moe/gndvee.pt

	* 20k (last stable loss trend): https://litter.catbox.moe/i7nh3x.pt

	* 60k (lowest loss rate state in trending graph): https://litter.catbox.moe/8wot9a.pt

* Kunaboto (195 images. 16 vectors per token, default learning rate of 0.005): https://files.catbox.moe/uk964z.pt

* Erika (Shadowverse): https://files.catbox.moe/y9cgr0.pt

* Luna (Shadowverse): https://files.catbox.moe/zwq5jz.pt

* Fujisaka Lyric: https://files.catbox.moe/8j6ith.pt

* Hitoyo (maybe WIP?): https://files.catbox.moe/srg90p.pt

* Hitoyo (58k): https://files.catbox.moe/btjsfg.pt

* kunaboto v2 (Same dataset, just a different training rate of 0.005:25000,0.0005:75000,0.00005:-1, 70k): https://files.catbox.moe/v9j3bz.pt

* Hitoyo (another, final vers?) (100k steps, bonnie-esque): https://files.catbox.moe/l9j1f4.pt

* Fatamoru: https://litter.catbox.moe/pn9xep.pt

	* Dead link: https://litter.catbox.moe/xd2ht9.pt

* Zip of Fatamoru, Morgana, and Kaneko Kazuma: https://litter.catbox.moe/9bf77l.zip

* Tekuho (NAI model, Clip Skip 2, VAE unloaded, Learning rate 0.002:2000, 0.0005:5000, 0.0001:9000): https://mega.nz/folder/VB5XyByY#HLvKyIJ6U5nMXx6i3M__VQ

	* manually cropped about 150 images, making sure that all of them have a full body shot, a shot from torso and up, and if applicable a closeup on the face

	* Images not from Danbooru

	* Best results around 4000 steps

* Reine: https://litter.catbox.moe/saav38.zip

* Embed of a girl anon liked (2500 steps, keyword "jma"): https://files.catbox.moe/1qlhjf.pt 

* Carpet Crawler: https://anonfiles.com/i3a2o0E5y0/carpetcrawlerv2-12500_pt

	* Embedding trained on nai-final-pruned at 8 vectors up to 20k steps. Turned into ugly overtrained garbage over 125000 steps so this is the one I'm releasing. Not good for much other than eldritch abominations.

	* https://www.deviantart.com/carpet-crawler/gallery

	* recommend using it in combination with other horror artist embeddings for best results.

* nora higuma (Fuckass, 0.0038, 24k, 1000+ dataset, might be pickle): https://litter.catbox.moe/tkj61z.pt

	* dead link: https://litter.catbox.moe/25n10h.pt

* mdf an (Bitchass train: 0.0038, steps: 48k, loss rate trend: 0.095, dataset: 500+, issue: nsfw majority, will darken sfw images): https://litter.catbox.moe/lxsnyi.pt

	* dead link: https://litter.catbox.moe/4liook.p

* subachi (shitass, train: 0.0038, steps: 48k, loss rate trend: 0.118, dataset: 500+, issue: due to artist's style, it's on sigma male mode; *respecting woman is not an option with this embedding*): https://litter.catbox.moe/6nykny.pt

	* dead link: https://litter.catbox.moe/idskrg.pt

* irys: https://files.catbox.moe/1iwmv1.pt

* DEAD LINK Omaru-polka: https://litter.catbox.moe/qfchu1.pt

* Embed for "veemo" (?), used to make this picture (https://s1.alice.al/vt/image/1665/54/1665544747543.png): https://files.catbox.moe/18bgla.pt

* Lui: https://files.catbox.moe/m54t0p.pt

* Reine:

	* 39,5k steps, pretty high vectors per token: https://files.catbox.moe/s2s5qg.pt

	* smaller clip skip and less steps, trained it to 13k: https://files.catbox.moe/nq126i.pt

* Big reine collection: https://files.catbox.moe/xe139m.zip

* Ilulu (64k steps with a learning rate of 0.001): https://files.catbox.moe/8acmvo.pt

* random embed from furry thread (6500 steps, 10 vectors, 1 placeholder_string, init_word "girl" these four images used): https://files.catbox.moe/4qiy0k.pt

* Cookie (from furry thread, apprently good with inpainting): https://files.catbox.moe/9iq7hh.pt

	* https://mega.nz/file/IABX1QKS#8vsSqlUm-o6QNB2gjSQeJzED1dtKOZVWdE8-By0INlI

* Cutie (cyclops, from furry thread, 8k steps): https://files.catbox.moe/aqs3x3.pt

	* 4.5k: https://files.catbox.moe/mcwxag.pt

* Felino's artstyle (from furry thread, 7 images): https://files.catbox.moe/vp21w4.pt

* Yakov (from mlp thread): https://i.4cdn.org/mlp/1666224881260593.png

* Rebecca (by booru anon, info is in link): https://huggingface.co/demibit/rebecca

* eastern artists combinination: https://mega.nz/file/SlQVmRxR#nLBxMj7_Zstv4XqfuEcF-pgza3T1NPlejCm1KGBbw70

* Elana (Shadowverse): https://files.catbox.moe/vbpo7m.pt

	* Info by anon: I just grab all the good images I can find, tag with BLIP and Deepdanbooru in the preprocessing, and pick a number of vectors based on how many images I have (16 here since not a lot). Other than that, I trained 6500 steps at 1 batch size under the schedule:

		0.02:200, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.00005

* Lina: https://files.catbox.moe/jnfo98.pt

* Power (60k): https://files.catbox.moe/72dfvc.pt

* Takeda, Mogudan Fourchanbal (?, from KR site): https://files.catbox.moe/430rus.pt

* Mikan (30 tokens, 36 images (before flipping/splitting), 5700steps, 5e-02:2000, 5e-03:4000): https://files.catbox.moe/xwdohx.pt

	* creator: I've been getting best results with these tags: (orange hair and (hair tubes:1.2), (dog ears and dog tail and (huge ahoge:1.2):1.2)), green eyes

	* apparently it's not very effective. a hypernetwork is WIP

* Fuurin Rei (6000, 5.5k most): https://files.catbox.moe/s19ub3.7z

* Mutsuki (Blue Archive) embedding (10k step,150 image, no clip skip [set the "stop at last layers of clip model" option at 1 to get good results], 0.02:300, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.0005, vae disabled by renaming): https://files.catbox.moe/6yklfl.pt

* Reine: https://files.catbox.moe/tv1zf4.pt

* as109 (trained with 1000+ dataset, 0.003 learning rate, 0.12 loss rate trend, 25k step snapshot): https://litter.catbox.moe/5iwbi5.pt

* sasamori tomoe (0.92 loss trend, 60k+ steps, 0.003 learning rate. 500+ dataset, pruned pre 2015 images. biased to doujin, weak to certain positions (mostly side)): https://litter.catbox.moe/mybrvu.pt

* egami(500+ dataset, 0.03 learning rate, 0.13 loss trend, 40k steps): https://litter.catbox.moe/dpqp1k.pt

* pink doragon (20k+ steps, 0.0031 learning rate, 0.113 loss trend, 800+ dataset): https://litter.catbox.moe/mml9b9.pt

	* kind of failure: fancy recent artworks are ignored due to dataset bias - will train with 2018+ data.

	* leaning to BIG ASS and BIG TIDDIES.

* Kiwi (by booru anon): https://huggingface.co/demibit/kiwi

* Labiata (8 vectors/token): https://files.catbox.moe/0kri2d.pt

* Akari (another, one I missed): https://files.catbox.moe/dghjhh.pt

* Arona from Blue Archive (I'm pretty sure): https://files.catbox.moe/4cp6rl.pt

* Emma (arcane, 50 vector embedding trained on ~250 pics for ~13500 steps): https://files.catbox.moe/2cd7s3.pt

* blade4649 embedding (10k steps, 352 images,16 vectors,learning rate at 0.005): https://files.catbox.moe/5evrpn.pt

* fechtbuch of Mair: https://files.catbox.moe/vcisig.pt

* Longsword (mainly for img2img): https://files.catbox.moe/r442ma.pt 

* Le Malin (listless Lapin skin, 10k steps with 712 inputs): https://files.catbox.moe/3rhbvq.pt

* minakata hizuru (summertime girl): https://files.catbox.moe/9igh8t.pt

* Roon (Azur Lane) (NAI model, 10k steps but with 83 different inputs): https://files.catbox.moe/9b77mp.pt

* arcane-32500: https://files.catbox.moe/nxe9qr.pt

* mashu003 (https://mashu003.tumblr.com/) (all danbooru images used as dataset): https://files.catbox.moe/kk7v9w.pt

* Takimoto Hifumi (18500 steps, prompt tag is takimoto_hifumi. Trained on NAI + Trinart2 80/20, but works fine using just NAI): https://files.catbox.moe/wiucep.png

* momosuzu nene: https://mega.nz/folder/s8UXSJoZ#2Beh1O4aroLaRbjx2YuAPg

* Harada Takehito (disgaea artist) (78k steps with 150 images): https://files.catbox.moe/e2iatm.pt

* Mda (1700 images and trained for 20k): https://files.catbox.moe/tz37dj.pt

* Polka (NAI, 16 vectors, 5500 steps): https://files.catbox.moe/pmzyhi.png

* Enna: https://files.catbox.moe/7edtp0.pt

* Ghislaine Dedoldia ("dark-skinned female" init word, 12 vectors per token, 0.02:200, 0.01:1000, 0.005:2000, 0.002:3000, 0.0005:4000, 0.00005 LR, 10k steps 75 image crop data set) https://mega.nz/folder/JPVSVLbQ#SqGZb7OVKe_UNRvI0R8U8A

	* Notes by uploader: Here is a terrible Ghislaine Dedoldia embedding I made while testing sd-tagging-helper and the new webui dataset tag editor extension. She has no tail because the crops were shit and I only trained on crops made using the helper. Sometimes the eye patch is on the wrong side because of two images where it was on the wrong eye. Stomach scar is sometimes there sort of but probably needed more time in the oven. She doesn't have dark skin because the AI is racist and probably because it was only tagged on half the images.

	* Uploader: Use "dark-skinned female" in your prompt or she will be pale

* Mizuryu-Kei (Mizuryu Kei): https://files.catbox.moe/bcy7vx.pt

* kidmo: https://litter.catbox.moe/44e28e.pt

	* dataset:kidmo

	* dataset:no filter

	* 10 tokens

	* 26k steps

	* 0.129 loss trend

	* 90-ish dataset

	* 0.0028 learning rate

	* issue: generic as shit, irradiated with kpop, potato gaming (you'll know when you try to use this shit with i2i)

* asanugget-16: https://litter.catbox.moe/9r0ixj.pt

	* dataset: asanagi

	* dataset: no pre-2010 artworks

	* 16 tokens

	* 22k steps

	* 0.114 loss trend

	* 500+ dataset (w/ auto focalpoint)

	* 0.0028 learning rate

* Ohisashimono (20k to 144k): https://www.mediafire.com/folder/eslki3wzlmesj/ohi

* Shadman: https://files.catbox.moe/fhwn7m.png

* ratatatat74: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

	* Uploader: Because the source images were prominently lewd in some shape or form, it really likes to give half-naked people.

	* In combination with Puuzaki Puuna, it certainly brings out some interesting humanoid Nanachis.

* WLOP: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA/folder/KWJUSR7T

	* This embedding has 24 vectors, has been trained by a rate of 0.00005 and was completed at the steps of around 35000.

	* The embedding was trained on NovelAI (final-pruned.ckpt).

	* Uploader's Note: This embedding has a HUGE problem in keeping the signature out - feel free to crop out the signature if you wish to redo the embedding. If you do find a way to remove it without recreating the whole embedding - feel free to post it in 4chan/g/ and I may stumble upon it.

	* Note 2: Use inpainting on the face in img2img to create some beautiful faces if they come out distorted initially.

* Asutora style embedding (mainly reflected in coloring and shading, since his faces are very inconsistent): https://mega.nz/folder/nZoECZyI#vkuZJoQyBZN8p66n4DP62A 

	* uploader: satisfactory results over 20k steps

	* Comparisons: https://i.4cdn.org/g/1667701438177228.jpg

* y'shtola: https://files.catbox.moe/5hefsb.pt

	* Uploader: You may need to use square brackets to lower it's impact. Also it likes making cencored pics unless you add penis to the input prompt

* Selentoxx (nai, 16v, 10k): https://files.catbox.moe/0j7ugy.png

* Aki (Goodboy, nai, 16v, 10k): https://files.catbox.moe/1p14ra.png

* Sana (nai, 15v): 

	* 10k: https://files.catbox.moe/g112gm.png

	* 100k: https://files.catbox.moe/3ndubu.png

	* In case these aren't good, use:

	* 10k: https://files.catbox.moe/r5ciho.pt

	* 25k: https://files.catbox.moe/e6aurx.pt

	* 50k: https://files.catbox.moe/lz016k.pt

	* 75k: https://files.catbox.moe/jhdjc9.pt

	* 100k: https://files.catbox.moe/2lvv2z.pt

	* Uploader note: don't use more than 0.8 weighting or else it gets deep fried

* delutaya: https://files.catbox.moe/r6pylz.pt

* Delutaya (another unrelated, 16v, 10k, nai): https://files.catbox.moe/kv2hdd.png

* mano-aloe-v1q (nai, manoaloe,mano aloe): https://files.catbox.moe/0i5qfl.pt

* Fauna (16v, 10k, nai): https://files.catbox.moe/zizgrw.png

* wawa (15v, 10k, nai): https://files.catbox.moe/2vpyi2.png

* Wagashi: https://mega.nz/file/exM21aTT#eawWbqsmajzs-TUCWfrVHvsG2HBEZ3HcYR5cy1AxFPw

* Deadflow: https://mega.nz/file/y41WHIgC#pXtCly7bzjDNJ7RZl7685_Nj1LTliIif_f_1BWMhHSE

* Elira (16v, 3k, nai sfw): https://litter.catbox.moe/4ylbez.png

* Rratatat (NAI, 16v, 10k): https://files.catbox.moe/nrekhk.png

	* Uploader: Works better with "red hair, multicolored hair, twintails"

* WLOP (reupload, retrained WITHOUT signatures - 24 vectors, 0.00005 learning rate, around 19000 steps: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

* ratatatat74 (reupload, retrained WITHOUT VAE - 24 vectors, 0.00005 learning rate, 13500 steps): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

* Wiwa embed steps pre deep frying: https://files.catbox.moe/6lu6od.zip

* Nilou (by anon, not sure if safe or of any training info, NOTE TO MYSELF SEARCH FOR THIS EMBED's DISCORD): https://cdn.discordapp.com/attachments/1019446913268973689/1039909937884713070/nilou.pt

	* https://pastebin.com/AJAuVqCi

* Makima (500s, 4v, NAI): https://i.4cdn.org/h/1668023713496532.png

* Fauna (updated, NAI, 8v, 10k): https://files.catbox.moe/dmu00i.png

* New rrat (8v, 10k, NAI): https://files.catbox.moe/fyqxjf.png

* Weine (8v, 10k, nai): https://files.catbox.moe/b9cn4z.png

* Moona (10k, 8v, nai): https://files.catbox.moe/tuh4nj.png

	* Comparison with Moona 2: https://i.4cdn.org/vt/1668038525258037s.jpg

* Aki (another, Goodboy, nai, 8v, 10k, nai): https://files.catbox.moe/k2cgxj.png

* Delu (another, notaloe, 8v, 10k, nai): https://files.catbox.moe/cvykdm.png

* Moona 2 (another anon, nai, moonmoon, nai, 8v, 10k): https://files.catbox.moe/yh8ora.png

	* Comparison with the Moona 4 links up: https://i.4cdn.org/vt/1668038525258037s.jpg

* Kobogaki (nai, 8v, 10k): https://files.catbox.moe/0r3a8o.png

* Yopi (nai, 8v, 10k): https://files.catbox.moe/hoh865.png

* FreeStyle/Yohan TI by andite#8484 (trained on ALL of his artwork, not only skin): https://cdn.discordapp.com/attachments/1019446913268973689/1038423463314075658/yohanstyle.pt

	* https://twitter.com/yohan1754?lang=en

* Matchach TI by methane#3131: https://cdn.discordapp.com/attachments/1019446913268973689/1040271410217635920/matcha-20000.pt

	* Might need to add cat ears to negative prompt because for some reason it appears

* Elira (8v, 10k, nai): https://files.catbox.moe/ldeg3v.png

	* Linked comparison (Elira default-5500 16v 5500 steps, Wiwa 4v 10000 steps, Elira t8 8v 10000 steps): https://i.4cdn.org/vt/1668135849025419s.jpg

* Reine (35v, 39500s, nai90sd10): https://files.catbox.moe/m0he7i.png

* Kobo (kbknr, 10k, 16v, NAI): https://files.catbox.moe/kphjec.png

* Kaela (Kovalski) (NAI, 4500k, 8v): https://files.catbox.moe/nxp368.png

	* Uploader: Try, eyewear on head, blonde hair, red eyes, fur trim, jacket, white dress, red ribbon behind hair,

	* Dataset?: https://files.catbox.moe/sqci4d.PNG

* Luna (LunaHime, NAI, 8v, 10k): https://files.catbox.moe/45fe4m.png

	* needs heterochromia to force the two eye colors 

* Zeta (Zetanism, 8v, 10k, nai): https://files.catbox.moe/z1u5py.png

* Aki (Goodboy) (NAI, 8v, 10k): https://litter.catbox.moe/vfd9fw.png

* Kobo (KoboGaki) (NAI, 8v, 10k): https://litter.catbox.moe/7hssgl.png

* Delu(?) (NotAloe) (NAI, 8v, 10k): https://litter.catbox.moe/9gdr5t.png

* Yopi (NAI, 8v, 10k): https://litter.catbox.moe/bhd01v.png

* AChan (NAI, 8v, 10k): https://i.4cdn.org/vt/1668274461405432.png

	* https://litter.catbox.moe/k5sifc.png

* Wiwa's alt hair (Elira, NAI, 8v, 10k): https://files.catbox.moe/vxz1yo.png

* miata8674 (45k training steps (4 Colab rounds)): https://mega.nz/folder/nZoECZyI#vkuZJoQyBZN8p66n4DP62A

	* Focuses on faces, the defining features of the style are general sketchiness and the eyes. Strengthened by the mention of eyelashes and eyeshadow

* Asagi Igawa, Edjit, and Rouge the Bat (RealYiffingFar#4510): https://mega.nz/folder/5nIAnJaA#YMClwO8r7tR1zdJJeTfegA

	* Has training info and a tutorial

* NIXEU: https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

	* By uploader: 24 vectors, 0.00005 training rate, around 16500 steps and 48 reference images with NovelAI (final-prune.ckpt)

	* From the testings that I have done, it is able to replicate the artstyle quite well with one exception - the primary problem being the eyes - they seem to be slightly overbaked. My suggestion is to use img2img to circumvent that problem.

	* Regardless: I recommend a CFG of around 8.5 and prompts such as 'soft lighting' which would underline the style. Requires a bit of fine tuning regarding prompts seeing that it is rather delicate to the touch,

* frank franzetta: https://huggingface.co/sd-concepts-library/frank-frazetta

* meme50 (WIP, 0.004 LR, 20k): https://litter.catbox.moe/e9v33j.pt

	* https://litter.catbox.moe/a31cuf.pt

* Anya (probably a reupload from a collection, v8, 8500s, NAI): https://files.catbox.moe/b8ghxx.png

* Amelia Watson (amedoko, 8v, 10k, NAI): https://files.catbox.moe/qc3qt2.png

	* Produces yellow eyes, prompt for blue eyes

* Kiara (kiarer, 10k, 5v, NAI): https://files.catbox.moe/87hdj3.png

	* op: tried to get a nice spread of quality images from different outfits and artists. It probably won't get any of her outfits right, but the girl in the output is very clearly a wawa

* NecoArc: https://mega.nz/folder/ToFEARJa#yvSV_Cb5c6KxjM3wXR2_ZA

	* Another anon uploaded a mirror (not sure if safe): https://gofile.io/d/fvz1Tl

* Trixie Lulamoon (100k, 16v, anything 3.0 pruned fp16): https://files.catbox.moe/8ek5o0.png

	* For blue/purple witches

	* The embedding associated the right blue tone with "aqua", as well as the correct purple tone with "purple". It tends to add long eyelashes and eyeshadow, but those can be enhanced with prompts.

	* The correct hairstyle comes from "hair over shoulder" and "asymmetrical hair", but "asymmetrical bangs" helps achieve it.

	* It dislikes clothes and will try to cheat them right off your prompts.

	* As far as I can tell it works decently well on any Nai-based model and at varying Clip Skip levels, but it was trained on Anything v3 with Clip Skip on 1. Going over 1.2 weight on clip skip 1 looks weird sometimes

	* Reupload by anon (not sure if safe): anonfiles.com/1ev4m8Hey1/trixie_lulamoon_pt

* Not sure what this is: https://files.catbox.moe/9l2nrw.pt

	* Ex pic: https://i.4cdn.org/h/1668550663647424s.jpg

* Blannie from Bleague of Blegends (Annie from LOL, 18 tokens large(?)): https://files.catbox.moe/un85e4.pt

	* Ex pic with skin: https://i.4cdn.org/h/1668567424263709s.jpg

* Nahida v2: https://cdn.discordapp.com/attachments/1019446913268973689/1031321278713446540/nahida_v2.zip

	* Nahida (50k, very experimental, not enough images): https://files.catbox.moe/2794ea.pt

* look at the 2nd and 3rd images: https://www.reddit.com/gallery/y4tmzo

* Negative embedding to be used in the negatives (supposedly a quality enhancer, supposedly fixes hands): https://huggingface.co/datasets/Nerfgun3/bad_prompt

	* https://old.reddit.com/r/StableDiffusion/comments/yy2i5a/i_created_a_negative_embedding_textual_inversion/

* Elysia (Honkai Impact): https://mega.nz/file/qnxiDQxR#3g7_gI-8OD83gPEWu-XjcPCedHCsvbjnxzjxW4c8GAo

	* https://www.pixiv.net/en/artworks/102931348

* Koyori (Koyoyo, NAI, 8v, 10k): https://files.catbox.moe/empi4b.png

	* Might need to prompt for the ears and midriff

* Kronii (10k, 8v, NAI): https://files.catbox.moe/vltkov.png

* Choco (ChocoSen, NAI, 8v, 10k): https://files.catbox.moe/1jf119.png

* Calli (Yaboy, NAI, v8, 10k) (https://s1.alice.al/vt/image/1668/53/1668537070785.jpg): https://files.catbox.moe/ilcpnn.png

	* Might need to prompt pink hair

* Ina (Hololive, tag: ina-nai-100, https://s1.alice.al/vt/image/1668/66/1668666743766.jpg): https://files.catbox.moe/lsaydm.pt

* Omega Alpha (NAI, 8v, 10k): https://files.catbox.moe/19tun3.png

* Elira (old): https://files.catbox.moe/6lu6od.zip

* Elira alt (NAI, v8, 10k): https://mega.nz/folder/23oAxTLD#vNH9tPQkiP1KCp72d2qINQ/file/jvJwzDhB

* Pomu (ImPomu, NAI, v8, 10k, https://s1.alice.al/vt/image/1668/69/1668692914583.jpg): https://files.catbox.moe/9zdw2f.png

	* Dead: https://litter.catbox.moe/qp32ku.png

	* Try: Blonde hair, fairy wings

	* Might be a good idea to exclude ocean? Dont ask, literally 1 image in dataset out of like 40 I dont understand why. 

* Feesh (NAI, v8, 10k, https://s1.alice.al/vt/image/1668/70/1668703156236.jpg): https://files.catbox.moe/3v7yhj.png

* Suisei (no training info, https://i.4cdn.org/vt/1668897948153665.png): https://files.catbox.moe/9z6ni5.pt

* Rosemi (RosemiSama, NAI, v8, 10k, https://i.4cdn.org/vt/1668897966152847.jpg): https://files.catbox.moe/2oj2qd.png

	* Might be tough to remove her thornyness.

* SelenToxx (NAI, v8, 10k, https://i.4cdn.org/vt/1668897792400569.png): https://files.catbox.moe/obxl01.png

	* Just beware of ember. I need to remove any trace of him from the dataset.

* Anya (from Anya-Petra thread, https://i.4cdn.org/vt/1668969732782744.png): https://files.catbox.moe/h3t0du.pt

* Reiumuwu (NAI, v8, 10k, https://i.4cdn.org/vt/1669075492548084.jpg): https://files.catbox.moe/woxu4q.png

* NinaMommy (NAI, v8, 10k): https://files.catbox.moe/875g3s.png

* Enna (EnnaBird, NAI, v8, 10k, https://i.4cdn.org/vt/1669164314343707.jpg): https://files.catbox.moe/dkwu0d.png

* Ethyria (MillieMilk, NAI, 8v, 7.5k, https://i.4cdn.org/vt/1669158802233887.jpg): https://files.catbox.moe/57vpza.png

* rd_rn99/roadie3 (no training info: https://mega.nz/file/gY80FTrC#BwV_FS1EqmVcvw6SkiOHFuiE3NpyF66gdJAyDMLN4bU

	- Artist's twitter: https://twitter.com/RD_RN00

* pwcsponson (133 images, 12k steps, ~0.11 loss, default settings)

	- https://files.catbox.moe/85e2k6.zip
	- Apparently generates strange things
	- "It's a pwcsponson model that I intended to use to create his characteristic breasts and genitals and unless I rein it in heavily in the prompt everything is made of uncut dicks, even the buildings"

* Bad artist (negative embedding): https://huggingface.co/nick-x-hacker/bad-artist

	- Reddit with info: https://www.reddit.com/r/StableDiffusion/comments/zk8y50/badartist_negative_embedding/

### **Hypernetworks:**

!!! info If a hypernetwork is <80mb, I mislabeled it and it's an embedding

!!! info Use a download manager to download these. It saves a lot of time + good download managers will tell you if you have already downloaded one

!!! All files in this section (ckpt, vae, pt, hypernetwork, embedding, etc) can be malicious: https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle. Make sure to check them for pickles using a tool like https://github.com/zxix/stable-diffusion-pickle-scanner or https://github.com/lopho/pickle_inspector

* anon: "Requires extremely low learning rate, 0.000005 or 0.0000005"  
**Good Rentry: https://rentry.co/naihypernetworks**  
Hypernetwork Dump: https://gitgud.io/necoma/sd-database  
Collection: https://gitlab.com/mwlp/sd  
Another collection: https://www.mediafire.com/folder/bu42ajptjgrsj/hn  
Senri Gan: https://files.catbox.moe/8sqmeh.rar  
Big dumpy of a lot of hypernets (has slime too): https://mega.nz/folder/kPdBkT5a#5iOXPnrSfVNU7F2puaOx0w  
Collection of asanuggy + maybe some more: https://mega.nz/folder/Uf1jFTiT#TZe4d41knlvkO1yg4MYL2A  
Collection: https://mega.nz/folder/fVhXRLCK#4vRO9xVuME0FGg3N56joMA  
**Mogubro + constant updates: https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ**

* **Korean megacollection:**

	* https://arca.live/b/hypernetworks?category=%EA%B3%B5%EC%9C%A0

		* Link scrape: https://pastebin.com/p0F4k98y

	* (includes mega compilation of artists): https://arca.live/b/hypernetworks/60940948

	* Original: https://arca.live/b/hypernetworks/60930993

	* **Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw**

**Chinese telegram (uploaded by telegram anon): magnet:?xt=urn:btih:8cea1f404acfa11b5996d1f1a4af9e3ef2946be0&dn=ChatExport%5F2022-10-30&tr=udp%3A%2F%2Ftracker.opentrackr.org%3A1337%2Fannounce**

> I've made a full export of the Chinese Telegram channel.
> 
> It's 37 GB (~160 hypernetworks and a bunch of full models).  
> If you don't want all that, I would recommend downloading everything but the 'files' folder first (like 26 MB), then opening the html file to decide what you want.

* Dead link: https://t.me/+H4EGgSS-WH8wYzBl

* Big collection: https://drive.google.com/drive/folders/1-itk7b_UTrxVdWJcp6D0h4ak6kFDKsce?usp=sharing

* https://arca.live/b/aiart/60927159?p=1

* https://arca.live/b/hypernetworks/60927228?category=%EA%B3%B5%EC%9C%A0&p=2

* NAIHypernetwork collection: https://rentry.org/naihypernetworks

Found on 4chan:

* bigrbear: https://files.catbox.moe/wbt30i.pt

* Senran Kagura v3 (850 images, 0.000005 learn rate, 20000 steps, 768x768): https://files.catbox.moe/m6jynp.pt

	* CGs from the Senran Kagura mobile game (NAI model): https://files.catbox.moe/vyjmgw.pt

		* Ran for 19,000 steps with a learning rate of 0.0000005. Source images were 768x576. It seems to only reproduce the art style well if you specify senran kagura, illustration, game cg, in your prompt.

	* Old version (19k steps, learning rate of 0.0000005. Source images were 768x576. NAI model. 850 CGs): https://files.catbox.moe/di476p.pt

	* Senran Kagura again (850, deepdanbooru, 0.000006, 768x576, 7k steps): https://files.catbox.moe/f40el4.pt

* Danganronpa: https://files.catbox.moe/9o5w64.pt

	* Trained on 100 images, up to 12k with 0.000025 rate, then up to 18.5k with 0.000005

	* Also seed 448840911 seems to be great quality for char showcase with just name + base NAI prompts.

* Alexi-trained hypernetwork (22000 steps): https://files.catbox.moe/ukzwlp.pt

	* Reupload by anon: https://files.catbox.moe/slbk3m.pt

	* works best with oppai loli tag

	* https://files.catbox.moe/xgozyz.zip

* Etrian Odyssey Shading hypernetwork (20k steps, WIP, WD 1.3)

* colored drawings by Hass Chagaev (6k steps, NAI): https://files.catbox.moe/3jh1kk.pt

* Morgana: https://litter.catbox.moe/3holmx.pt

* EOa2Nai: https://files.catbox.moe/ex7yow.7z

* EO (WD 1.3): https://files.catbox.moe/h5phfo.7z

* Taran Jobu (oppai loli, WIP, apparently it's kobu not jobu)

	* https://files.catbox.moe/72wjlt.pt

* Higurashi (NAI:SD 50:50): https://litter.catbox.moe/lfg6ik.pt 

	* by op anon: "1girl, [your tags here], looking at viewer, solo, art by higurashi", cfg 7, steps about 40"

* Tatata (15 imgs, 10k steps): https://files.catbox.moe/7hp2es.pt

* Zankuro (0.75 NAI:WD, 51 imgs, 25k+ steps): https://files.catbox.moe/tlurbe.pt

	* Training info + hypernetwork: https://files.catbox.moe/4do43z.zip 

* Test Hypernetwork (350 imgs where half are flipped, danooru tags, 0.00001 learning rate for 3000 steps, 0.000004 until step 7500): https://files.catbox.moe/coux0u.pt

* Kyokucho (40k steps, good at 10-15k, NAI:WD1.2): https://workupload.com/file/TFRuGpdGZZn

* Final Ixy (more detail in discord section): https://mega.nz/folder/yspgEBhQ#GLo7mBc1EH7RK7tQbtC68A

	* Old Ixy (more data, more increments): https://mega.nz/file/z8AyDYSS#zbZFo9YLeJHd8tWcvWiRlYwLz2n4QXTKk04-cKMmlrg

	* Old Ixy (less increments, no training data): https://mega.nz/file/ixxzkR5T#cxxSNxPF1KmszJDqiP4K4Ou8tbl1SFKL6DdQC58k6zE

* Grandblue Fantasy character art (836 images, 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000 learn rate, 20000 steps, 1024x1024): https://files.catbox.moe/2uiyd4.pt

* Bombergirl (Stats: 178 images, 5e-8 learn rate continuing from old Bombergirl, 20000 steps, 768x768): https://files.catbox.moe/9bgew0.pt

	* Old Bombergirl (178 imgs, 0.000005 learning rate, 10k, 768x768): https://files.catbox.moe/4d3df4.pt

* Aki99 (200 images , 512x512, 0.00005, 19K steps, NAI): https://files.catbox.moe/bwff89.pt

* Aki99 (200 images , 512x512, 0.0000005, 112K steps, learning prompt: [filewords], NAI): https://www.mediafire.com/file/sud6u1vb0gvqswu/aki99-112000.7z/filehttps://files.catbox.moe/6hca0u.pt

* Great Mosu: https://files.catbox.moe/mc1l37.pt

	* Reupload: https://mega.nz/file/MlRVGbDJ#hwA868cievybQC_7T1yc3bDouUB54Bor-LsCfs04LEI

* mda starou: https://a.pomf.cat/xcygvk.pt

* Mogudan (12 vectors per token, 221 image dataset, preprocessing: split oversize, flipped mirrors, deepdanbooru auto-tag, 0.00005 learning rate, 62,500 steps): https://mega.nz/file/UtAz1CZK#Y5OSHPkD38untOPSEkNttAVi2tdRLBFEsKVkYCFFaHo

* Onono Imoko: https://files.catbox.moe/amfy2x.pt

	* Dataset: https://files.catbox.moe/dkn85w.zip 

* Etrian Odyssey (training rate 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000,20k steps, 512 x 512 pics): https://files.catbox.moe/94qm83.7z

* Jesterwii: https://files.catbox.moe/hlylo4.zip

* jtveemo (v1): https://mega.nz/folder/ctUXmYzR#_Kscs6m8ccIzYzgbCSupWA

	* 35k max steps, 0.000005 learning rate, 180 images, ran through deepbooru and manually cleaned up the txt files for incorrect/redundant tags.

	* Recommended the 13500.pt, or something near it

	* Recommended: https://files.catbox.moe/zijpip.pt

* Artsyle based on Yuugen (HBR) (Stats: 103 images, 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000 learn rate, 20000 steps, 1024x1024,Trained on NAI model): https://files.catbox.moe/bi2ts0.7z

* Alexi: https://files.catbox.moe/3yj2lz.pt (70000 steps)

	* as usual, works best with oppai loli tag. chibi helps as well

	* changes from original one i noticed during testing:  
		-hair shading is more subtle now  
		-nipple color transition is also more subtle  
		-eyelashes not as thick as before, probably because i used more pre-2022 pictures. actually bit sad about it, but w/e  
		-eyes in general look better, i recommend generating on 768×768 with highres fix  
		-blonde hair got a pink gradient for some reason  
		-tends to hide dicks between the breasts more often, but does it noticeably better  
		-likes to add backgrounds, i think i overcooked it a bit so those look more like artifacts, perhaps with other prompts it will look better  
		-less hags  
		-from my test prompts, it looked like it breaks anatomy less often now, but i mostly tested pov paizuri  
		-became kinda worse at non-paizuri pictures, less sharpness. because of that, i'm also including 60000 steps version, which is slightly better at that, but in the end, it's a matter of preference, whether to use newer version or not: https://files.catbox.moe/1zt65u.pt

* Ishikei: https://www.mediafire.com/folder/obbbwkkvt7uhk/ishikemono

* Curss style (slime girls): https://files.catbox.moe/0sixyq.pt 

* WIP Collection of hypernets: https://litter.catbox.moe/xxys2d.7z

* DEAD LINK Mumumu's art: https://mega.nz/folder/tgpikL6C#Mj0sHUnr-O6u4MOMDRTiMQ

* Senri Gan: https://files.catbox.moe/8sqmeh.rar

	* 2 hypernetworks and 5 TI

	* Anon: "For the best results I think using hyper + TI is the way. I'm using TI-6000 and Hyper-8000. It was trained on CLIP 1 Vae off with those rates 5e-5:100, 5e-6:1500, 5e-7:10000, 5e-8:20000."

* Ulrich: https://files.catbox.moe/jhgsxw.zip

* akisora: https://files.catbox.moe/gfdidn.pt

* lilandy: https://files.catbox.moe/spzm60.pt

* shadman: https://files.catbox.moe/kc850y.pt

	* anon: "if anyone else wants to try training, can recommend - 0.00005:2000, 0.000005:4000, 0.0000005:6000 learning rate setup (6k steps total with 250~1000 images in dataset)"

* not sure what this is, probably a style: https://files.catbox.moe/lnxwks.pt

* ndc hypernet, muscle milfs: https://files.catbox.moe/hsx4ml.pt

* Asanuggy: https://mega.nz/folder/Uf1jFTiT#TZe4d41knlvkO1yg4MYL2A

* Tomubobu: https://files.catbox.moe/bzotb7.pt

	* Works best with jaggy lines, oekaki, and clothed sex tags.

* satanichia kurumizawa macdowell (around 552 pics in total with 44.5k steps, most of the datasets are fanarts but some of them are from the anime, tagged with deepdanbooru, flipped and manually cropped): https://files.catbox.moe/g519cu.pt

* Imazon v1: https://files.catbox.moe/0e43tq.pt

* Imazon v2: https://files.catbox.moe/86pkaq.pt

* WIP Baffu: https://gofile.io/d/4SNmm5

* Ilulu (74k steps at 0.0005 learning rate, full NAI, init word "art by Ilulu"): https://files.catbox.moe/18ad25.pt

* belko paizuri (86k swish + normalization): https://www.mediafire.com/folder/urirter91ect0/belkomono

	* WIP: training/0.000005/swish/normalization 

* Pinvise (Suzutsuki Kirara) (NAI-Full with 5e-6 for 8000 steps and 5e-7 until 12000 steps on 200 (400 with flipped) images): https://litter.catbox.moe/glk7ni.zip

* Bonnie: https://files.catbox.moe/sc50gl.pt

* Another batch of artists hypernetworks (some are with 1221 structure, so bigger size)

	* https://files.catbox.moe/srhrn6.pt - diathorn

	* https://files.catbox.moe/dytn06.pt - gozaru

	* https://files.catbox.moe/69t1im.pt - Sunahara Wataru

* kunaboto (new swish activation function + dropout using a learning rate of 5e-6:12000, 5e-7:30000): https://files.catbox.moe/lynmxm.pt

	* aesthetic: https://files.catbox.moe/qrka4m.pt

* Reine: https://litter.catbox.moe/1yjgjg.pt

* Om (nk2007): 

	* 250 images (augmented to 380), learning rate: 5e-5:380,5e-6:10000,5e-7:20000, template: [filewords] 

	* 10k step : https://files.catbox.moe/8kqb4c.pt

	* 16k step : https://files.catbox.moe/7vtcgt.pt

	* 20k step (omHyper): https://files.catbox.moe/f8xiz1.pt

* Spacezin: https://mega.nz/folder/Os5iBQDY#42xOYeZq08ZG0j8ds4uL2Q

	* excels at his massive tits, covered nipples, body form, sharp eyes, all that nice stuff

	* no cbt data

	* using the new swish activation method +dropout, works very well, trained at 5e-6 to 14000

	* data it was trained on and cfg test grid included in the folder

	* Hypernetwork trained on 13 handpicked images from spacezin

	* recommend using spacezin in the prompt, using 14000 step hypernetwork, lesser steps are included for testing

	* Aesthetic gradient embedding included

* amagami artstyle (30k,5e-6:12000, 5e-7:30000,swish+dropout): https://files.catbox.moe/3a2cll.7z

* Ken Sugimori (pokemon gen1 and gen2) art: https://files.catbox.moe/uifwt7.pt

* mikozin: https://mega.nz/folder/a0wxgQrR#OnJ0dK_F6_7WZiWscfb5hg

	* Trained a hypernetwork on mikozin's art, using nai full pruned, swish activation method+dropout

	* placing mikozin in the prompt will make it have a stronger effect, as all the training prompts include the [name] at the end.

	* has a number of influences on your output, but mostly gives a very soft, painted style to the output image

	* Aesthetic gradient embedding also included, but not necessary

	* check the training data rar to read the filewords to see if you want to call anything it was specifically trained on

	* Found on Discord (copied from SD Training Labs discord, so grammar mistakes may be present):

* Pippa (trained on NAI 70%full-30%sfw): https://files.catbox.moe/uw1y8g.pt

* reine (WIP): https://files.catbox.moe/od4609.pt

* WiseSpeak/RubbishFox (updated): https://files.catbox.moe/pzix7f.pt

	* Info: Uses 176 Fanbox images that were preprocessed with splitting, flipping and mild touchup to remove text in Paint on about 1/4th of the images. I removed images from the Preprocess folder that did not have discernable character traits. Most images are of Tamamo since that is his waifu. Total images after split, flip, and corrections was 636. Took 13 hours at 0.000005 Rate at 512x512. Seems maybe a bit more touchy than the 61.5K file, but I believe that when body horror isn't present you can match the RubbishFox's style better.

* Style from furry thread: https://files.catbox.moe/vgojsa.pt

* 2bofkatt (from furry thread): https://files.catbox.moe/cw30m8.pt

* Hypernetwork trained on all 126 cards from the first YGO set in North America, 'Legend Of The Blue Eyes White Dragon' released on 03/08/2002: https://mega.nz/folder/ILkwRZLb#UJ03LDIfcMiFTn6-pyNyXQ

* WiseSpeak (Rubbish Fox on Twitter): https://files.catbox.moe/kyllcc.pt

	* Info: Uses 176 images that were preprocessed with splitting, flipping and mild touchup to remove text in Paint on about 1/4th of the images. I removed images from the Preprocess folder that did not have discernable character traits. Most images are of Tamamo since that is his waifu. Total images after split, flip, and corrections was 636. Took 8 hours at 0.000005 Rate at 512x512

	* 93k, less overtrained: https://files.catbox.moe/fluegz.pt

* Large collection of stuff from korean megacollection: https://mega.nz/folder/sSACBAgC#kNiPVzRwnuzs8JClovS1Tw

* Crunchy: https://files.catbox.moe/tv1zf4.pt

* Obui styled hypernetwork (125k steps): https://files.catbox.moe/6huecu.pt

* KurosugatariAI (2 hypernets, 1 embed, embedding is light at 17 token weight. at 24 or higher creator anon thinks the effect would be better): https://mega.nz/folder/TAggRTYT#fbxf3Ru8PkXz_edIkD2Ttg

* Amagami (Layer structure 1, 1.5 1.5 1; mish; xaviernormal; No layer normalization; Dropout O (appling only at 2nd layer due to bug); LR 8e-06 fixed; 20k done): https://files.catbox.moe/ucziks.7z

* Reine (from VTuber dump, might be pickled): https://files.catbox.moe/uf09mp.pt

* Onono imoko: https://mega.nz/file/67AUDQ4K#8n4bzcxGGUgaAVy7wLXvVib0jhVjt2wPS-jsoCxcCus

	* Info moved to discord section

* Sironora: 

	* 30k: https://files.catbox.moe/oej0si.pt

	* 17k: https://files.catbox.moe/kodsvu.pt

* minakata hizuru (summertime girl): https://files.catbox.moe/gmbnnr.pt

* a1 (4.5k): https://files.catbox.moe/x6zt6u.pt

* 焦茶 / cogecha hypernetwork, trained against NAI (DEAD LINK): https://mega.nz/folder/BLtkVIjC#RO6zQaAYCOIii8GnfT92dw

* 山北東 / northeast_mountain hypernetwork, trained against NAI (DEAD LINK): https://mega.nz/folder/RflGBS7R#88znRpu7YC1J1JYa9N-6_A

* emoting mokou (cursed): https://mega.nz/folder/oPUTQaoR#yAmxD_yqeGqyIGfOYCR4PQ

* Cutesexyrobutts and gram: https://files.catbox.moe/silh2p.7z

* Scott: https://files.catbox.moe/qgqbs7.7z

* zunart (NAI, steps from 20000 to 50000): https://mega.nz/file/T9RmlbCQ#_JPkZqY5f0aaNxVc8MnU3WQHW4bv_yCWzJqOwL8Uz1U

* HBRv3D aka Heaven Burns Red (yuugen) retrained on new dataset of 142 mixed images: https://files.catbox.moe/urjkbm.7z

	* Setting was 1,2,1 relu ,Learning rate: 5e-6:12000, 5e-7:30000

* momosuzu nene: https://mega.nz/folder/s8UXSJoZ#2Beh1O4aroLaRbjx2YuAPg

* TATATA and Alkemanubis: https://mega.nz/folder/zYph3LgT#oP3QYKmwqurwc9ievrl9dQ

	* Tatata: Contains dataset, hypernetworks for steps 10000-19000 with a 1000 steps step, as well as full res sfw and nsfw comparisons.

	* It was created before layer structure option, so it parameters are 1, 2, 1 layer structure, linear activation function.

	* Alkemanubis: Alkemanubis is with elu activation function and normalisation, Alkemanubis4 is with swish and dropout, Alkemanubis5 is with linear and dropout. All have 1, 2, 4, 2, 1 layer structure.

	* dataset and more fullres preview grid are inside too.

* HKSW (wrong eye color because of dataset): https://files.catbox.moe/dykyab.pt

* Nanachi and Puuzaki Puuna (retrained, 4700 steps, sketches are good, VAE turned off): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

* HiRyS: https://mega.nz/file/Mk8jTZ4I#TdlF5Bxwz_gAuQeR0PWa_YUZotcQkA34d6m49I6eUMc

	* Dead link, I think this is the same hypernetwork: https://litter.catbox.moe/rx8uv0.pt

* 4k, 3d, highres images: 4k, 3d, highres images: https://mega.nz/file/UAEHkbhK#R-zdpiIz6Ig2-laa-M9_Hmtq6xgLNJZ0ZwVOiXt3OSc

	* It has a preference for 3d design, large breasts and curves. It also has a preference for applying backgrounds,if none suggested. usually parks, beaches, indoors or cityscapes

	* Comparison: https://i.4cdn.org/h/1667278030582788.png

* Okegom (Funamusea / Deep Sea Prisoner): https://mega.nz/file/XYQF3YoZ#BAvBQduEx-tnUKvyJQ3mH-zOa_cKUKxpc58YpO8h2jc

	* Crashed after 5.3k steps, continued training after when hypernetwork training resuming is broken. Apprently it got better

	* Uploader: Alright, it's done. Maybe it's the small training data or the mediocre tagging but sometimes you get stuff that doesn't resemble their art style. Still releasing the three models I liked though, they work nicely with img2img.

* Funamusea/Okegom/Mogeko (12500 steps): https://mega.nz/file/SBg0zBIa#BU1KkBY1vMvLXpfkDci1RZYi5f8P0yN5oyQzGYXF8q0

	* Notes by uploader:

	> Most results (at least with img2img) will have a chibi style regardless of your prompt.  
	> 30 steps recommended.  
	> Does very well with white skin/pale characters, this is because the hypernetwork is trained mainly on white characters. Not because I wanted to but because it's what she tends to draw the most.  
	> Hypernetwork has most of her NSFW art in its data including a fanart which looks like it was drawn by her, just so the AI has a reference. So, yes, it can generate nudity and porn in her style, although I'm not sure about penetration stuff because I haven't tried.  
	> "outline" tag is recommended in prompt to have the same thick outlines she often uses in her artwork.

* Sakimichan: https://mega.nz/file/TBJwFDLI#H_bgih8qbWe-EN4ntL_7ur6Ylr2qbcxhDwlC2AfWpnc

	* dead link: https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8

* arnest (109 images, 12000 steps): https://mega.nz/file/HNIhlZ7B#o1hpR04PxBDWTEHDfxLfbRi_9K56HVJ58YgCwDUeRMw

	* uploader: Hypernetwork trained on 109 total images dating from 2015 to 2022, including his deleted NSFW commissions and Fanbox content. Also trained on like two or three pre-2015 images just because why not. Should be able to do Touhou characters (especially Alice and Patchouli) extremely well.

	* I recommend using the white pupils tag for the eyes to look like picrel.

* Zanamaoria (20k steps, 47 imgs, mostly dark-skinned elves, and paizuri/huge tits): https://files.catbox.moe/10iasp.pt

	* 18500 steps: https://files.catbox.moe/xgf1ho.pt

* Pinvise (30k steps, 5e-6 for 8k steps and 5e-7 for the rest): https://files.catbox.moe/dec3h3.pt

	* dead: https://litter.catbox.moe/nrpkuy.pt

* Black Souls II (V2 wasn't uploaded because it was "disappointing"):

	* V1 (Image: 181 augmented to 362,Learning Rate 5e-5:362,5e-6:14000,5e-7:20000, steps: 10k): https://files.catbox.moe/fdoyt9.pt

	* V3 (Image:164 augmented to 328, Learning Rate 5e-5:328,5e-6:14000,5e-7:20000, steps: 10k): https://files.catbox.moe/1r36tp.pt

		* uploader: Unlike V1, I manually edited almost all tags generated with deepdanbooru with the dataset tag editor

	* Uncensored X/Y plots:

		* V3 (strength: 1) : https://files.catbox.moe/tse4kr.png, https://files.catbox.moe/8y91f0.png (no 'sketch')

		* V1 (strength: 0.7): https://files.catbox.moe/pml06i.png ('sketch'), https://files.catbox.moe/18993y.png (without "sketch")

	* Uploader: Those two hypernetwork seem to be more accurate if we put "sketch" in the prompt. V1 break if we set hypernetwork strength to 1 (or anything over 0.8) and 0.7 seem to be the sweet spot. V3 does not seem to have the same problem.

* Hataraki Ari (30k, 50k, and 100k steps): https://mega.nz/folder/TZ5jXYrb#-NXJo8wlmanr8ebbJ5GBBQ

	* Training Info: 

	> Modules: 768, 320, 640, 1280  
	> Hypernetwork layer structure: 1, 2, 1  
	> Activation function: swish + dropout  
	> Layer weights initialization / normalization: none  
	> 115 images, size 512x512, manually selected from patreon gallery on sadpanda  
	> Watermarks + text manually removed or cropped out  
	> Deepbooru used for captions  
	> Hypernetwork learning rate: 5e-6:12000, 5e-7:30000, 2.5e-7:50000, 1e-7:100000

	* Uploader note: Works best with huge or gigantic breasts. Occasionally has some problems with extra limbs or nipples. Tags like tall female, muscular female or abs may lead to small heads or weirdly proportioned bodies, so I recommend lowering the weighting on those.

* IRyS (not sure if this is a reupload of a previous one): https://files.catbox.moe/qnery5.pt

* Nanachi (reupload, re-retrained WITHOUT sneaky VAE - 0.000005 learning rate, around 16000 steps, around 13000 steps): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

* Puuzaki Puuna (reupload, re-retrained WITHOUT sneaky VAE - 0.000005 learning rate): https://mega.nz/folder/PfhRUbST#6oXUaNjk_B6nhJzjc_M0UA

* Sayori (trained on mostly nsfw CGs (30 out of 40 images were nsfw) from nekopara, koikuma + fandisc, and tropical liquor, trained on NAI pruned): https://mega.nz/file/LegFzJxa#Q1Se9fByKcjuXA2DNWt0gCaV3rCP8U-voBKgFjOevF8

* Henreader: https://files.catbox.moe/q6t6vw.pt

	* 104 imgs, mostly from Loli no Himo and some of his recent art, used a grabber to download with gelbooru tags

	* Training settings:

		* layer: 1, 2, 1

		* activation function: linear

		* initialization: Normal

		* Images: 104 (208 with flipped images)

		* dataset: https://files.catbox.moe/e0e3nk.7z (NSFW + loli)

		* resolution: 512x512

		* Learning rate: 5e-5:832,5e-6:14000,5e-7:2000

		* steps: 10000

		* Template: [filewords] 

* Sakimichan (not sure if it's a reupload): https://cdn.discordapp.com/attachments/1041563266041794580/1041563947528093746/sakimichan.pt

* Dohna2 (apparently incorporates backgrounds better (for stuff like tentacles), anon reports underbaked, wip): https://mega.nz/file/y65DwBYQ#1BLmT4IyuUVeUrjYSIjE-oBpmMvkVp4ZSCXVV3jkOb8

	* Password: https://rentry.org/f787o

	* Original dead link: https://litter.catbox.moe/8m4ue9.7z

* Kinjo kuromomo: https://files.catbox.moe/8bgjto.pt

	* Example pic (Prompt: https://rentry.org/e8mhs): https://i.4cdn.org/g/1668467554941924s.jpg

* ruan chen yue (artstyle, rcy3):

	* Example: https://i.4cdn.org/g/1668780254347358s.jpg

	* Based on Anythingv3 (op recommended the anything vae too), set to CFG 9 for best results

	* Example prompt: masterpiece, highest quality, colorful, shiny hair, colored hair shine, ((by ruan chen yue)), rcy3, vibrant, soft face, lips, blush, sparkles, glitter, HDR

	* Negative: nsfw, worst quality, low quality, normal quality, jpeg artifacts, signature, watermark, username, blurry, poorly drawn hands, poorly drawn limbs, bad anatomy, deformed, amateur drawing, odd, lowres, bad hands, text, error, missing fingers, extra digit, fewer digits, cropped, multiple body parts, two-colored hair, multicolored hair

* chinanago (chinanago7010) (NAI, 10k, all drawings on gelbooru): https://files.catbox.moe/kk1rss.pt

	* Example: https://i.4cdn.org/g/1668823784304863s.jpg

* Dishwasher1910 (also known as dickwasher on /alg/) (NAI): https://files.catbox.moe/7fs8xu.pt

	* Example: https://i.4cdn.org/g/1668824088843108s.jpg

* Muk (monsieur): https://files.catbox.moe/q8jnsd.pt

	* Example: https://i.4cdn.org/g/1668824504567981s.jpg

* Olga Discordia (35k, old version): https://www.dropbox.com/s/fc8bg0ti7uy8qxz/olgadiscordiav6-35000.pt?dl=0

	* make sure you have these prompt to activate her: yellow eyes, intricate eyes, (symmetrical face), (mature female:1.2), pointy ears, elf, earrings, hair over one eye, jewelry, dark elf, breasts, black hair, long hair, dark skin, parted lips, thighhighs, gloves, 1girl, solo, 

	* final-pruned model. mixberry gives good results too. clip set at 2. vae is optional

	* More info by creator: can use final-pruned, berrymix and v3 without any problem. i do not recommend vae with it. clip set at 1 for higher detail. 2 for whatever. to get the prompt working, make sure to included dark elf, dark skinned female, and pointy ears. 

* olga discordia (Kuroinu) (50k steps):

	* https://www.dropbox.com/s/ivz7nr43b0xmbth/olgadiscordiav8-10000-7000%20armor%20-%20Copy.pt?dl=0

	* to activate olga, please use this prompt: 1girl, olga discordia, amber eyes, dark elf and dark skinned female, hair covering one eye.

	* for additional stuff, such as her outfit, you have to use purple armor, purple sleeves and purple thighhighs. for the top acccuracy, use disconnected corset purple armor. weight accordingly too.

	* NOTE: was trained with censored images. make sure to have censored and mosaic censored in the negative. put 1 or 2 emphasis on it. up to you.

	* works with every model too. works best with naileak and all berrymixes. clip at 1 or 2 depends on the model. enjoy

* Mogudan), Mumumu (Three Emu), Satou Shouji, Onomeshin, Bang-You, Aoi Nagisa, Honjou Raita, Amazon : https://mega.nz/folder/hlZAwara#wgLPMSb4lbo7TKyCI1TGvQ

	* Changelog of new stuff: onomeshin (pic https://i.4cdn.org/h/1669000305326267.png), Bang-You (https://i.4cdn.org/h/1669000350687492.png), Aoi Nagisa (https://i.4cdn.org/h/1669000401417659.png), Honjou Raita (uses new options, comparison between current one and the one mogubro uploaded: https://i.4cdn.org/h/1669000583045601.png), Amazon (https://i.4cdn.org/h/1669114002712582.png): 

	* Has training info, dataset, comparison, and hypernetworks

	* Amazon hypernet does the best on DPM++ 2M a Karras, has deformities on some other samplers

* Albino_Otokuyou (Otokuyou's Shinroi Ko character) (White eyelashes and true albinos): https://files.catbox.moe/k7ftww.rar

	* Good when using with Nerfgun3's new Albino_style

	* ex: https://i.4cdn.org/g/1668896107598228.jpg (Prompt: https://rentry.org/gacnc)

	* Best results: Half-closed eyes at low weight may have some benefits. Using my Albino_Otokuyou Shiroi Ko Hypernet at just 0.2 strength helps with white eyelash cohesion. Use 'parted bangs' and 'swept bangs' and prompts that clear space above the eyes to help consistently generate white eyelashes, experiment as you like.

	* Issues: My 30000step Hypernet has a slight problem squashing images, reducing the strength helps mitigate this quite abit, the AlbinoFix is slightly weaker but may be best used with Nerfgun3's embedding.

* Tatata + Dataset (supposedly trained on CHINAI + 0.45(Trinart115-SD-1.4)): https://mega.nz/folder/sTV0EI6b#hGotLRXpotvmYxqfTb_KMw/folder/8eMylBTK

* Eula Lawrence (old, seemed to be misplaced):  https://mega.nz/file/l9tAHJBD#xdXMf7vulY4GJBigxegFVLSOULONnk4o86qKHYoBZmc

* Kincora (Azur Lane artist): https://files.catbox.moe/enzbw6.pt

	*  Training:

		* > layer: 1, 2, 1

		* > activation function: linear

		* > initialization: Normal

		* > Images: 136 (half of those image are just portrait version of the other half)  or  272 if we count flipped images

		* > Dataset:  https://files.catbox.moe/yc9kkh.7z

		* > Steps: 20k

		* > Learning rate: 5e-5:816,5e-6:10000,5e-7:20000

		* > resolution: 512x512

		* > Template: [filewords] 

	* Example (it's the one on the right): https://i.4cdn.org/g/1669142706465584.jpg

* Tomoko: https://raw.githubusercontent.com/hlky/sd-embeddings/main/tomoko/tomoko.pt

- Morino Bambi (NUH) (NAI, 10k steps,learning rate: 5e-5:672,5e-6:10000,5e-7:30000, 224 images): https://files.catbox.moe/5x3icv.pt
	- Example (NSFW): https://i.4cdn.org/g/1669256512125648.jpg, Prompt: https://pastebin.com/GsZA9BEa
	- Example (SFW): https://i.4cdn.org/g/1669260253330069.jpg, Prompt: https://pastebin.com/DGD4DV7g
	- Dataset (NSFW): https://files.catbox.moe/q3l0wl.7z

Found on Discord:

* Art style of Rumiko Takahashi 

	> Base:  Novel AI's Final Pruned  
	> [126 images, 40000 steps, 0.00005 rate]  
	> Tips:  "by Rumiko Takahashi" or "Shampoo from Ranma" etc.

	* LINK: https://cdn.discordapp.com/attachments/1029640494915006504/1031188941245784124/rumikotakahashistyle.pt

* Amamiya Kokoro (天宮こころ) a Vtuber from Njiisanji [NSFW / SFW] (Work on WD / NAI)

	> (Training set: 36 Input images, 21500 Steps, 0.000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with nijisanji-kokoro to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0 

	* LINK: https://files.catbox.moe/032110.pt

* Haru Urara (ハルウララ) from Umamusume ウマ娘 [NSFW / SFW] (Work on WD / NAI)

	> Training set: 42 Input images, 21500 Steps, 0.000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with uma-urara to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0 

	* LINK: https://files.catbox.moe/qixn0m.pt

* Genshin Impact [SFW]

	> 992 images, official art including some game assets  
	> 15k steps trained on nai  
	> use "character name genshin impact" or "genshin impact)" for best results

	* LINK: https://files.catbox.moe/t4ooj6.pt 

	* 45k step version: https://files.catbox.moe/newhp6.pt

* Ajitani Hifumi (阿慈谷 ヒフミ) from Blue Archive [NSFW / SFW] (Work on WD / NAI)

	> Training set: 41 Input images, 20055 Steps, 0.000005 Learning rate.  
	> Model: NAI-Full-Prunced  
	> Start with ba-hifumi to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0  
	> 1.0 Is a little bit overkill I thought about.  
	> If you want to go different costume like swimsuit or casual, I think 0.4 to 0.7 is the best ideal rate.

	* LINK: https://files.catbox.moe/ylbekm.7z 

* Higurashi no Nako Koro ni // ryukishi07's artstyle

	> Trained on Higurashi's original VN sprites. Might do Umineko's sprites next, or mix the two together.  
	> 8k steps, 15k steps, 18k steps included.

	* LINK: https://drive.google.com/file/d/1A8KMQV_0qNHmM8yYFAxLdt8dTWt8GoSo/view?usp=sharing 

	* DATASET: https://cdn.discordapp.com/attachments/1029640494915006504/1030760102493425664/higurashi-datset.7z

* Trained Koharu of Blue Archive. I'm not very good at English, so it's painful to read this describe.

	> Training set: 41 images, 20000 steps, 0.000005 learning rate.  
	> Model: WD1.3 merged NAI (3/7 - Sigmoid)

	* LINK: https://files.catbox.moe/b6a6mc.pt

* queencomplexstyle (no training info): https://files.catbox.moe/32s6yb.pt

* Shiroko of Blue Archive. Training set: 14 images at 20000 steps 0.000005 learning rate. The tag is 'ba-shiroko'

	* Link: https://mega.nz/file/sx1DCS4Y#3v4bSaA3iq3V7SuRQx4ppKaYKOgPHBk7x3NJJDkG8ys

* Queen Complex 

	> (https://queencomplex.net/gallery/?avia-element-paging=2) [NSFW]  
	> "It's a cool style, and it has nice results.  Don't need to special reference anything, seems to work fine regardless of prompt."  
	> Base Model:  Novel AI  
	> Training set:  52 images at 4300 steps 0.00005 learning rate (images sourced from link above and cropped) 

	* https://cdn.discordapp.com/attachments/1029640494915006504/1030277229512491038/queencomplexstyle-2-4300.pt

* Raichiyo33 style hypernetwork. Not perfect but seems good enough.

	> Trained with captions from booru tags for compability with model + art by raichiyo33 in the beginning over NAI model.  Use "art by raichiyo33" in the begining of prompt to triggering.  
	> Some useful tips: 
	> 1) with tag "traditional media" produce more beautiful results
	> 2) try to avoid too much negativ promts. I use only "bad anatomy, bad hands, lowres, worst quality, low quality, blurry, bad quality" even that seems too much. With many UC tags (especially with full NAI set of uc) it will produce almost generic NAI result. 
	> 3) Use CLIP -2 (because its trained over NAI, ofc) 

	* LINK: https://mega.nz/file/VJ5H3KhL#Hkl8LIHRS5AiDIrytxPpht2ckO9oTpwZVgxbJy-vdcU

* Genshin Impact [SFW]

	> 992 images, official art including some game assets  
	> 15k steps trained on nai  
	> use "character name genshin impact" or "genshin impact)" for best results

	* LINK: https://files.catbox.moe/t4ooj6.pt 

* Gyokai-ZEN (aliases: Gyokai / Onono Imoko / shunin)  [NSFW / SFW] (For NAI) 

	> Includes training images  
	> Training set: 329 Input images, Various steps included. Main model is 21,000 steps.  
	> Training model: NAI-Full-Pruned.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0. Lower strength is good for the overtrained model.  
	> Emphasise the hypernet by using the prompt words "gyokai" or "art by gyokai".
	> 
	> Note: the prompt words "color halftone" or "halftone" can be good at adding the little patterns in the shading often seen in onono imoko's style.  
	> HOWEVER: This often results in a noise/grain which often can be fixed if you render at a resolution higher than 768x768 (with hi-res fix)  
	> Omit these options from your prompt if the noise is too much in the image. Your outputs will be sharper and cleaner, but unfortunately less in the style.
	> 
	> gyokai-zen-1.0 is 16k steps at 0.000005, then up to 21k steps at 0.0000005  
	> gyokai-zen-1.0-16000 is a bit less trained (16k steps) and sometimes outputs cleaner at full strength.  
	> gyokai-zen-1.0-overtrain is at 22k steps all at 0.000005. It can sometimes be a bit baked in.

	* Link: https://mega.nz/file/67AUDQ4K#8n4bzcxGGUgaAVy7wLXvVib0jhVjt2wPS-jsoCxcCus

* yapo (ヤポ) Art Style [NSFW / SFW] (Work on WD / NAI)

	> Training set: 51 Input images, 8000 Steps, 0.0000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with in style of yapo / yapo to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.4 to 0.8 
	>

	* Preview Link: https://imgur.com/a/r2sOV41

	* Download Link: https://anonfiles.com/N6B4d4D7y9/yapo_pt 

* Lycoris recoil chisato

	> Training set: 100 Input images, 21500 Steps, 0.000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with "cr-chisato"  
	> Recommend Hypernetwork Strength rate: 0.4 to 0.8. clip skip : 1 Euler

	* Link: https://mega.nz/file/wlchDJpB#9nh5rIYtzRIhfLGvYeMrj6AOG-PcEx9JscTp4wXi-_E

* Liang Xing styled

	> Artstation: https://www.artstation.com/liangxing  
	> 20,000 steps at varying learning rates down to 0.000005, 449 training images.  Novel AI base.  
	> Requires that you mention Liang Xing in some form as that was what I used in the training document.  "in the style of Liang Xing" as an example.

	* Examples: https://cdn.discordapp.com/attachments/1029640494915006504/1031785112246952007/Liang_Zing_D.Va_Outputs.zip

	* Link: https://cdn.discordapp.com/attachments/1029640494915006504/1031688311804276826/liangxingstyle-20000.pt

* アーニャ(anya)(SPY×FAMILY) [NSFW / SFW] (Work on WD / NAI)

	> Training set: 46 Input images, 20500 Steps, 0.00000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with Anya to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 0.9 
	>

	* Preview Link: https://imgur.com/a/ZbmIVRe

	* Download Link: https://anonfiles.com/ZdKej8D5ya/Anya_pt

* cp-lucy

	> Training set: 67 Input images, 21500 Steps, 0.000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with "cp-lucy" / clip skip : 1  
	> Recommend Hypernetwork Strength rate: 0.6 to 0.9

	* Link: https://mega.nz/file/lltzwaDI#_ZoJktJmCdBQZtYFNuuYnbnySIh5cxlOf9rYT73O2ig

* バッチ (azur bache) (アズールレーン) [NSFW / SFW] (Work on WD / NAI)

	> Training set: 55 Input images, 20050 Steps, 0.00000005 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with azur-bache to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0 

	* Link: https://anonfiles.com/Q84dw4D1y4/azur-bache_pt

* Ixy (by ixyanon):

	> Hypernetwork trained on ixy's style from 100 handpicked images from them, using split oversized images.  
	> Trained in Nai-full-pruned  
	> recommend using white pupils in the prompt, ixy for a greater effect of their style  
	> Uses: will generally make your output more flat in shading, very good at frilly stuff, and white pupils of course  
	> Grid examples located in the folder.

	* https://mega.nz/folder/yspgEBhQ#GLo7mBc1EH7RK7tQbtC68A 

* Blue Archives Azusa

	> Training set: 28 Input images, 20000 Steps, 5e-6:12000, 5e-7:30000 Learning rate.  
	> Training model: NAI-Full-Prunced  
	> Start with ba-azusa to get a good result.  
	> Recommend Hypernetwork Strength rate: 0.6 to 1.0 clip skip : 1

	* Link: https://mega.nz/file/UslRnQbb#A37957mbty2PtnRKZVlikb8y8l0RuOqluebPsRXhFyg

* Makoto Shinkai HN

	> trained on a roughly ~150 images, 1,2,2,1 for 30,000 steps on NAI model, use "art by makotoshinkaiv2" to trigger it (experimental, it might not be that much different from base model but I have noticed that it improved composition when paired with the aesthetic gradient)  
	> 1007 frames from the entire 5 Centimeter Per Second (Byousoku 5 Centimeter) (2007) animovie by Makoto Shinkai

	* Dataset (for the aesthetic gradient and for general hypernetwork training/finetuning of a model if anyone else wants to attempt to get this style down.):

		* 1: https://cdn.discordapp.com/attachments/1022209206146838599/1033198526714363954/5_Centimeters_Per_Second.7z.001

		* 2: https://cdn.discordapp.com/attachments/1022209206146838599/1033198659321475184/5_Centimeters_Per_Second.7z.002

		* 3: https://cdn.discordapp.com/attachments/1022209206146838599/1033198735657803806/5_Centimeters_Per_Second.7z.003

	* Link: https://cdn.discordapp.com/attachments/1032726084149583965/1033200762085453874/makotoshinkaiv2.pt

	* Aesthetic Gradient: https://cdn.discordapp.com/attachments/1033147620966801609/1033196207478161488/makoto_shinkai.pt

* Hypernetwork based on the following prompts:

	* cervix, urethra, puffy pussy, fat_mons, spread_pussy, gaping_anus, prolapse, gape, gaping

	> Released by IWillRemember#1912  
	> This hyper network was trained for 2000 steps at different learning rates on different batches of images (usually 25 images each batch)
	> 
	> I suggest using an HYPERNETWORK STRENGTH OF 0,5 or maybe up to 0,8 since it's really strong ; it is compatible with almost all anime like models and it performs great even with semi realistic ones.
	>

	> The examples are made using the Nai model , but it works with ally , and any other anime based model if strength is adjusted acccordingly , also it COULD work with f111 and other models with the right prompts , to get really fat labia majora/minora , and/or gaping
	>

	* Link: https://mega.nz/file/pSN3mYoS#Q7e8tJWPSYGxdsyJMwhhtE5Jj8-A5e-sYZHhzbi3QAg

	* Examples: https://cdn.discordapp.com/attachments/1018623945739616346/1033541564603039845/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033542053444988938/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033544232310411284/unknown.png, https://cdn.discordapp.com/attachments/1018623945739616346/1033550933151469688/unknown.png

* (reupload from the 4chan section) Hypernetwork trained on spacezin's art, 13 handpicked images flipped and used oversized crop, data is the rar in the link

	> by ixyanon  
	> Trained in Nai-full-pruned, using swish activation method with dropout, 5e-6 training rate  
	> recommend using spacezin in the prompt, lesser steps are included for testing and usage if 20k is too much  
	> Uses: booba with covered nipples, sharp eyes and all that stuff you'd expect from him.  
	> Aesthetic gradient embedding included, helps a lot to use, nails the style significantly further if you can find good settings…

	* Link: https://mega.nz/folder/Os5iBQDY#42xOYeZq08ZG0j8ds4uL2Q

* Hypernetwork trained on mikozin's art (reupload from 4chan section)

	> Trained in Nai-full-pruned, using swish activation method with dropout, 5e-6 training rate  
	> placing mikozin in the prompt will make it have a stronger effect  
	> has a number of effects, but mostly gives a very soft, painted style to the output image  
	> Aesthetic gradient embedding included, not necessary but could be neat!  
	> Data it was trained on included in the mega link, if you want something specific from the data it was trained on it'll help looking at the fileword txts

	* Download: https://mega.nz/folder/a0wxgQrR#OnJ0dK_F6_7WZiWscfb5hg

* yabuki_kentarou(1,1_relu_5e-5)-8750

	> Source image count: 75 (white-bg, hi-res, and hi-qual)  
	> Dataset image count: 154 (split, 512x512)  
	> Dataset stress test: excellent (LR 0.0005, 2000 steps)  
	> Model: NAI [925997e9]  
	> Layer: 1, 1  
	> Learning rate: 0.00005  
	> Steps: 8750

	* Download: https://anonfiles.com/H7RajcFby6/yabuki_kentarou_1_1_relu_5e-5_-8750_pt 

* namori(1,1_relu_5e-5)-9000.pt

	> Source image count: 50 (white-bg, hi-res, and hi-qual)  
	> Dataset image count: 98 (split, 512x512)  
	> Dataset stress test: excellent (LR 0.0005, 2000 steps)  
	> Model: NAI [925997e9]  
	> Layer: 1, 1  
	> Learning rate: 0.00005  
	> Steps: 9000  
	> Preview: https://i.imgur.com/MEmvDCS.jpg  
	> Download: https://anonfiles.com/n2W8rdF7y5/namori_1_1_relu_5e-5_-9000_pt

* Yordles:

	> Released by IWillRemember#1912 on discord  
	> Trained for roughly 30000 steps at different learning rates on 80 images  
	> Trained with NAI but they work best with Arena's Gape60  
	> Trained on the following tags: Yordle, tristana, lulu_(league_oflegends), poppy(league_oflegends), vex(league_oflegends), shortstack  
	> Suggested to not use negative prompts 
	> 
	> Yordles = to be use with an HYPERNETWORK STRENGHT OF 0,7  
	> Yordles-FullSTR = to be useed with an HYPERNETWORK STRENGHT OF 1
	> 
	> Example for Poppy : masterpiece, highest quality, digital art, colored skin, blue skin, white skin, 1girl, (yordle:1.1), purple eyes, (poppy(league_of_legends):1.1), shortstack, twintails, fang, red scarf, white armor, thighs, sitting, night, gradient background , grass , blonde hair , on back, :d
	> 
	> I suggest not using negative prompts or use only the conditional ones like : monochrome, letterbox, ecc ecc  
	> https://mega.nz/file/FCdiSIbI#ekOnlvox0ksEe1zzOQCFXgMJPkClEFPJFfGaAXv4rYc  
	> Examples:  
	> https://cdn.discordapp.com/attachments/1023082871822503966/1037513553386684527/poppy.png  
	> https://cdn.discordapp.com/attachments/1023082871822503966/1037513571355066448/lulu.png 

Colored eyes:

	>Released by IWillRemember#1912
	>I'm releasing an Hn to do better animation like glowing eyes, and a more slender face/upper body.
	>
	>The tags are : 
	>detailed eyes, 
	>(color) eyes  = ex: white eyes, blue eyes, etc etc
	>collarbone
	>
	>Trained for 12k steps on a 80 ish images dataset
	>
	>You can use the Hn with a str of 1 without any problem.
	>
	>Happy prompting!
	>
	>Example: https://media.discordapp.net/attachments/1023082871822503966/1038115846222008392/00162-3940698197-masterpiece_highest_quality_digital_art_1girl_on_back_detailed_eyes_perfect_face_detailed_face_breasts_white_hair_yell.png?width=648&height=702
	>
	>https://mega.nz/file/dHFwmaxS#NQhMPjT4TElPXX_YAZhTsFrQ36PDJhpWFm9BcHU_BO4 

### **Aesthetic Gradients**

Collection of Aesthetic Gradients: https://github.com/vicgalle/stable-diffusion-aesthetic-gradients/tree/main/aesthetic_embeddings

* Pussy improvements (Called an aesthetic embed, not sure if it's supposed to be here or in embeds):  
https://files.catbox.moe/l7gclr.pt

### **Polar Resources**

* Scat (??): https://files.catbox.moe/8hklc5.pt

* Horse (?): https://files.catbox.moe/idm0vf.pt

* MLP nsfw f16 f32 (might be pickled): https://drive.google.com/drive/folders/14JyQE36wYABH-0TSV_HBEsBJ3r8ZITrS?usp=sharing

### DEAD/MISSING

If you have one of these, please get it to me

Dreambooth:

* Anya Taylor-Joy: https://drive.google.com/drive/mobile/folders/1f0FI2Vtr0dNfxyCzsNkNau20JT9Kmgn-

	* https://www.reddit.com/r/StableDiffusion/comments/xx8p1p/anya_taylorjoy_model_link_in_comments/

* Fujimoto: https://huggingface.co/demibit/fujimoto_temp/tree/main

* Nardack: https://huggingface.co/Alice2O3/Nardack_dreambooth

	* Trained on artworks of Nardack on dreambooth with 60000 and 80000 steps

	* Dataset: https://huggingface.co/datasets/Alice2O3/Nardack_sd_Dataset

Embed:

* Omaru-polka: https://litter.catbox.moe/qfchu1.pt

* Sakimichan: https://mega.nz/file/eE8QDKrI#y7kdyWgPUjI4ZkY8PSq89F28eU_Vz_0EgTbG6yAowH8

* Deadflow (190k, "bitchass"(?)): https://litter.catbox.moe/03lqr6.pt

* Wagashi (12k, shitass(?)), no associated pic or replies so might be pickled: https://litter.catbox.moe/ktch8r.pt

* ex-penis-50000.pt and ex-penis-35000.pt

* Elira default-5500 16v 5500 steps

* Wiwa 4v 10000 steps

Hypernetworks:

* Chinese telegram (dead link): https://t.me/+H4EGgSS-WH8wYzBl

* HiRyS: https://litter.catbox.moe/rx8uv0.pt

* Huge training from KR site: https://mega.nz/folder/wKVAybab#oh42CNeYpnqr2s8IsUFtuQ

	* https://arca.live/b/aiart/60758880

* 焦茶 / cogecha hypernetwork, trained against NAI: https://mega.nz/folder/BLtkVIjC#RO6zQaAYCOIii8GnfT92dw

* 山北東 / northeast_mountain hypernetwork, trained against NAI: https://mega.nz/folder/RflGBS7R#88znRpu7YC1J1JYa9N-6_A

* Sayori (not sure if it's just a reupload of the one in the rentry): https://mega.nz/file/ArR0jRAS#3Q4mBmSd-kqFNVapkr52XMbDoSEBM2ko_-cDsWqXUbU

Datasets:

* expanded ie_(raarami) dataset: https://litter.catbox.moe/j4mpde.zip

* Toplessness: https://litter.catbox.moe/mttar5.zip

* https://gofile.io/d/R74OtT

* thanukiart (colored): https://www.dropbox.com/sh/mtf094lb5o61uvu/AABb2A83y4ws4-Rlc0lbbyHSa?dl=0

## Training

* Training guide for textual inversion/embedding and hypernetworks: https://pastebin.com/dqHZBpyA

* Hypernetwork Training by ixynetworkanon: https://rentry.org/hypernetwork4dumdums

* Training with e621 content: https://rentry.org/sd-e621-textual-inversion 

* Informal Model Training Guide: https://rentry.org/informal-training-guide

* Anon's guide: https://rentry.org/stmam

* Anon2's guide: https://rentry.org/983k3

	* Full Textual Inversion folder: https://files.catbox.moe/c6502c.7z

* Wiki: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Textual-Inversion

* Wiki 2: https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Features#textual-inversion

> Use pics where:
> * Character doesn't blend with background and isn't overlapped by random stuff
> * Character is in different poses, angles, and backgrounds
> * Resolution is 512x512 (crop if it's not)

* Manually tagging the pictures allows for faster convergence than auto-tagging. More work is needed to see if deepdanbooru autotagging helps convergence

* Dreambooth on 8gb: https://github.com/huggingface/diffusers/tree/main/examples/dreambooth#training-on-a-8-gb-gpu

* Finetune diffusion: https://github.com/YaYaB/finetune-diffusion

	* Can train models locally

* Training guide: https://pastebin.com/xcFpp9Mr

* Reddit guide: https://www.reddit.com/r/StableDiffusion/comments/xzbc2h/guide_for_dreambooth_with_8gb_vram_under_windows/

* Reddit guide (2): https://www.reddit.com/r/StableDiffusion/comments/y389a5/how_do_you_train_dreambooth_locally/

* Dreambooth (8gb of vram if you have 25gb+ of ram and Windows 11): https://pastebin.com/0NHA5YTP

* Another 8gb Dreambooth: https://github.com/Ttl/diffusers/tree/dreambooth_deepspeed/examples/dreambooth#training-on-a-8-gb-gpu

* Dreambooth: https://rentry.org/dreambooth-shitguide

* Dreambooth: https://rentry.org/simple-db-elinas

* Dreambooth (Reddit): https://www.reddit.com/r/StableDiffusion/comments/ybxv7h/good_dreambooth_formula/

* Very in depth Hypernetworks guide: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670

* Runpod guide: https://rentry.org/runpod4dumdums

* Small guide written on hypernetwork activation functions.: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-3999660

* Dataset tag manager that can also load loss.: https://github.com/starik222/BooruDatasetTagManager

* Tips on hypernetwork layer structure: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-4010316

* Prompt template + info: https://github.com/victorchall/EveryDream-trainer

	* by anon: allows you to train multiple subjects quickly via labelling file names but it requires a normalization training set of random labelled images in order to preserve model integrity

* github + some documentation: https://github.com/cafeai/stable-textual-inversion-cafe

* Documentation: https://www.reddit.com/r/StableDiffusion/comments/wvzr7s/tutorial_fine_tuning_stable_diffusion_using_only/

* Guide on dreambooth training in comments: https://www.reddit.com/r/StableDiffusion/comments/yo05gy/cyberpunk_character_concepts/

* Dreambooth on 12gb no WSL: https://gist.github.com/geocine/e51fcc8511c91e4e3b257a0ebee938d0

* Very good beginner Twitter tutorial (read replies): https://twitter.com/divamgupta/status/1587452063721693185

* Japanese finetuning guide (?): https://note.com/kohya_ss/n/nbf7ce8d80f29

* Guide: https://github.com/nitrosocke/dreambooth-training-guide

* TI Guide: https://bennycheung.github.io/stable-diffusion-training-for-embeddings

* Faunanon guide: https://files.catbox.moe/vv8gwa.png

* Discussion about editing the training scripts for Hypernetworks: https://archived.moe/h/thread/6984678/#6984825

* Good training info: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2670#discussioncomment-4022968

* TI Tutorial: https://lambdalabs.com/blog/how-to-fine-tune-stable-diffusion-how-we-made-the-text-to-pokemon-model-at-lambda

* Dreambooth info by Huggingface: https://huggingface.co/blog/dreambooth

* Dreambooth on 3080Ti 12g: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/4436

Train stable diffusion model with Diffusers, Hivemind and Pytorch Lightning: https://github.com/Mikubill/naifu-diffusion

Official pytoch implementation of one shot text to image generation via contrastive prompt-tuning AKA 1 image embedding training: https://github.com/7eu7d7/DreamArtist-stable-diffusion  
Extension: https://github.com/7eu7d7/DreamArtist-sd-webui-extension  
DreamArtist extension changes ui.py code in the modules directory, which might not be safe

* Site where you can train: https://www.astria.ai/

* Colab: https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb

* Colab 2: https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb

* Colab 3: https://github.com/XavierXiao/Dreambooth-Stable-Diffusion

* Colab 4 (fast): https://github.com/TheLastBen/fast-stable-diffusion

* colab 5: https://colab.research.google.com/drive/1Iy-xW9t1-OQWhb0hNxueGij8phCyluOh

* site?: drawanyone.com

* Colab for TI: https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb#scrollTo=Yl3r7A_3ASxm

Dreambooth colab with custom model (old, so might be outdated): https://desuarchive.org/g/thread/89140837/#89140895

Dreambooth thing in Japanese: https://note.com/kohya_ss/n/nee3ed1649fb6

* "Has aspect ratio bucketing, saving in fp16, etc."

GPU seems to determine training results (--low/med vram arg too)

Extension: https://github.com/d8ahazard/sd_dreambooth_extension

* Based on https://github.com/ShivamShrirao/diffusers/tree/main/examples/dreambooth

* Original dreambooth: https://github.com/JoePenna/Dreambooth-Stable-Diffusion

* Dreambooth gui: https://github.com/smy20011/dreambooth-gui

	* the app automatically chooses the best settings for your current VRAM

* **GUI helper for manual tagging and cropping: https://github.com/arenatemp/sd-tagging-helper/**

* Waifu Diffusion 1.4 Tagger (you can use to tag datasets):  
https://github.com/toriato/stable-diffusion-webui-wd14-tagger  
https://mega.nz/file/ptA2jSSB#G4INKHQG2x2pGAVQBn-yd_U5dMgevGF8YYM9CR_R1SY

Image tagger helper: https://github.com/nub2927/image_tagger/

- subject filewords: https://pastebin.com/XRFhwXj8
- subject filewords but less emphasis on filewords: https://pastebin.com/LxZGkzj1
- subject filewords v3: https://pastebin.com/hL4nzEDW
- Character training text template: https://files.catbox.moe/wbat5x.txt

* Training on multiple people at once comparison: https://www.reddit.com/r/StableDiffusion/comments/yjd5y5/more_dreambooth_experiments_training_on_several/

* Extract keyframes from a video to use for training: https://github.com/Maurdekye/training-picker

* Huge collection of regularization images: https://huggingface.co/datasets/ProGamerGov/StableDiffusion-v1-5-Regularization-Images

* Embed vector, clip skip, and vae comparison: https://desuarchive.org/g/thread/89392239#89392432

* Hypernet comparison discussion: https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2284

* Comparison of linear vs relu activation function on a number of different prompts, 12K steps at 5e-6.

	* https://files.catbox.moe/q8h8o3.png

* Clip skip comparison: https://files.catbox.moe/f94fhe.jpg

* Hypernetwork comparison: https://files.catbox.moe/q8h8o3.png

anything.ckpt comparisons  
Old final-pruned: https://files.catbox.moe/i2zu0b.png (embed)  
v3-pruned-fp16: https://files.catbox.moe/k1tvgy.png (embed)  
v3-pruned-fp32: https://files.catbox.moe/cfmpu3.png (embed)  
v3 full or whatever: https://files.catbox.moe/t9jn7y.png (embed)

* VAE: https://huggingface.co/stabilityai

* Image Scraper: https://github.com/mikf/gallery-dl

* Img scraper 2: https://github.com/Bionus/imgbrd-grabber

* image scaper 3: 

	``` python
	You can batch download image (+tags) using imgbrd-grabber
	
	1. Go to tools->Option then go to save->"separate log files"
	2. add a separate log file (same settings as pic related)
	3. download your image (don't forget to set a new destination folder for each dataset) and for each image it will create a text file in the same format as deepdanbooru caption
	
	For some reason Grabber always add image file extension (like .jpg and .png) to caption name and you need to remove them.
	You can use rename (from util-linux) to remove them form all caption files like this:
	
	`rename .png.txt .txt *.txt`
	
	
	`rename .jpg.txt .txt *.txt`
	
	don't forget to use the [filewords] template during training
	```

* Bulk resizer: https://www.birme.net/?target_width=512&target_height=512

* Model merging math: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commit/c250cb289c97fe303cef69064bf45899406f6a40#comments

* Old model merging: https://github.com/eyriewow/merge-models/

* Can use ckpt_merge script from https://github.com/bmaltais/dehydrate

	* python3 merge.py <path to model 1> <path to model2> --alpha <value between 0.0 and 1.0> --output <output filename>  
From anon: For sigmoid/inverse sigmoid interpolation between modesl, add this code starting with line 38 of merge.py:

``` python
for key in tqdm(theta_0.keys(), desc="Stage 1/2"):
    if "model" in key and key in theta_1:
        # sigmoid
        alpha = alpha * alpha * (3 - (2 * alpha))
        theta_0[key] = theta_0[key] + ((theta_1[key] - theta_0[key]) * alpha)

        # inverse sigmoid
        #alpha = 0.5 - math.sin(math.asin(1.0 - 2.0 * alpha) / 3.0)
        #theta_0[key] = theta_0[key] + ((theta_1[key] - theta_0[key]) * alpha)

        # Weighted sum
        #theta_0[key] = ((1 - alpha) * theta_0[key]) + (alpha * theta_1[key])
```

* Model merge guide: https://rentry.org/lftbl

	* anon: The Checkpoint Merger tab in webui works well. It uses standard RAM not VRAM. As a general guide, you need 2x as much RAM as the total combined size of the models you need to load. 

* Supposedly empty ckpt to help with memory issues, might be pickled: https://easyupload.io/ggfxvc

* batch checkpoint merger: https://github.com/lodimasq/batch-checkpoint-merger

Supposedly how to append model data without merging by anon:

> x = (Final Dreambooth Model) - (Original Model)  
> filter x for x > = (Some Threshold)  
> out = (Model You Want To Merge It With) * (1 - M) + x * M

Model merging method that preserves weights: https://github.com/samuela/git-re-basin

Alternate model merging using https://github.com/bmaltais/dehydrate by anon:

> Dehydrate a model  
> Hydrate it back into a dreambooth  
> Merge with other stuff  
> run `python ckpt_subtract.py dreamboothmodel.ckpt basemode.ckpt --output dreambooth_only` to dehydrate  
> run 'python ckpt_add.py dreambooth_only target_model.ckpt --output output_model.ckpt' to hydrate it into another model.

3rd party git re basin:  
https://github.com/ogkalu2/Merge-Stable-Diffusion-models-without-distortion

Git rebasin pytorch: https://github.com/themrzmaster/git-re-basin-pytorch

* Aesthetic Gradients: https://github.com/AUTOMATIC1111/stable-diffusion-webui-aesthetic-gradients

* Image aesthetic rating (?): https://github.com/waifu-diffusion/aesthetic

* 1 img TI: https://huggingface.co/lambdalabs/sd-image-variations-diffusers

* You can set a learning rate of "0.1:500, 0.01:1000, 0.001:10000" in textual inversion and it will follow the schedule

* Tip: combining natural language sentences and tags can create a better training

* Dreambooth on 2080ti 11GB (anon's guide): https://rentry.org/tfp6h

* Training a TI on 6gb (not sure if safe or even works, instructions by uploader anon): https://pastebin.com/iFwvy5Gy

	* Have xformers enabled.

	> This diff does 2 things.
	> 1. enables cross attention optimizations during TI training. Voldy disabled the optimizations during training because he said it gave him bad results. However, if you use the InvokeAI optimization or xformers after the xformers fix it does not give you bad results anymore.  
	> This saves around 1.5GB vram with xformers
>
	>2. unloads vae from VRAM during training. This is done in hypernetworks, and idk why it wasn't in the code for TI. It doesn't break anything and doesn't make anything worse.
	>This saves around .2 GB VRAM
	>
	>After you apply this, turn on Move VAE and CLIP to RAM and Use cross attention optimizations while training

* By anon: 

> No idea if someone else will have a use for this but I needed to make it for myself since I can't get a hypernetwork trained regardless of what I do.
> 
> https://mega.nz/file/LDwi1bab#xrGkqJ9m-IsqsTQNixVkeWrGw2HvmAr_fx9FxNhrrbY
> 
> That link above is a spreadsheet where you paste the hypernetwork_loss.csv data into A1 cell (A2 is where numbers should start). Then you can use M1 to set how many epochs of the most recent data you want to use for the red trendline (green is the same length but starting before red). Outlayer % is if you want to filter out extreme points 100% means all points are considered for trendline 95% filters out top and bottom 5 etc. Basically you can use this to see where the training started fucking up. 

* Anon's best: 

> Creation:  
> 1,2,1  
> Normalized Layers  
> Dropout Enabled  
> Swish  
> XavierNormal (Not sure yet on this one. Normal or XavierUniform might be better)

Training:

> Rate: 5e-5:1000, 5e-6:5000, 5e-7:20000, 5e-8:100000  
> Max Steps: 100,000

* Anon's Guide: https://rentry.org/zcspm

Vector guide by anon: https://rentry.org/dah4f

* Another training guide: https://www.reddit.com/r/stablediffusion/comments/y91luo

* Super simple embed guide by anon: Grab the high quality images, run them through the processor. Create an embedding called `art by {artist}. Then train that same embedding with your processed images and set the learning rate to the following: `0.1:500,0.05:1000,0.025:1500,0.001:2000,1e-5` Run it for 10k steps and you'll be good. No need for an entire hypernetwork.

* Has training info and a tutorial for Asagi Igawa, Edjit, and Rouge the Bat embeds (RealYiffingFar#4510): https://mega.nz/folder/5nIAnJaA#YMClwO8r7tR1zdJJeTfegA

* Anon's dreambooth guide:  
for a character, steps ~1500-2000  
checkpoint every 500 if you have the VRAM for it, else 99999 (ie: at the end), previews are shit don't even bother, 99999  
learning rate: 0.000001-0.000005, I don't have a reason for it, default is probably fine.  
instance prompt: [filewords], class prompt: 1girl, 20x regularisation images than training images, style matters, if you want anime get anime regularisation stuff.  
advanced: auto-adjust, batch size: 2, 8bit adam, fp16, don't cache latents (noticeable speedup if you do cache), train text, train EMA, gradient checkpointing, 2 gradient accumulation

none of this is concrete stuff I do every time, I just roll whatever works. the single most important stuff is to ensure you never tag anything that isn't in an image after cropping.  
reduce the tags as much as humanly possible, ie:

legwear, black thighhighs, long socks, long thighhighs, pantyhose, stockings, etc.

to just:

thighhighs

try add images that both do and do not use all of your tags. if you have a pic with thighhighs, include at least one without, otherwise the tag is meaningless  
if your training cannot establish a positive and negative for each tag it's gonna struggle to recall those features  
have makima with yellow eyes? include some girl with similar features but red or blue eyes, or just an entirely different girl that's been accurately tagged with the negatives you need  
in this way you can distinguish between features and emphasise stuff.

### Datasets

* ie_(raarami): https://mega.nz/folder/4GkVQCpL#Bg0wAxqXtHThtNDaz2c90w

	* Expanded (DEAD LINK): https://litter.catbox.moe/j4mpde.zip

* Toplessness: https://litter.catbox.moe/mttar5.zip

* Reine: https://files.catbox.moe/zv6n6q.zip

* Power: https://files.catbox.moe/wcpcbu.7z

* Baffu: https://files.catbox.moe/ejh5sg.7z

* tatsuki fujimoto: https://litter.catbox.moe/k09588.zip

* Butcha-U and Hypnosis: https://files.catbox.moe/9dv0cy.7z

* (By midnanon) tagged data sets with minimal effort and you're comfortable with C# (not sure if safe): https://pastebin.com/JmZFWCUK

	* Take whatever that produces and throw it into a duplicate detector.

	* Take whatever remains, filter out stuff you don't like or otherwise deviates too much.

	* I built up the midna dataset in about 10 minutes or so end to end.

	* You can customise tags on line 248.

* Anya: https://litter.catbox.moe/o5efml.zip

* Amelia Watson: https://files.catbox.moe/vrr2sl.zip

* Henreader (NSFW + loli): https://files.catbox.moe/e0e3nk.7z

* olga discordia from kuroinu: https://www.dropbox.com/s/wir30k9oj3uvnay/process%202.rar?dl=0

* Olga (another?): https://tstorage.info/a70vikp8waeg

* LeMat and Radom (guns): https://files.catbox.moe/zen22z.zip

* AK and SCAR (gun families): https://files.catbox.moe/7vo31t.zip

* Alkemanubis, Siina You Honzuki, Tatata: https://mega.nz/folder/sTV0EI6b#hGotLRXpotvmYxqfTb_KMw

* Onono imoko (NSFW + SFW, 300 cropped images): https://files.catbox.moe/dkn85w.zip

* Moona: https://files.catbox.moe/mmrf0v.rar

* Au'ra, a playable race from Final Fantasy (~100 imgs): https://mega.nz/folder/ZWcXCYpB#Zo-dHbp_u30iIz-LxLUGyA

Training dataset with aesthetic ratings: https://github.com/JD-P/simulacra-aesthetic-captions

## Alternatives

### Browser

**I want to run this, but my computer is too bad. Is there any other way?**  
Check out one of these (I did not use most of these, so I can't attest to their safety):

* (used and safe) Free online browser SD: https://huggingface.co/spaces/stabilityai/stable-diffusion

* https://promptart.labml.ai/playground

* https://novelai.manana.kr/

* https://boards.4channel.org/g/thread/89199040

* https://www.mage.space/

* (used and safe) https://github.com/TheLastBen/fast-stable-diffusion

	* https://colab.research.google.com/github/TheLastBen/fast-stable-diffusion/blob/main/fast_stable_diffusion_AUTOMATIC1111.ipynb

* (used and safe) https://github.com/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb

* visualise.ai

	* Account required

	* Free unlimited 512x512/64 step runs

* img2img with stable horde (good): https://tinybots.net/artbot

- alternative to above (good): https://aqualxx.github.io/stable-ui/

* Free, GPU-less, powered by Stable Horde: https://dbzer0.itch.io/lucid-creations

* Free crowdsourced distributed cluster for Stable Diffusion (not sure how safe this is because of p2p): https://stablehorde.net/

* https://creator.nightcafe.studio/

* Artificy.com

* https://www.craiyon.com/

	* DALL·E mini

* http://aiart.house

* HF demo list: https://pastebin.com/9X1BPf8S

* Automatic1111 webui on SageMaker Studio Lab (free): https://github.com/Miraculix200/StableDiffusionUI_SageMakerSL/blob/main/StableDiffusionUI_SageMakerSL.ipynb

* notebook for running Dreambooth on SageMaker Studio Lab: https://github.com/Miraculix200/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion_SageMakerSL.ipynb

* anything.ckpt: https://colab.research.google.com/drive/1CkIPJrtXa3hlRsVk4NgpM637gmE3Ly5v

* Google Colab webui with 1.5/1.5 inpainting/VAE/waifu division (?): https://colab.research.google.com/drive/1VYmKX7eayuI8iTaCFKVHw9uxSkLo8Mde

* Site (didn't test): https://ai-images.net/

* SD 1.5: https://colab.research.google.com/drive/1kw3egmSn-KgWsikYvOMjJkVDsPLjEMzl

* https://dreamlike.art/

* https://pixelz.ai/

* Anything v3 + Gigachad models + a lot of other models + simple sd webui launcher that doesn't require an account/tokens: https://colab.research.google.com/github/Miraculix200/StableDiffusionUI_Colab/blob/main/StableDiffusionUI_Colab.ipynb#scrollTo=R-xAdMA5wxXd

* Paperspace (has a free plan): https://www.paperspace.com/pricing

* Old WD demo model: https://huggingface.co/spaces/hakurei/waifu-diffusion-demo

* Site, needs account, not free forever: https://getimg.ai/

* Deforum: https://colab.research.google.com/github/deforum-art/deforum-stable-diffusion/blob/main/Deforum_Stable_Diffusion.ipynb

- https://stadio.ai/

* Some gpu rental sites:

	* has free plan: https://colab.research.google.com/

	* https://vast.ai/

	* https://www.runpod.io/

## FAQ

Check out https://rentry.org/sdupdates and https://rentry.org/sdupdates2 for other questions  
https://rentry.org/sdg_FAQ

**What's all the new stuff?**

> Check here to see if your question is answered: 

* https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki

* https://www.reddit.com/r/StableDiffusion

* https://github.com/AUTOMATIC1111/stable-diffusion-webui/search

**What's the "Hello Asuka" test?**

> It's a flawed test to see if you're able to get a 1:1 recreation with NAI and have everything set up properly. Coined after asuka anon and his efforts to recreate 1:1 NAI before all the updates. Deviations arise with certain systems.

> Refer to
> * https://github.com/AUTOMATIC1111/stable-diffusion-webui/discussions/2017
> * Very easy Asuka 1:1 Euler A: https://boards.4chan.org/h/thread/6893903#p6894236
> 	

**What is pickling/getting pickled?**

> ckpt files and python files can execute code. Getting pickled is when these files execute malicious code that infect your computer with malware. It's a memey/funny way of saying you got hacked.

* Automatic1111's webui should unpickle the files for you, but that is only 1 line of defense: https://github.com/AUTOMATIC1111/stable-diffusion-webui/search?q=pickle&type=commits

* anon: there are checks but they can be disabled and you can still bypass with nested things

* https://docs.python.org/3/library/pickle.html, https://huggingface.co/docs/hub/security-pickle

* Pickle toolkit to extract the pickle information: https://docs.python.org/3/library/pickletools.html

* anon:  
	pickle is a format that can load code objects  
	originally the objects weren't sanitized, so remote code could run

	> by implementing **reduce** in a class which instances we are going to pickle, we can give the pickling process a callable plus some arguments to run  
	now **reduce** is restricted (anything not NN related), the joke lives on as a meme

**How do I directly check AUTOMATIC1111's webui updates?**

> For a complete list of updates, go here: https://github.com/AUTOMATIC1111/stable-diffusion-webui/commits/master

**What do I do if a new updates bricks/breaks my AUTOMATIC1111 webui installation?**

> Go to https://github.com/AUTOMATIC1111/stable-diffusion-webui/commits/master  
> See when the change happened that broke your install  
> Get the blue number on the right before the change  
> Open a command line/git bash to where you usually git pull (the root of your install)  
> 'git checkout <blue number without these angled brackets>'  
> to reset your install, use 'git checkout master'

> `git checkout .` will clean any changes you do

> Another Guide: https://rentry.org/git_retard

**What is…? (by anon)**

> What is a VAE?  
Variational autoencoder, basically a "compressor" that can turn images into a smaller representation and then "decompress" them back to their original size. This is needed so you don't need tons of VRAM and processing power since the "diffusion" part is done in the smaller representation (I think). The newer SD 1.5 VAEs have been trained more and they can recreate some smaller details better.  
> What is pruning?  
Removing unnecessary data (anything that isn't needed for image generation) from the model so that it takes less disk space and fits more easily into your VRAM  
> What is a pickle, not referring to the python file format? What is the meme surrounding this?  
When the NAI model leaked people were scared that it might contain malicious code that could be executed when the model is loaded. People started making pickle memes because of the file format.  
> Why is some stuff tagged as being 'dangerous', and why does the StableDiffusion WebUI have a 'safe-unpickle' flag? -- I'm stuck on pytorch 1.11 so I have to disable this  
Safe unpickling checks the pickle's code library imports against an approved list. If it tried to import something that isn't on the list it won't load it. This doesn't necessarily mean it's dangerous but you should be cautious. Some stuff might be able to slip through and execute arbitrary code on your computer.  
> Is the rentry stuff all written by one person or many?  
There are many people maintaining different rentries.

**What's the difference between embeds, hypernetworks, and dreambooths? What should I train?**  
Anon:

> I've tested a lot of the model modifications and here are my thoughts on them:  
> embeds: these are tiny files which find the best representation of whatever you're training them on in the base model. By far the most flexible option and will have very good results if the goal is to group or emphasize things the model already understands  
> hypernetworks: there are like instructions that slightly modify the result of the base model after each sampling step. They are quite powerful and work decently for everything I've tried (subjects, styles, compositions). The cons are they can't be easily combined like embeds. They are also harder to train because good parameters seem to vary wildly so a lot of experimentation is needed each time  
> dreambooth: modifies part of the model itself and is the only method which actually teaches it something new. Fast and accurate results but the weights for generating adjacent stuff will get trashed. These are gigantic and have the same cons as embeds

## Misc

Links: https://rentry.org/sdg-link  
https://catbox.moe/

## Archives

[SDupdates 1](https://rentry.org/sdupdates) for v1 of sdupdates  
[SDupdates 2](https://rentry.org/sdupdates2) for v2 of sdupdates  
[SDump 1](https://rentry.org/sdump1) for stuff that's unsorted and/or I have no idea where to sort them  
[Soutdated 1](https://rentry.org/soutdated1) for stuff that's outdated
