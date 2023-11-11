# Disallowed-raw-html

## Disallowed Raw HTML (extension)

GFM enables the `tagfilter` extension, where the following HTML tags will be filtered when rendering HTML output:  

* `<title>`

* `<textarea>`

* `<style>`

* `<xmp>`

* `<iframe>`

* `<noembed>`

* `<noframes>`

* `<script>`

* `<plaintext>`

Filtering is done by replacing the leading `<` with the entity `&lt;`. These tags are chosen in particular as they change how HTML is interpreted in a way unique to them (i.e. nested HTML is interpreted differently), and this is usually undesireable in the context of other rendered Markdown content.  
All other HTML tags are left untouched.  
<Example :index="653"/>
