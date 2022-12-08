---
created: 2022-07-16T15:08:02 (UTC -04:00)
tags: []
source: https://cloud9.ctrlaltback.space/index.php/settings/admin/serverinfo
author: 
---

# Settings - CLOUD9

> ## Excerpt
> Version:7.4.28

---
## External monitoring tool

You can connect an external monitoring tool by using this end point:

Appending "?format=json" at the end of the URL gives you the result in JSON.

To use an access token, please generate one then set it using the following command:

_occ config:app:set serverinfo token --value yourtoken_

Then pass the token with the "NC-Token" header when querying the above URL.
