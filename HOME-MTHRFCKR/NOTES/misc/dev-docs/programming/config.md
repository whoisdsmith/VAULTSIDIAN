title: devlopr
subtitle: A Portfolio Jekyll Theme Built for Developers
description: >- # this means to ignore newlines until "baseurl:"
  devlopr-jekyll is a beautiful Jekyll Theme Built For Developers, which is optimized for speed and readability.

url: "" # the base hostname & protocol for your site, e.g. https://example.github.io
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


# Edit Author details (For multi authors check _data/authors.yml)

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

# social links
twitter_username: wh0isdsmith
github_username: whoisdsmith
facebook_username: dontcallmedsmith
instagram_username: dsmith4life


#for comments ( we got Disqus and Hyvor Commenting, uncomment the one you want to use )

#for comments ( we got Disqus and Hyvor Commenting, uncomment the one you want to use )

# wakatime username (coding activity)
# wakatime_username: whoisdsmith

# mailchimp embedded form url (newsletter):
# mailchimp_form_url:

# contact form - (choose formspress or getform)
# getform_endpoint: 83b703c3-9e47-4df4-ac55-e24d7eb02abc
#formspree_email:

# releases - widget can be (sidebar, modal or embed)
# olvy_organization:
# olvy_widget_type:

# syntax highlighter
markdown:
highlighter:
permalink:

# Choose what to show ( can be true or false)
show_author_work_experiences: false
show_author_education_details: false
show_author_project_details: false

# pagination of posts
paginate: 4
per_page: 4
paginate_path: "/blog/page/:num/"

# minify
# compress_html:
#   clippings: all
#   comments: ["<!-- ", " -->"]
#   endings: all
#   ignore:
#     envs: ['development']

# Archives
# jekyll-archives:
#   enabled:
#     - categories
#   layout: archive
#   permalinks:
#     category: '/category/:name/'

collections:
  products:
    output: false
  authors:
    output: false

defaults:
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

# Build settings
plugins:
  - jekyll-paginate
  - jekyll-gist
  - jekyll-seo-tag
  - jekyll-sitemap
  - jekyll-admin

# Jekyll Admin Config
jekyll_admin:
  # hidden_links:
  #   - posts
  #   - pages
  #   - staticfiles
  #   - datafiles
  #   - configuration
  homepage: "posts"


# Exclude from processing.
# The following items will not be processed, by default.
# Any item listed under the `exclude:` key here will be automatically added to
# the internal "default list".
#
# Excluded items can be processed by explicitly listing the directories or
# their entries' file path in the `include:` list.

### Switching Deployment Strategy (in DEPLOY_STRATEGY) file change the key accordingly:
# none - For no default
# gh-pages - For Github Pages
# firebase - For Firebase Hosting

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
