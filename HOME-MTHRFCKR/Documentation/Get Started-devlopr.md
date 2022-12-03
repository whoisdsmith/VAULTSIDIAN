## Getting Started - How to use “devlopr-jekyll” theme

## What’s Jekyll ?

If you aren’t familiar with Jekyll yet, you should know that it is a static site generator. It will transform your plain text into static websites and blogs. No more databases, slow loading websites, risk of being hacked…just your content. And not only that, with Jekyll you get free hosting with GitHub Pages! If you are a beginner we recommend you start with [Jekyll’s Docs](https://jekyllrb.com/docs/installation/). Now, if you know how to use Jekyll, let’s move on to using this theme in Jekyll:

## Watch Tutorial

<iframe width="560" height="315" src="https://www.youtube.com/embed/cXBEfpn0qrg?rel=0&amp;controls=0&amp;showinfo=0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen=""></iframe>

### Steps to create your blog using devlopr-jekyll and Host using Github Pages :

> **Step 1.** Fork the repo - [click here](https://github.com/sujaykundu777/devlopr-jekyll/fork)

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/6c58d1c95619c5b27492b29edc67f6b15d313011/0a0d1/assets/img/posts/fork1.png)

> **Step 2.** Use **your-github-username.github.io** as the new repo ( Replace your-github-username with yours). Remember if you use the name other than your-github-username.github.io , your blog will be built using gh-pages branch.

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/2d1270a9d382a0476f0ce10b9905631556720619/d2327/assets/img/posts/fork2.png)

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/c4d95f17eead2fe6b0c2031b6c0298d3277cf674/09cf9/assets/img/posts/fork3.png)

> **Step 3.** Clone the new repo locally to make changes :

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/ec51ae48f858e1512f20d8f292482b26d2f17a02/c00c9/assets/img/posts/fork31.png)

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/dc0ef3e7d1e615d6121fdc9617c1669cbbfa95dd/1bdf3/assets/img/posts/fork32.png)

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/3f85cc1d6f28574da7a2770104dc8325aa30c3f3/65ee1/assets/img/posts/fork33.png)

```
 $ git clone https://github.com/yourusername/yourusername.github.io
 $ cd yourusername.github.io
 $ code .
```

> **Step 4.** Open the files using VSCode and edit \_config.yml and edit with your details:

-   \_config.yml file - replace with your own details
-   \_posts - Add your blog posts here
-   \_includes - You can replace the contents of the files with your data. (contains widgets)
-   \_assets/img - Add all your images here

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/ec506c3b10dac7dd64759dc78eeb9f2c6aa67810/7e73b/assets/img/posts/fork34.png)

> **Step 5** - Install the development requirements:

### Set up local development environment

1.  [Git](https://git-scm.com/)
2.  [Ruby](https://www.ruby-lang.org/) and [Bundler](https://bundler.io/)
3.  [VSCode](https://code.visualstudio.com/download)

We need ruby and bundler to build our site locally. After installation check if its working:

For ruby :

```
$ ruby -v
ruby 2.5.1p57 (2018-03-29 revision 63029) [x86_64-linux-gnu]
```

For bundler :

```
$ gem install bundler
$ bundler -v
Bundler version 2.2.29
```

Add jekyll :

```
$ bundle update
$ bundle add jekyll
```

This command will add the Jekyll gem to our Gemfile and install it to the ./vendor/bundle/ folder.

You can check the jekyll version

```
$ bundle exec jekyll -v
jekyll 4.2.0
```

> **Step 6.** Install the gem dependencies by running the following command

```
$ bundle update
$ bundle install
```

> **Step 7.** Serve the site locally by running the following command below:

```
$ bundle exec jekyll serve --watch
```

or you can also serve using :

Visit [http://localhost:4000](http://localhost:4000/) for development server

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/bd03d616d2b25a54f6b1365900f86c941b7d7158/87139/assets/img/posts/fork41.png)

### Adding Content

Start populating your blog by adding your .md files in \_posts. devlopr-jekyll already has a few examples.

#### YAML Post Example:

```
---
layout: post
title: Sample Post
author: Sujay Kundu
date: '2019-05-21 14:35:23 +0530'
category:
        - jekyll
summary: This is the summary for the sample post
thumbnail: sample.png
---

Hi ! This is sample post.

```

#### YAML Page Example:

```
---
layout: page
title: Sample Page
permalink: /sample-page/
---

Hi ! This is sample page.
```

#### Editing stylesheet

You’ll only work with a single file to edit/add theme style: assets/css/main.scss.

### Deploy your Changes

Once happy with your blog changes. Push your changes to master branch.

> **Step 8.** Push Your Local Changes

```
 $ git add .
 $ git commit -m "my new blog using devlopr-jekyll"
 $ git push origin master
```

Visit your Github Repo settings ! Enable master branch as Github Pages Branch :

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/d614e7554df3b8adec3e4b4d508a3e3b29378485/b3489/assets/img/posts/fork6.png)

> **Step 9.** Deploy your Blog :

![Devlopr Jekyll Repo](https://d33wubrfki0l68.cloudfront.net/9fc8167e2f5820e51a3a69c00f0654e4b8c1dd50/749eb/assets/img/posts/fork7.png)

> Congrats ! On your new shining Blog !

You can visit the blog using [http://your-github-username.github.io](http://your-github-username.github.io/).