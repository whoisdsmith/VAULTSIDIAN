# WordPress

Version Latest

### Note

This is the documentation for the new WordPress app. [Here is the documentation for the legacy WordPress (legacy) app.](https://www.make.com/en/help/apps/website-building/wordpresswordpress--legacy-.html "WordPress (legacy)")

[

## Getting Started with WordPress





](https://www.make.com/en/help/apps/website-building/wordpress#getting-started-with-wordpress-968742_body)

The WordPress modules allow you to monitor, publish, update, delete, or search posts, pages, comments, media, users, and tags on your WordPress site.

Prerequisites

-   WordPress installed on your server or webhosting – you can download WordPress at [wordpress.org/download/](https://wordpress.org/download/) and install by following the instructions on [wordpress.org/support/article/how-to-install-wordpress](https://wordpress.org/support/article/how-to-install-wordpress/).
    
-   [Make Connector](https://wordpress.org/plugins/integromat-connector/) **plugin** – get the plugin at [wordpress.org/plugins/Make\-connector](https://wordpress.org/plugins/integromat-connector/).
    

### Note

The module dialog fields that are displayed in **bold** (in the Make scenario, **not** in this documentation article) are mandatory!

[

## Connecting WordPress to Make





](https://www.make.com/en/help/apps/website-building/wordpress#connecting-wordpress-to-make-968742_body)

To connect your WordPress account to Make, the [Make Connector](https://wordpress.org/plugins/integromat-connector/) plugin has to be installed in your WordPress installation.

1.  Visit [https://wordpress.org/plugins/Make\-connector](https://wordpress.org/plugins/integromat-connector/) and **download** the _Make Connector_ plugin ([direct link](https://downloads.wordpress.org/plugin/integromat-connector.zip)).
    
2.  Log in to your WordPress administration and navigate to _Plugins_.
    
    ![61d6be64a5383.gif](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c0b80cc.gif)
    
3.  Click the _Add New_ button.
    
    ![61d6be66efe5a.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c0e1add.png)
    
4.  Click on the _Upload plugin_ button, _browse_ and select the plugin ZIP file. Click _Install now_ to install the plugin.
    
    ![61d6be686ce59.gif](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c0e763e.gif)
    
5.  After the installation is finished, click on the _Activate Plugin_ button (![61d6be6b2a6b5.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c1144cf.png)).
    
6.  Open Make plugin from the menu on the left and copy the provided API Key.
    
    ![61d6be6c41a28.gif](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c118f8d.gif)
    
7.  Go to Make and open the _Create a connection_ dialog of the desired _WordPress_ module. Enter the _REST API Base URL_ of your WordPress site (for example _https://my-wordpress-site.com**/wp-json**_) and the _API Key_ you have copied in step 6 above to the respective fields.
    
8.  Establish a connection by clicking the _Continue_ button.
    
    ![61d6be6f422be.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c136ed4.png)
    

The connection has been established. You can proceed with setting up the module.

## Custom Fields

1.  To work with object's custom fields you want to include in module's output you need to activate the desired fields in the [MakeConnector](https://wordpress.org/plugins/integromat-connector/) plugin.
    
2.  Install the Make Connector plugin as described in the [Connecting WordPress to](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742 "Connecting WordPress to Make") Make section above.
    
3.  If needed, follow these [instructions](https://www.wpbeginner.com/wp-tutorials/wordpress-custom-fields-101-tips-tricks-and-hacks/) in order to add a custom field to your post, page, media, or another object.
    
4.  Navigate to Make _> Custom API Fields_ settings.
    
    ![61d6be70b20f2.gif](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c13c666.gif)
    
5.  Select the desired object's custom fields you want to include in the module's output.
    
    ![61d6be73ee882.gif](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c176fe2.gif)
    
6.  Click on the _Save Settings_ button.
    
7.  The selected custom fields are now available in the module's output.
    
    ![61d6be773758d.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c19913d.png)
    

## Posts

[

### Watch Posts





](https://www.make.com/en/help/apps/website-building/wordpress#watch-posts-968742_body)

Triggers when a new object is added.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select whether you want to retrieve newly added posts, pages, or other objects.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of objects <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Posts





](https://www.make.com/en/help/apps/website-building/wordpress#search-posts-968742_body)

Searches for a post and returns its details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select the type of post you want to search.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Status</strong></span></p></td><td class="td"><p>Select statuses you want to filter returned posts by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Field</strong></span></p></td><td class="td"><p>Select the fields you want to order returned fields by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Order</strong></span></p></td><td class="td"><p>Select the ascending or descending order of returned results.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of posts <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

For descriptions of fields under _Advanced settings_ please refer to the [WordPress API documentation.](https://developer.wordpress.org/rest-api/reference/categories/#arguments)

[

### Get a Post





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-post-968742_body)

Retrieves post details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select the type of post you want to retrieve details about.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the post you want to retrieve details about.</p></td></tr></tbody></table>

[

### Create a Post





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-post-968742_body)

Creates an object.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Title</strong></span></p></td><td class="td"><p>Set the post's title.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Content</strong></span></p></td><td class="td"><p>Enter the content of the new post. HTML is allowed.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select whether you want to retrieve newly added posts, pages, media, or another object.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Excerpt</strong></span></p></td><td class="td"><p>Enter the excerpt content for the post.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Date</strong></span></p></td><td class="td"><p>Enter the date of the new post. <a class="link" href="https://www.make.com/en/help/apps/website-building/wordpress../../mapping/date-examples.html" title="Examples of date format:">List of supported date formats.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Slug</strong></span></p></td><td class="td"><p>Enter the post's slug (in order to have a more SEO-friendly URL).</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Status</strong></span></p></td><td class="td"><p>Set the status of the new post. If no status is selected the post's status will be set to <span class="emphasis"><em>draft</em></span>.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Format</strong></span></p></td><td class="td"><p>Select one of the formats for the post. For more information about post formats refer to <a class="link" href="https://wordpress.org/support/article/post-formats/#supported-formats" target="_blank" rel="noopener">wordpress.org/support/article/post-formats</a>.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Parent ID Object</strong></span></p></td><td class="td"><p>Enter the ID of the parent object.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Categories</strong></span></p></td><td class="td"><p>Select categories that a new post should belong to.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Tags</strong></span></p></td><td class="td"><p>Select tags you want to add to the new post – The terms assigned to the object in the post_tag taxonomy.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author</strong></span></p></td><td class="td"><p>Select the author of the post or enter (map) the ID of the author.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Featured media ID</strong></span></p></td><td class="td"><p>Enter the ID of the media.</p><p>Retrieve the media by following these steps:</p><p>1. Open <span class="emphasis"><em>Media</em></span> settings.</p><p>2. Change the mode to <span class="emphasis"><em>List view.</em></span></p><p><span class="emphasis"><em>3. </em></span>Hover the mouse over the image.</p><p>4. See the media ID in the status bar.</p><div class="mediaobject"><div class="material-placeholder"><img src="https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c19f567.png" style="" alt="61d6be78b3e0f.png" class="materialboxed"></div></div></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Template</strong></span></p></td><td class="td"><p>Enter the name of the template you want to use for this post. For example <code class="code">templates/template-full-width.php</code></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Password</strong></span></p></td><td class="td"><p>Set the password if you want the post <span class="emphasis"><em>password protected</em></span>.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Sticky</strong></span></p></td><td class="td"><p>Set whether or not the object should be treated as <a class="link" href="https://wordpress.org/support/article/sticky-posts/" target="_blank" rel="noopener">sticky</a>.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Comment status</strong></span></p></td><td class="td"><p>Set whether or not comments are open on the post.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Ping status</strong></span></p></td><td class="td"><p>Set whether the post can be pinged.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Additional fields</strong></span></p></td><td class="td"><p>Specify additional fields.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Metadata (custom fields)</strong></span></p></td><td class="td"><p>Specify custom fields.</p><p>This option is available for the following content types:</p><div class="itemizedlist"><ul class="itemizedlist" style="list-style-type: disc; "><li class="listitem"><p>Post</p></li><li class="listitem"><p>Comments</p></li><li class="listitem"><p>Users</p></li><li class="listitem"><p>Terms</p></li></ul></div></td></tr></tbody></table>

[

### Update a Post





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-post-968742_body)

Allows you to modify the existing post.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select the type of post you want to update.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the post you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section [Create a Post](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-post-968742 "Create a Post") above.

[

### Delete a Post





](https://www.make.com/en/help/apps/website-building/wordpress#delete-a-post-968742_body)

Deletes a specified WordPress object (post, page, media, product, ...)

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the object you want to delete.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Type</strong></span></p></td><td class="td"><p>Select the type of the post you want to delete.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Force</strong></span></p></td><td class="td"><p>Enable this option to delete the post without moving to trash.</p></td></tr></tbody></table>

## Categories

[

### Watch Categories





](https://www.make.com/en/help/apps/website-building/wordpress#watch-categories-968742_body)

Triggers when a new category is created.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of categories <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Categories





](https://www.make.com/en/help/apps/website-building/wordpress#search-categories_body)

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Parent Category</strong></span></p></td><td class="td"><p>Select the category to filter results by its subcategories.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post Type</strong></span></p></td><td class="td"><p>Select the type to filter results by specific post.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post</strong></span></p></td><td class="td"><p>Select the specific post to filter results by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Field</strong></span></p></td><td class="td"><p>Select the fields you want to order returned fields by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Order</strong></span></p></td><td class="td"><p>Select the ascending or descending order of returned results.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of categories <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

For descriptions of fields under _Advanced settings_ please refer to the [WordPress API documentation](https://developer.wordpress.org/rest-api/reference/categories/#arguments).

[

### Get a Category





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-category-968742_body)

Retrieves the category details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Category ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the category you want to retrieve information about.</p></td></tr></tbody></table>

[

### Create a Category





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-category-968742_body)

Adds a new category.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Name</strong></span></p></td><td class="td"><p>Enter the name of the category and how it appears on your site.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Description</strong></span></p></td><td class="td"><p>Enter the text for the description.</p><div dir="ltr" class="note"><h3 class="title">Note</h3><p>The description is not prominent by default; however, some themes may show it.</p></div></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Slug</strong></span></p></td><td class="td"><p>Enter the slug of the category you want to create.</p><div dir="ltr" class="note"><h3 class="title">Note</h3><p>The <span class="emphasis"><em>slug</em></span> is the URL-friendly version of the name. It is usually all lowercase and contains only letters, numbers, and hyphens.</p></div></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Parent category ID</strong></span></p></td><td class="td"><p>Enter the ID of the parent category in the case where you want to create a child category.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Metadata (custom fields)</strong></span></p></td><td class="td"><p>Specify custom fields.</p></td></tr></tbody></table>

[

### Update a Category





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-category-968742_body)

Modifies an existing category.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Category ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the category you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section [Create a Category](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-category-968742 "Create a Category") above.

[

### Delete a Category





](https://www.make.com/en/help/apps/website-building/wordpress#delete-a-category-968742_body)

Deletes a specified category.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Category ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the category you want to delete.</p></td></tr></tbody></table>

## Comments

[

### Watch Comments





](https://www.make.com/en/help/apps/website-building/wordpress#watch-comments-968742_body)

Triggers when a new comment is posted.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of comments <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Comments





](https://www.make.com/en/help/apps/website-building/wordpress#search-comments-968742_body)

Searches for the comment and returns its details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Parent Comment</strong></span></p></td><td class="td"><p>Select the comment to filter results by its sub-comments.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Status</strong></span></p></td><td class="td"><p>Select the status to filter returned results by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post Type</strong></span></p></td><td class="td"><p>Select the type to filter results by specific post.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post</strong></span></p></td><td class="td"><p>Select the specific post to filter results by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Field</strong></span></p></td><td class="td"><p>Select the fields you want to order returned fields by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Order</strong></span></p></td><td class="td"><p>Select the ascending or descending order of returned results.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of comments <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

For descriptions of fields under _Advanced settings_ please refer to the [WordPress API documentation.](https://developer.wordpress.org/rest-api/reference/categories/#arguments)

[

### Get a Comment





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-comment-968742_body)

Retrieves details of a specified comment.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Comment ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the comment you want to retrieve information about.</p></td></tr></tbody></table>

[

### Create a Comment





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-comment-968742_body)

Creates a comment.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the post you want to create a comment for.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Content</strong></span></p></td><td class="td"><p>Enter the text content of the comment.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Status</strong></span></p></td><td class="td"><p>Set the status of the new comment.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author name</strong></span></p></td><td class="td"><p>Enter a display name for the comment author.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author ID</strong></span></p></td><td class="td"><p>Enter the ID of the user if the author of the comment is the user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author email</strong></span></p></td><td class="td"><p>Enter the email address for the comment author.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author IP</strong></span></p></td><td class="td"><p>Set the comment author IP address.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author URL</strong></span></p></td><td class="td"><p>Enter the URL for the author of the comment.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Author User-Agent</strong></span></p></td><td class="td"><p>Enter the author User-Agent. E.g. <span class="emphasis"><em>Mozilla/5.0 (Windows NT 10.0; Win64; x64; rv:67.0) Gecko/20100101 Firefox/67.0</em></span></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Parent object ID</strong></span></p></td><td class="td"><p>Enter the ID of the parent object.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Metadata (custom fields)</strong></span></p></td><td class="td"><p>Add custom fields to the comment.</p></td></tr></tbody></table>

[

### Update a Comment





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-comment-968742_body)

Allows you to modify an existing comment.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Comment ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the comment you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section [Create a Comment](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-comment-968742 "Create a Comment") above.

[

### Delete a Comment





](https://www.make.com/en/help/apps/website-building/wordpress#delete-a-comment-968742_body)

Deletes a specified comment.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Comment ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the comment you want to delete.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Force</strong></span></p></td><td class="td"><p>Enable this option to delete the comment without moving it to the trash.</p></td></tr></tbody></table>

## Media

[

### Watch Media Items





](https://www.make.com/en/help/apps/website-building/wordpress#watch-media-items-968742_body)

Triggers when new media is added to the library.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of media items <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Media Items





](https://www.make.com/en/help/apps/website-building/wordpress#search-media-items_body)

Searches for media items.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search term</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Media Type</strong></span></p></td><td class="td"><p>Select the type of media you want to filter the search results by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Status</strong></span></p></td><td class="td"><p>Select the status to filter returned results by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Field</strong></span></p></td><td class="td"><p>Select the fields you want to order returned fields by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Order</strong></span></p></td><td class="td"><p>Select the ascending or descending order of returned results.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of comments <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

For descriptions of fields under _Advanced settings_ please refer to the [WordPress API documentation.](https://developer.wordpress.org/rest-api/reference/categories/#arguments)

[

### Get a Media Item





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-media-item-968742_body)

Retrieves the details for a specified media item.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Media item ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the media item you want to retrieve information about.</p></td></tr></tbody></table>

[

### Create a Media Item





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-media-item-968742_body)

Creates a media item.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Source file</strong></span></p></td><td class="td"><p>Map the file you want to upload from the previous module (e.g. HTTP &gt; Get a File or Google Drive &gt; Download a File), or enter the file name and file data manually.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Title</strong></span></p></td><td class="td"><p>Enter the media title.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Alternative text</strong></span></p></td><td class="td"><p>Enter alt text to display when media is not displayed.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Caption</strong></span></p></td><td class="td"><p>Enter the attachment caption.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Description</strong></span></p></td><td class="td"><p>Enter the description of the media.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Enter the ID of the associated post of the media attachment. Will be set as featured image of the specified post.</p></td></tr></tbody></table>

[

### Update a Media Item





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-media-item-968742_body)

Allows you to modify an existing media item.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Media item ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the media item you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section [Create a Media Item](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-media-item-968742 "Create a Media Item") above.

[

### Delete Media Item





](https://www.make.com/en/help/apps/website-building/wordpress#delete-media-item-968742_body)

Deletes specified media.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Media Item ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the media item you want to delete.</p></td></tr></tbody></table>

## Users

[

### Watch Users





](https://www.make.com/en/help/apps/website-building/wordpress#watch-users-968742_body)

Triggers when a new user is added.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of users <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Users





](https://www.make.com/en/help/apps/website-building/wordpress#search-users-968742_body)

Searches for the user by the search term.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Roles</strong></span></p></td><td class="td"><p>Select the roles to filter results to users matching at least one specific role provided.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Field</strong></span></p></td><td class="td"><p>Select the fields you want to order returned fields by.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Order</strong></span></p></td><td class="td"><p>Select the ascending or descending order of returned results.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of comments <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Get a User





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-user-968742_body)

Retrieves specified user details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>User ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the user you want to retrieve information about.</p></td></tr></tbody></table>

[

### Create a User





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-user-968742_body)

Creates a new user.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p>Establish a connection to your WordPress.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Username</strong></span></p></td><td class="td"><p>Enter the login user name for the user you want to add.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Password</strong></span></p></td><td class="td"><p>Enter the password for the user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Email address</strong></span></p></td><td class="td"><p>Enter the email address of the new user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Display name</strong></span></p></td><td class="td"><p>Enter the display name for the user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>First name</strong></span></p></td><td class="td"><p>Enter the user's first name.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Last name</strong></span></p></td><td class="td"><p>Enter the user's last name.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Description</strong></span></p></td><td class="td"><p>Enter the description for the user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Locale</strong></span></p></td><td class="td"><p>Set the user's locale. E.g. <code class="code">en_US</code>.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Nickname</strong></span></p></td><td class="td"><p>Enter the user's nickname.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>URL</strong></span></p></td><td class="td"><p>Enter the user's website.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Slug</strong></span></p></td><td class="td"><p>Enter the alphanumeric identifier for the user.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Roles</strong></span></p></td><td class="td"><p>Select the roles you want to assign the user to.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Metadata (custom fields)</strong></span></p></td><td class="td"><p>Add desired custom fields.</p></td></tr></tbody></table>

[

### Update a User





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-user-968742_body)

Allows you to modify existing user information.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>User ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the user you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section, [Create a User](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-user-968742 "Create a User") above.

[

### Delete a User





](https://www.make.com/en/help/apps/website-building/wordpress#delete-a-user-968742_body)

Deletes a specified user.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>User ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the user you want to delete.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Reassign posts and links to user ID</strong></span></p></td><td class="td"><p>Enter the user ID of another user to reassign the deleted user's posts and link it to this user ID.</p></td></tr></tbody></table>

## Tags

[

### Watch Tags





](https://www.make.com/en/help/apps/website-building/wordpress#watch-tags-968742_body)

Triggers when a new tag is added.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of tags <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Search Tags





](https://www.make.com/en/help/apps/website-building/wordpress#search-tags_body)

Searches for tags.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Search</strong></span></p></td><td class="td"><p>Enter the search term.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post ID</strong></span></p></td><td class="td"><p>Select the post to filter results by tags assigned to the specified post.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of tags <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>

[

### Get a Tag





](https://www.make.com/en/help/apps/website-building/wordpress#get-a-tag-968742_body)

Retrieves specified tag details.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Tag ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the tag you want to retrieve information about.</p></td></tr></tbody></table>

[

### Create a Tag





](https://www.make.com/en/help/apps/website-building/wordpress#create-a-tag-968742_body)

Creates a new tag.

<table class="informaltable frame-void rules-rows"><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Name</strong></span></p></td><td class="td"><p>Enter the name of the tag how it appears on your site.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Description</strong></span></p></td><td class="td"><p>Enter the tag description. The description is not prominent by default; however, some themes may show it.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Slug</strong></span></p></td><td class="td"><p>Enter the slug for the tag. The slug is the URL-friendly version of the name. It is usually all lowercase and contains only letters, numbers, and hyphens.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Metadata (custom fields)</strong></span></p></td><td class="td"><p>Add desired custom fields.</p></td></tr></tbody></table>

[

### Update a Tag





](https://www.make.com/en/help/apps/website-building/wordpress#update-a-tag-968742_body)

Allows you to modify an existing tag.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Tag ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the tag you want to update.</p></td></tr></tbody></table>

Please find the descriptions of the fields in the section, [Create a Tag](https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#create-a-tag-968742 "Create a Tag") above.

[

### Delete a Tag





](https://www.make.com/en/help/apps/website-building/wordpress#delete-a-tag-968742_body)

Deletes a specified tag.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Tag ID</strong></span></p></td><td class="td"><p>Enter (map) the ID of the tag you want to delete.</p></td></tr></tbody></table>

## Make an API Call

Allows you to perform a custom API call.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>URL</strong></span></p></td><td class="td"><p>Enter a path relative to <code class="code">https://{DOMAIN}/wp-json/wp/v2/</code>. E.g. <code class="code">posts/1</code></p><div dir="ltr" class="note"><h3 class="title">Note</h3><p>For the list of available endpoints, refer to the <a class="link" href="https://developer.wordpress.org/rest-api/reference/" target="_blank" rel="noopener">WordPress REST API documentation</a>.</p></div></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Method</strong></span></p></td><td class="td"><p>Select the HTTP method you want to use:</p><p><span class="bold bold"><strong>GET</strong></span></p><p>to retrieve information for an entry.</p><p><span class="bold bold"><strong>POST</strong></span></p><p>to create a new entry.</p><p><span class="bold bold"><strong>PUT</strong></span></p><p>to update/replace an existing entry.</p><p><span class="bold bold"><strong>PATCH</strong></span></p><p>to make a partial entry update.</p><p><span class="bold bold"><strong>DELETE</strong></span></p><p>to delete an entry.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Headers</strong></span></p></td><td class="td"><p>Enter the desired request headers. You don't have to add authorization headers; we already did that for you.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Query String</strong></span></p></td><td class="td"><p>Enter the request query string.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Body</strong></span></p></td><td class="td"><p>Enter the body content for your API call.</p></td></tr></tbody></table>

[

### Example of Use - List Pages





](https://www.make.com/en/help/apps/website-building/wordpress#example-of-use---list-pages-968742_body)

The following API call returns all pages in your WordPress:

![61d6be79f13ce.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c1a6be1.png)

Matches of the search can be found in the module Output under Bundle > Body.

In our example, 8 pages were returned:

![wordpress1.png](https://www.make.com/en/help/apps/website-building/wordpress../../image/1621f61c1ad9f4.png)

[

### Search Taxonomies





](https://www.make.com/en/help/apps/website-building/wordpress#search-taxonomies_body)

Retrieves taxonomies based on filter settings, including custom taxonomies.

<table class="informaltable frame-void rules-rows"><colgroup><col><col></colgroup><tbody><tr><td class="td"><p><span class="bold bold"><strong>Connection</strong></span></p></td><td class="td"><p><a class="link" href="https://www.make.com/en/help/apps/website-building/wordpresswordpress.html#connecting-wordpress-to-make-968742" title="Connecting WordPress to Make">Establish a connection to your WordPress.</a></p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Post Type</strong></span></p></td><td class="td"><p>Select the type to limit results to taxonomies associated with a specific post type.</p></td></tr><tr><td class="td"><p><span class="bold bold"><strong>Limit</strong></span></p></td><td class="td"><p>Set the maximum number of taxonomies <span class="phrase">Make</span> will return during one cycle.</p></td></tr></tbody></table>