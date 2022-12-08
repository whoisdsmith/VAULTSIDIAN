---
tags:: notes
created: 2022-07-16T00:09:47 (UTC -04:00)
tags: []
source: https://cloud9.ctrlaltback.space/index.php/settings/user/file_upload_notification
author: 
---

# Settings - CLOUD9

> ## Excerpt
> Connection URL

---
## File Upload Notification

Connection URL 

Notification interval 

Connection ID 

Connection common key

 

## Example of Notification

```
{   
  "id": "https://nextcloud.example.com:user001",
  "since": "1603621635",
  "min_interval": "10" 
}
    
```

## Example of Receipt Notification

```
import logging
import httplib as http
import hmac
from hashlib import sha256
import json
from flask import request
from framework.exceptions import HTTPError

from my_app import celery_check_updated_files

logger = logging.getLogger(__name__)

### connection common key
SECRET = '?????????????????????'  # from configuration file or DB.

# example of flask
def notif_from_nextcloud():
    SIGNATURE_HEADER = 'X-Nextcloud-File-Upload-Notification-Signature'
    signature = request.headers.get(SIGNATURE_HEADER)
    try:
        data = json.loads(request.data)
        provider_id = data.get('id')
    except Exception:
        logger.error('provider_id not found')
        raise HTTPError(http.FORBIDDEN)

    digest = hmac.new(SECRET.encode(), request.data, sha256).hexdigest()
    if not hmac.compare_digest(signature.encode('utf-8'), digest):
        logger.error('invalid signature')
        raise HTTPError(http.FORBIDDEN)

    since = data.get('since')
    interval = data.get('min_interval')

    # run in background task
    celery_check_updated_files.delay(provider_id, since, interval)

    # return immediately
    return ''
    
```

## Example of API Call

```
curl -u test2:password -H 'OCS-APIRequest: true' -X GET 'https://nextcloud.example.com/ocs/v2.php/apps/file_upload_notification/api/recent?since=1607511624'
    
```

## Example of API Call Response

```
<?xml version="1.0"?>
<ocs>
 <meta>
  <status>ok</status>
  <statuscode>200</statuscode>
  <message>OK</message>
 </meta>
 <data>
  <count>2</count>
  <files>
   <element>
    <id>288</id>
    <type>file</type>
    <time>1607512590</time>
    <name>test1.txt</name>
    <path>/test2/test1.txt</path>
    <modified_user>test2</modified_user>
   </element>
   <element>
    <id>277</id>
    <type>file</type>
    <time>1607511624</time>
    <name>test2.txt</name>
    <path>/test2/test2.txt</path>
    <modified_user>test2</modified_user>
   </element>
  </files>
 </data>
</ocs>
    
```
