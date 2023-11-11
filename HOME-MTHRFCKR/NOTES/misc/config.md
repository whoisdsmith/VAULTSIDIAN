title: devlopr  
subtitle: A Portfolio Jekyll Theme Built for Developers  
description: >- # this means to ignore newlines until "baseurl:"  
  devlopr-jekyll is a beautiful Jekyll Theme Built For Developers, which is optimized for speed and readability.

url: "" # the base hostname & protocol for your site, e.g. <https://example.github.io>  
baseurl: "" # the subpath of your site, e.g. /blog

# Navigation

urls:  
    - text: Home  
      url: /  
    - text: About  
      url: /about  
    - text: Blog  
      url: /blog  
    - text: Gallery  
      url: /gallery  
    - text: Shop  
      url : /shop  
    - text: Contact  
      url : /contact

# Edit Author Details (For Multi Authors Check _data/authors.yml)

author_logo: Profile.PNG  
author: Dustin Smith  
author_bio: I spend most of my time trying to learn shit I'll never understand.  
author_email: "whoisdsmith@gmail.com"  
author_website_url: "https://whoisdsmith.github.io"  
typewrite-text: I dont know have a clue what im doing, but im doing it anyways  
hero_cover_img:

# Experiences

author_work_experiences:  
            - company_name:  
              company_logo:  
              company_url:  
              designation:  
              description:  
              visibility: false  
            - company_name:  
              company_logo:  
              company_url:  
              designation:  
              description:  
              visibility: false

# Education

author_education_details:  
              - college_logo:  
                college_url:  
                college_degree:  
                description:  
                visibility: false

# Projects

author_project_details:  
              - project_thumbnail:  
                project_title:  
                project_description:  
                project_url:  
                visibility: false  
              - project_thumbnail:  
                project_title:  
                project_description:  
                project_url:  
                visibility: false

# Social Links

twitter_username: wh0isdsmith  
github_username: whoisdsmith  
facebook_username: dontcallmedsmith  
instagram_username: dsmith4life

# For Comments ( We Got Disqus and Hyvor Commenting, Uncomment the One You want to Use )

# For Comments ( We Got Disqus and Hyvor Commenting, Uncomment the One You want to Use )

# Wakatime Username (coding activity)

# wakatime_username: Whoisdsmith

# Mailchimp Embedded Form Url (newsletter)

# mailchimp_form_url

# Contact Form - (choose Formspress or getform)

# getform_endpoint: 83b703c3-9e47-4df4-ac55-e24d7eb02abc

# formspree_email

# Releases - Widget Can Be (sidebar, Modal or embed)

# olvy_organization

# olvy_widget_type

# Syntax Highlighter

markdown:  
highlighter:  
permalink:

# Choose what to Show ( Can Be True or false)

show_author_work_experiences: false  
show_author_education_details: false  
show_author_project_details: false

# Pagination of Posts

paginate: 4  
per_page: 4  
paginate_path: "/blog/page/:num/"

# Minify

# compress_html

# Clippings: All

# Comments: ["<!-- ", " -->"]

# Endings: All

# Ignore

# Envs: ['development']

# Archives

# Jekyll-archives

# Enabled

# - Categories

# Layout: Archive

# Permalinks

# Category: '/category/:name/'

collections:  
  products:  
    output: false  
  authors:  
    output: false

defaults
  -

    scope:
      path: "gallery"
    values:
      permalink: /:path/:basename:output_ext

-  
    scope:  
      path: ""  
      type: authors  
    values:  
      layout: author  
      permalink: /blog/authors/:slug

# Build Settings

plugins:

- jekyll-paginate
- jekyll-gist
- jekyll-seo-tag
- jekyll-sitemap
- jekyll-admin

# Jekyll Admin Config

jekyll_admin:

# hidden_links

# - Posts

# - Pages

# - Staticfiles

# - Datafiles

# - Configuration

  homepage: "posts"

# Exclude from Processing

# The following Items Will not Be Processed, by Default

# Any Item Listed under the `exclude:` Key here Will Be Automatically Added to

# The Internal "default list"

#


# Excluded Items Can Be Processed by Explicitly Listing the Directories or

# Their Entries' File Path in the `include:` List

## Switching Deployment Strategy (in DEPLOY_STRATEGY) File Change the Key Accordingly

# None - For no Default

# Gh-pages - For Github Pages

# Firebase - For Firebase Hosting

exclude:

- .sass-cache/
- .jekyll-cache/
- gemfiles/
- Gemfile
- Gemfile.lock
- node_modules/
- vendor/bundle/
- vendor/cache/
- vendor/gems/
- vendor/ruby/

destination: ./build
