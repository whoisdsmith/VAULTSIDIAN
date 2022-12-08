
tags:: occ
---
created: 2022-07-16T16:32:05 (UTC -04:00)
tags: []
source: https://cloud9.ctrlaltback.space/index.php/apps/occweb/
author: 
---

# OCCWeb - CLOUD9
---

```
{

    "system": {

        "instanceid": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "passwordsalt": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "secret": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "trusted\_domains": \[

            "cloud9.ctrlaltback.space"

        \],

        "datadirectory": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "dbtype": "mysql",

        "version": "24.0.1.1",

        "overwrite.cli.url": "https:\\/\\/cloud9.ctrlaltback.space",

        "dbname": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "dbhost": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "dbport": "",

        "dbtableprefix": "oc\_",

        "mysql.utf8mb4": true,

        "dbuser": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "dbpassword": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "installed": true,

        "default\_phone\_region": "US",

        "mail\_smtpmode": "smtp",

        "mail\_sendmailmode": "smtp",

        "mail\_from\_address": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "mail\_domain": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "app\_install\_overwrite": \[

            "customproperties",

            "workflow\_script",

            "xray",

            "messagevault",

            "file\_upload\_notification",

            "bookmarks\_fulltextsearch",

            "activitylog",

            "occweb"

        \],

        "maintenance": false,

        "has\_rebuilt\_cache": true,

        "enable\_file\_metadata": true,

        "profile.enabled": true,

        "allow\_user\_to\_change\_display\_name": true,

        "enable\_previews": true,

        "preview\_max\_x": 4096,

        "preview\_max\_y": 4096,

        "enabledPreviewProviders": \[

            "OC\\\\Preview\\\\PNG",

            "OC\\\\Preview\\\\JPEG",

            "OC\\\\Preview\\\\GIF",

            "OC\\\\Preview\\\\BMP",

            "OC\\\\Preview\\\\XBitmap",

            "OC\\\\Preview\\\\MP3",

            "OC\\\\Preview\\\\TXT",

            "OC\\\\Preview\\\\MarkDown",

            "OC\\\\Preview\\\\OpenDocument",

            "OC\\\\Preview\\\\Krita"

        \],

        "mail\_smtpsecure": "ssl",

        "mail\_smtpauthtype": "LOGIN",

        "mail\_smtpauth": 1,

        "mail\_smtphost": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "mail\_smtpport": "465",

        "mail\_smtpname": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "mail\_smtppassword": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

        "music.lastfm\_api\_key": "ddbe7f9b20c1d0c519cf099e218e963b",

        "log\_type": "errorlog",

        "logfile": "\\/home2\\/elnulqmy\\/public\_html\\/cloud9-ctrlaltback-space\\/data\\/nextcloud.log",

        "loglevel": "0",

        "log\_query": true,

        "log\_rotate\_size": 104857600,

        "log.condition": {

            "apps": \[

                "admin\_audit"

            \]

        }

    },

    "apps": {

        "accessibility": {

            "enabled": "no",

            "installed\_version": "1.10.0",

            "types": ""

        },

        "activity": {

            "enabled": "no",

            "installed\_version": "2.16.0",

            "notify\_email\_account\_deletion": "1",

            "notify\_email\_analytics\_data": "1",

            "notify\_email\_analytics\_report": "1",

            "notify\_email\_bookmarks": "1",

            "notify\_email\_calendar": "1",

            "notify\_email\_calendar\_event": "1",

            "notify\_email\_calendar\_todo": "1",

            "notify\_email\_comments": "1",

            "notify\_email\_contacts": "1",

            "notify\_email\_file\_changed": "1",

            "notify\_email\_file\_downloaded": "1",

            "notify\_email\_group\_settings": "1",

            "notify\_email\_phonetrack": "1",

            "notify\_email\_phonetrack\_geofence\_event": "1",

            "notify\_email\_phonetrack\_proximity\_event": "1",

            "notify\_email\_public\_links": "1",

            "notify\_email\_remote\_share": "1",

            "notify\_email\_shared": "1",

            "notify\_email\_spreed": "1",

            "notify\_email\_systemtags": "1",

            "notify\_email\_transfer\_failed": "1",

            "notify\_email\_transfer\_started": "1",

            "notify\_email\_transfer\_succeeded": "1",

            "notify\_notification\_account\_deletion": "1",

            "notify\_notification\_analytics\_data": "1",

            "notify\_notification\_analytics\_report": "1",

            "notify\_notification\_bookmarks": "1",

            "notify\_notification\_calendar": "1",

            "notify\_notification\_calendar\_event": "1",

            "notify\_notification\_calendar\_todo": "1",

            "notify\_notification\_comments": "1",

            "notify\_notification\_contacts": "1",

            "notify\_notification\_favorite": "0",

            "notify\_notification\_file\_changed": "1",

            "notify\_notification\_file\_downloaded": "1",

            "notify\_notification\_file\_favorite\_changed": "0",

            "notify\_notification\_group\_settings": "1",

            "notify\_notification\_personal\_settings": "1",

            "notify\_notification\_phonetrack": "1",

            "notify\_notification\_phonetrack\_geofence\_event": "1",

            "notify\_notification\_phonetrack\_proximity\_event": "1",

            "notify\_notification\_public\_links": "1",

            "notify\_notification\_remote\_share": "1",

            "notify\_notification\_security": "1",

            "notify\_notification\_shared": "1",

            "notify\_notification\_spreed": "0",

            "notify\_notification\_systemtags": "1",

            "notify\_notification\_transfer\_failed": "1",

            "notify\_notification\_transfer\_started": "1",

            "notify\_notification\_transfer\_succeeded": "1",

            "notify\_setting\_batchtime": "0",

            "notify\_setting\_self": "0",

            "notify\_setting\_selfemail": "0",

            "types": "filesystem"

        },

        "admin\_audit": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "logging"

        },

        "analytics": {

            "enabled": "no",

            "installed\_version": "4.3.1",

            "types": ""

        },

        "apporder": {

            "enabled": "no",

            "installed\_version": "0.15.0",

            "types": ""

        },

        "audioplayer": {

            "enabled": "yes",

            "installed\_version": "3.3.0",

            "types": "filesystem"

        },

        "auto\_groups": {

            "enabled": "no",

            "installed\_version": "1.4.0",

            "types": ""

        },

        "backgroundjob": {

            "lastjob": "1717"

        },

        "bookmarks": {

            "enabled": "no",

            "installed\_version": "10.5.1",

            "performance.maxBookmarksperAccount": "",

            "previews.pageres.env": "",

            "previews.screenly.token": "",

            "previews.screenly.url": "",

            "previews.screenshotmachine.key": "",

            "previews.webshot.url": "",

            "privacy.enableScraping": "true",

            "types": ""

        },

        "bookmarks\_fulltextsearch": {

            "enabled": "yes",

            "installed\_version": "1.2.0",

            "types": ""

        },

        "breezedark": {

            "enabled": "no",

            "installed\_version": "24.0.1",

            "types": ""

        },

        "bruteforcesettings": {

            "enabled": "no",

            "installed\_version": "2.4.0",

            "types": ""

        },

        "calendar": {

            "enabled": "no",

            "installed\_version": "3.4.2",

            "types": ""

        },

        "camerarawpreviews": {

            "enabled": "no",

            "installed\_version": "0.7.16",

            "types": "filesystem"

        },

        "carnet": {

            "enabled": "no",

            "installed\_version": "0.24.5",

            "types": "filesystem"

        },

        "checksum": {

            "enabled": "yes",

            "installed\_version": "1.1.4",

            "types": "filesystem"

        },

        "circles": {

            "enabled": "no",

            "installed\_version": "24.0.0",

            "loopback\_tmp\_scheme": "https",

            "maintenance\_run": "0",

            "maintenance\_update": "{\\"3\\":1657658889,\\"2\\":1657661046,\\"1\\":1657661046}",

            "types": "filesystem,dav"

        },

        "cloud\_federation\_api": {

            "enabled": "yes",

            "installed\_version": "1.7.0",

            "types": "filesystem"

        },

        "cms\_pico": {

            "enabled": "no",

            "installed\_version": "1.0.19",

            "limit\_groups": "\[\]",

            "plugins\_etag": "7mHljpmeIW",

            "system\_plugins": "{\\"PicoDeprecated\\":{\\"name\\":\\"PicoDeprecated\\",\\"type\\":1,\\"compat\\":true}}",

            "system\_templates": "{\\"empty\\":{\\"name\\":\\"empty\\",\\"type\\":1,\\"compat\\":true},\\"sample\_pico\\":{\\"name\\":\\"sample\_pico\\",\\"type\\":1,\\

"compat\\":true}}",

            "system\_themes": "{\\"default\\":{\\"name\\":\\"default\\",\\"type\\":1,\\"compat\\":true}}",

            "themes\_etag": "30tKzl8MXS",

            "types": "filesystem"

        },

        "collectives": {

            "enabled": "no",

            "installed\_version": "1.2.1",

            "types": "filesystem"

        },

        "comments": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "logging"

        },

        "contacts": {

            "enabled": "yes",

            "installed\_version": "4.1.1",

            "types": "dav"

        },

        "contactsinteraction": {

            "enabled": "no",

            "installed\_version": "1.5.0",

            "types": "dav"

        },

        "core": {

            "backgroundjobs\_mode": "cron",

            "emailTestSuccessful": "1",

            "installed.bundles": "\[\\"CoreBundle\\"\]",

            "installedat": "1655247565.2945",

            "lastcron": "1657926843",

            "lastupdateResult": "{\\"version\\":\\"24.0.2.1\\",\\"versionstring\\":\\"Nextcloud 24.0.2\\",\\"url\\":\\"https:\\\\\\/\\\\\\/download.nextcloud.com\\\\

\\/server\\\\\\/releases\\\\\\/nextcloud-24.0.2.zip\\",\\"web\\":\\"https:\\\\\\/\\\\\\/docs.nextcloud.com\\\\\\/server\\\\\\/24\\\\\\/admin\_manual\\\\\\/maintenance\\\\\\/upgrad

e.html\\",\\"changes\\":\\"https:\\\\\\/\\\\\\/updates.nextcloud.com\\\\\\/changelog\_server\\\\\\/?version=24.0.2\\",\\"autoupdater\\":\\"1\\",\\"eol\\":\\"0\\"}",

            "lastupdatedat": "1657998722",

            "moveavatarsdone": "yes",

            "newUser.sendEmail": "no",

            "oc.integritycheck.checker": "\[\]",

            "previewsCleanedUp": "1",

            "public\_files": "files\_sharing\\/public.php",

            "public\_webdav": "dav\\/appinfo\\/v1\\/publicwebdav.php",

            "theming.variables": "334655d156b79fde55c69362cf8d1322",

            "vendor": "nextcloud"

        },

        "cpanelmailsync": {

            "enabled": "no",

            "installed\_version": "0.1.7",

            "types": ""

        },

        "customproperties": {

            "enabled": "no",

            "installed\_version": "2.0.4",

            "types": ""

        },

        "dashboard": {

            "enabled": "yes",

            "installed\_version": "7.4.0",

            "types": ""

        },

        "data\_request": {

            "enabled": "yes",

            "installed\_version": "1.11.0",

            "types": ""

        },

        "dav": {

            "buildCalendarReminderIndex": "yes",

            "buildCalendarSearchIndex": "yes",

            "builtSocialSearchIndex": "yes",

            "enabled": "yes",

            "installed\_version": "1.22.0",

            "regeneratedBirthdayCalendarsForYearFix": "yes",

            "types": "filesystem"

        },

        "drop\_account": {

            "enabled": "yes",

            "installed\_version": "2.0.0",

            "types": ""

        },

        "duplicatefinder": {

            "backgroundjob\_interval\_cleanup": "1209600",

            "backgroundjob\_interval\_find": "3024000",

            "enabled": "no",

            "ignored\_files": "\[\]",

            "installed\_version": "0.0.14",

            "types": ""

        },

        "emlviewer": {

            "enabled": "no",

            "installed\_version": "1.0.2",

            "types": ""

        },

        "end\_to\_end\_encryption": {

            "enabled": "no",

            "installed\_version": "1.10.0",

            "types": "filesystem,dav"

        },

        "external": {

            "enabled": "no",

            "installed\_version": "4.0.0",

            "types": ""

        },

        "extract": {

            "enabled": "no",

            "installed\_version": "1.3.5",

            "types": ""

        },

        "federatedfilesharing": {

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": ""

        },

        "federation": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "authentication"

        },

        "file\_upload\_notification": {

            "enabled": "yes",

            "installed\_version": "0.1.2",

            "types": "filesystem"

        },

        "files": {

            "enabled": "yes",

            "installed\_version": "1.19.0",

            "types": "filesystem"

        },

        "files\_accesscontrol": {

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": "filesystem"

        },

        "files\_automatedtagging": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "filesystem"

        },

        "files\_downloadactivity": {

            "enabled": "no",

            "installed\_version": "1.13.0",

            "types": "filesystem"

        },

        "files\_external": {

            "enabled": "no",

            "installed\_version": "1.16.1",

            "types": "filesystem",

            "user\_mounting\_backends": "ftp,dav,owncloud,sftp,amazons3,swift,\\\\OC\\\\Files\\\\Storage\\\\SFTP\_Key"

        },

        "files\_fulltextsearch": {

            "enabled": "no",

            "files\_audio": "0",

            "files\_encrypted": "0",

            "files\_external": "1",

            "files\_federated": "0",

            "files\_group\_folders": "0",

            "files\_image": "0",

            "files\_local": "1",

            "files\_office": "1",

            "files\_pdf": "1",

            "files\_size": "20",

            "installed\_version": "24.0.0",

            "types": "filesystem"

        },

        "files\_fulltextsearch\_tesseract": {

            "enabled": "no",

            "installed\_version": "24.0.0",

            "tesseract\_enabled": "1",

            "tesseract\_lang": "eng",

            "tesseract\_pdf": "1",

            "tesseract\_pdf\_limit": "0",

            "tesseract\_psm": "4",

            "types": ""

        },

        "files\_linkeditor": {

            "enabled": "no",

            "installed\_version": "1.1.11",

            "types": ""

        },

        "files\_markdown": {

            "enabled": "no",

            "installed\_version": "2.3.6",

            "types": ""

        },

        "files\_pdfviewer": {

            "enabled": "yes",

            "installed\_version": "2.5.0",

            "types": ""

        },

        "files\_readmemd": {

            "auto\_refresh": "false",

            "disable\_workspace": "true",

            "enabled": "no",

            "fileslist\_footer": "\[\\"README\\"\]",

            "fileslist\_header": "\[\\"HEADER\\"\]",

            "installed\_version": "1.2.2",

            "show\_asciidoc": "true",

            "show\_html": "false",

            "show\_title": "true",

            "types": "filesystem",

            "yellow\_back": "true"

        },

        "files\_rightclick": {

            "enabled": "yes",

            "installed\_version": "1.3.0",

            "types": ""

        },

        "files\_sharing": {

            "enabled": "yes",

            "installed\_version": "1.16.2",

            "types": "filesystem"

        },

        "files\_snapshots": {

            "enabled": "no",

            "installed\_version": "1.0.4",

            "types": ""

        },

        "files\_trashbin": {

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": "filesystem,dav"

        },

        "files\_versions": {

            "enabled": "yes",

            "installed\_version": "1.17.0",

            "types": "filesystem,dav"

        },

        "files\_videoplayer": {

            "enabled": "yes",

            "installed\_version": "1.13.0",

            "types": ""

        },

        "files\_zip": {

            "enabled": "yes",

            "installed\_version": "1.1.2",

            "types": ""

        },

        "fileslibreofficeedit": {

            "enabled": "no",

            "installed\_version": "1.0.4",

            "types": ""

        },

        "firstrunwizard": {

            "enabled": "yes",

            "installed\_version": "2.13.0",

            "types": "logging"

        },

        "flow\_notifications": {

            "enabled": "no",

            "installed\_version": "1.4.0",

            "types": ""

        },

        "fulltextsearch": {

            "app\_navigation": "1",

            "enabled": "no",

            "installed\_version": "24.0.0",

            "search\_platform": "OCA\\\\FullTextSearch\_Elasticsearch\\\\Platform\\\\ElasticSearchPlatform",

            "types": ""

        },

        "fulltextsearch\_elasticsearch": {

            "enabled": "no",

            "installed\_version": "24.0.0",

            "types": ""

        },

        "groupfolders": {

            "enabled": "yes",

            "installed\_version": "12.0.1",

            "types": "filesystem,dav"

        },

        "impersonate": {

            "enabled": "yes",

            "installed\_version": "1.11.0",

            "types": ""

        },

        "integration\_dropbox": {

            "enabled": "yes",

            "installed\_version": "1.0.4",

            "types": ""

        },

        "integration\_github": {

            "enabled": "yes",

            "installed\_version": "1.0.2",

            "types": ""

        },

        "integration\_google": {

            "client\_id": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

            "client\_secret": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

            "enabled": "yes",

            "installed\_version": "1.0.6",

            "types": ""

        },

        "integration\_onedrive": {

            "enabled": "yes",

            "installed\_version": "1.1.2",

            "types": ""

        },

        "integration\_reddit": {

            "enabled": "yes",

            "installed\_version": "1.0.4",

            "types": ""

        },

        "integration\_twitter": {

            "enabled": "yes",

            "installed\_version": "1.0.2",

            "types": ""

        },

        "logreader": {

            "enabled": "yes",

            "installed\_version": "2.9.0",

            "levels": "11111",

            "types": ""

        },

        "lookup\_server\_connector": {

            "enabled": "yes",

            "installed\_version": "1.12.0",

            "types": "authentication"

        },

        "mail": {

            "enabled": "no",

            "installed\_version": "1.13.6",

            "types": ""

        },

        "mediadc": {

            "enabled": "no",

            "installed\_version": "0.1.9",

            "types": ""

        },

        "messagevault": {

            "enabled": "no",

            "installed\_version": "1.0.0",

            "types": "filesystem"

        },

        "metadata": {

            "enabled": "yes",

            "installed\_version": "0.16.0",

            "types": ""

        },

        "music": {

            "enabled": "yes",

            "installed\_version": "1.5.2",

            "types": "filesystem"

        },

        "ncdownloader": {

            "enabled": "no",

            "installed\_version": "0.9.37",

            "types": ""

        },

        "news": {

            "enabled": "no",

            "installed\_version": "18.1.0",

            "types": ""

        },

        "nextcloud\_announcements": {

            "enabled": "no",

            "installed\_version": "1.13.0",

            "pub\_date": "Thu, 24 Oct 2019 00:00:00 +0200",

            "types": "logging"

        },

        "notifications": {

            "enabled": "yes",

            "installed\_version": "2.12.0",

            "types": "logging"

        },

        "notify\_push": {

            "enabled": "yes",

            "installed\_version": "0.4.0",

            "types": "filesystem"

        },

        "oauth2": {

            "enabled": "yes",

            "installed\_version": "1.12.0",

            "types": "authentication"

        },

        "occweb": {

            "enabled": "yes",

            "installed\_version": "0.1.0",

            "types": ""

        },

        "officeonline": {

            "enabled": "no",

            "installed\_version": "1.1.3",

            "types": "filesystem,dav,prevent\_group\_restriction"

        },

        "password\_policy": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "authentication"

        },

        "passwords": {

            "SSEv1ServerKey": "w3yvVGIWkkouYD+tx9Lg1OVMbddfP53\\/ybLe6sZX7r6RpWtyQ3nqq1ZQdtHR3vA2FrElTR0JMgn2cifAB+wpFJ7ESgTECViv09f3O3Vj1E\\/6SbnWY

E7CclJ8FQr5QJf7L9q2+DrQgo9dxKYuDIomXB0dGg3e0odE0z18Trzf+PoHY2lpBrevbYmLLWqQpyVgDBHsa4ZUt7pL8BYgUetOCkE36kNLUV1uMrTZxMwx3I1S599ajK4UgQ\\/0h8NCS2pn7Z

Fq90YE8LPxF29cqLxRVl6Xs3CTs3Wt3gbvm1BJW9a5Hp1DufBFTXUNOlEetNBvNNk6z9e9K8jQ7MUZzQ9qxpysFBJfV7eWPO73XVnu+hAxidVwXi0j+fabdmP4XWWrYgn1PBMvqfgm\\/dnEnM2

Se3CvKFOcx\\/cp033yIBtd2CWiDa\\/9iLFLCYNf5jLoRSi7hqukJxFR\\/UMHTUiPLYlKAKQuso4zCOHzjwajnq1Mv9p0L3plEG9OuB8P9eJdUVXw4D6TJTkMTKbQTb1+fud6LuprdTgUiiS7FY

fjTRB7yWj4X2Q7YqJvIYM9ufthOXsZHZquNbaptdm+MLLHt0ILNLynlqXVRUs6ANVMRBzAzmwsPTe\\/XeFj0MAKB4wk26mCfH7oI8yHvu7mqizRQVhMBV6BUbk8fZg4VHQbO8nWy5RJLKgnFrJ

jCRdtOkWGtUMT8yNB8aCBC\\/BXk6c90yXx2Wk1USRb9KA3gjZVj67RD2D15GRPGbXq43w3xfgE1NxFgZvF7dhpi58iITppJ2EQs4NNP6rMkSGvhgpE6C5mNzlxTZdyAb4W4Lq3ve\\/zVLHw224

EQ\\/vDm87M8aMg0TWSfo8V6ol4hvqduWJByzZq8isBeeEsPyOd62mI+wZCq7nnPoaqMsfbtw4vCMiwUjaQ3YjXaDXA0Uc8zQFRdyw5OgMuq7MUi6yEMylCPg7g29PXo0sZHBBV88u8NKSOnavt

LUgVvm2OS37Ada\\/dHmw70LPARX4wMD17n1vmJTFEGVJZ",

            "cron\\/php\\/version\\/id": "70428",

            "cron\\/php\\/version\\/string": "7.4.28",

            "enabled": "no",

            "installed\_version": "2022.6.10",

            "passwords\\/localdb\\/type": "hibp",

            "types": "",

            "web\\/php\\/version\\/id": "70428",

            "web\\/php\\/version\\/string": "7.4.28"

        },

        "permissions\_overwrite": {

            "enabled": "no",

            "installed\_version": "0.1.7",

            "types": "filesystem"

        },

        "phonetrack": {

            "enabled": "no",

            "installed\_version": "0.7.0",

            "types": ""

        },

        "photos": {

            "enabled": "yes",

            "installed\_version": "1.6.0",

            "types": ""

        },

        "preferred\_providers": {

            "enabled": "no",

            "installed\_version": "1.11.0",

            "provider\_token": "3490312889e469c025af217173c060e9",

            "types": ""

        },

        "previewgenerator": {

            "enabled": "yes",

            "installed\_version": "5.0.0",

            "types": "filesystem"

        },

        "privacy": {

            "enabled": "no",

            "installed\_version": "1.8.0",

            "readableLocation": "us",

            "types": ""

        },

        "provisioning\_api": {

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": "prevent\_group\_restriction"

        },

        "recommendations": {

            "enabled": "no",

            "installed\_version": "1.3.0",

            "types": ""

        },

        "registration": {

            "admin\_approval\_required": "no",

            "disable\_email\_verification": "yes",

            "domains\_is\_blocklist": "no",

            "email\_is\_login": "no",

            "email\_is\_optional": "no",

            "enabled": "yes",

            "enforce\_fullname": "no",

            "enforce\_phone": "no",

            "installed\_version": "1.5.0",

            "show\_domains": "no",

            "show\_fullname": "yes",

            "show\_phone": "no",

            "types": "prevent\_group\_restriction"

        },

        "richdocuments": {

            "disable\_certificate\_verification": "yes",

            "enabled": "no",

            "installed\_version": "6.1.0",

            "types": "prevent\_group\_restriction",

            "wopi\_url": "http:\\/\\/cloud9.ctrlaltback.space\\/apps\\/richdocumentscode\\/proxy.php?req="

        },

        "richdocumentscode": {

            "enabled": "no",

            "installed\_version": "22.5.301",

            "types": ""

        },

        "root\_cache\_cleaner": {

            "enabled": "no",

            "installed\_version": "0.1.2",

            "types": ""

        },

        "serverinfo": {

            "cached\_count\_filecache": "126305",

            "cached\_count\_storages": "7",

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": ""

        },

        "settings": {

            "enabled": "yes",

            "installed\_version": "1.6.0",

            "types": ""

        },

        "sharebymail": {

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "types": "filesystem"

        },

        "sharerenamer": {

            "enabled": "no",

            "installed\_version": "3.0.1",

            "types": ""

        },

        "side\_menu": {

            "cache-categories": "\[{\\"id\\":\\"customization\\",\\"translations\\":{\\"fy\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout 

and UX change apps\\"},\\"ga\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"gd\\":{\\"name\\":\\"Customization\\"

,\\"description\\":\\"Themes, layout and UX change apps\\"},\\"gl\\":{\\"name\\":\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de temas, a

parencia e cambio de interface\\"},\\"en\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"af\\":{\\"name\\":\\"Cus

tomization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"sk\\":{\\"name\\":\\"Prisp\\\\u00f4sobenie\\",\\"description\\":\\"T\\\\u00e9my, rozlo\\\\

u017eenia a zmeny UX aplik\\\\u00e1ci\\\\u00ed\\"},\\"sl\\":{\\"name\\":\\"Prilagajanje sistema\\",\\"description\\":\\"Teme, razporeditve in spremembe vmesnika

\\"},\\"sq\\":{\\"name\\":\\"P\\\\u00ebrshtatje\\",\\"description\\":\\"Temat, pamja dhe Nd\\\\u00ebrfaqja e P\\\\u00ebrdoruesit ndryshojn\\\\u00eb aplikacionet\\"},

\\"sr\\":{\\"name\\":\\"\\\\u041f\\\\u0440\\\\u0438\\\\u043b\\\\u0430\\\\u0433\\\\u043e\\\\u0452\\\\u0430\\\\u0432\\\\u0430\\\\u045a\\\\u0435\\",\\"description\\":\\"\\\\u0422\\\\u0435\\

\\u043c\\\\u0435, \\\\u0440\\\\u0430\\\\u0441\\\\u043f\\\\u043e\\\\u0440\\\\u0435\\\\u0434 \\\\u0435\\\\u043b\\\\u0435\\\\u043c\\\\u0435\\\\u043d\\\\u0430\\\\u0442\\\\u0430 \\\\u0438 \\\\

u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u043c\\\\u0435\\\\u045a\\\\u0430\\\\u0458\\\\u0443 \\\\u04

3a\\\\u043e\\\\u0440\\\\u0438\\\\u0441\\\\u043d\\\\u0438\\\\u0447\\\\u043a\\\\u0438 \\\\u0438\\\\u043d\\\\u0442\\\\u0435\\\\u0440\\\\u0444\\\\u0435\\\\u0458\\\\u0441\\"},\\"hy\\":{\\"nam

e\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"ia\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout a

nd UX change apps\\"},\\"id\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"io\\":{\\"name\\":\\"Customization\\",

\\"description\\":\\"Themes, layout and UX change apps\\"},\\"is\\":{\\"name\\":\\"S\\\\u00e9rsn\\\\u00ed\\\\u00f0ing\\",\\"description\\":\\"\\\\u00deemu, framsetning

 og breytingar \\\\u00e1 vi\\\\u00f0m\\\\u00f3ti\\"},\\"it\\":{\\"name\\":\\"Personalizzazione\\",\\"description\\":\\"Applicazioni di temi, modifiche della dispo

sizione e UX\\"},\\"ja\\":{\\"name\\":\\"\\\\u30ab\\\\u30b9\\\\u30bf\\\\u30de\\\\u30a4\\\\u30ba\\",\\"description\\":\\"\\\\u30a2\\\\u30d7\\\\u30ea\\\\u306e\\\\u30c6\\\\u30fc\\\\u30d

e\\\\u3001\\\\u30ec\\\\u30a4\\\\u30a2\\\\u30a6\\\\u30c8\\\\u3001UX\\\\u5909\\\\u66f4\\"},\\"ka\\":{\\"name\\":\\"\\\\u10de\\\\u10d4\\\\u10e0\\\\u10e1\\\\u10dd\\\\u10dc\\\\u10d0\\\\u10da\\

\\u10d8\\\\u10d6\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d0\\",\\"description\\":\\"\\\\u10d5\\\\u10d8\\\\u10d6\\\\u10e3\\\\u10d0\\\\u10da\\\\u10e3\\\\u10e0\\\\u10d8 \\\\u10d7\\\\u10d4\\\\u10d

b\\\\u10d4\\\\u10d1\\\\u10d8, \\\\u10db\\\\u10d0\\\\u10d9\\\\u10d4\\\\u10e2\\\\u10d8 \\\\u10d3\\\\u10d0 UX \\\\u10ea\\\\u10d5\\\\u10da\\\\u10d8\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10

e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, 

layout and UX change apps\\"},\\"kk\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"km\\":{\\"name\\":\\"Customiz

ation\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"kn\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change a

pps\\"},\\"ko\\":{\\"name\\":\\"\\\\uc0ac\\\\uc6a9\\\\uc790 \\\\uc815\\\\uc758\\",\\"description\\":\\"\\\\ud14c\\\\ub9c8, \\\\ub808\\\\uc774\\\\uc544\\\\uc6c3, UX\\\\ub97c \\\\ubcc0

\\\\uacbd\\\\ud558\\\\ub294 \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"lt\\":{\\"name\\":\\"Tink

inimas\\",\\"description\\":\\"Apipavidalinimai, i\\\\u0161d\\\\u0117stymas ir naudotojo patyrimo keitimo program\\\\u0117l\\\\u0117s\\"},\\"lv\\":{\\"name\\":\\"Cu

stomization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"mk\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX ch

ange apps\\"},\\"ml\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"mn\\":{\\"name\\":\\"Customization\\",\\"descri

ption\\":\\"Themes, layout and UX change apps\\"},\\"te\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"mr\\":{\\

"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"my\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layo

ut and UX change apps\\"},\\"nb\\":{\\"name\\":\\"Tilpasning\\",\\"description\\":\\"Apper for \\\\u00e5 endre tema, utseende og brukeropplevelse\\"},\\"ne\\":{\\

"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"nl\\":{\\"name\\":\\"Maatwerk\\",\\"description\\":\\"Thema's, layout e

n UX aanpassingsapps\\"},\\"th\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"tr\\":{\\"name\\":\\"Uyarlama\\",\\"

description\\":\\"Temalar, g\\\\u00f6r\\\\u00fcn\\\\u00fcm ve kullan\\\\u0131c\\\\u0131 aray\\\\u00fcz\\\\u00fcn\\\\u00fc de\\\\u011fi\\\\u015ftiren uygulamalar\\"},\\"tt

\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"udm\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes

, layout and UX change apps\\"},\\"uk\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"ur\\":{\\"name\\":\\"Custom

ization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"ar\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change

 apps\\"},\\"ast\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"az\\":{\\"name\\":\\"Customization\\",\\"descripti

on\\":\\"Themes, layout and UX change apps\\"},\\"bg\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"be\\":{\\"na

me\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"bn\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout 

and UX change apps\\"},\\"vi\\":{\\"name\\":\\"C\\\\u00e1 nh\\\\u00e2n h\\\\u00f3a\\",\\"description\\":\\"C\\\\u00e1c \\\\u1ee9ng d\\\\u1ee5ng Ch\\\\u1ee7 \\\\u0111\\\\u1ec1

, b\\\\u1ed1 c\\\\u1ee5c v\\\\u00e0 thay \\\\u0111\\\\u1ed5i tr\\\\u1ea3i nghi\\\\u1ec7m ng\\\\u01b0\\\\u1eddi d\\\\u00f9ng\\"},\\"zh-hans\\":{\\"name\\":\\"Customization\\"

,\\"description\\":\\"Themes, layout and UX change apps\\"},\\"zh-hant\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change app

s\\"},\\"br\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"bs\\":{\\"name\\":\\"Customization\\",\\"description\\":

\\"Themes, layout and UX change apps\\"},\\"ca\\":{\\"name\\":\\"Personalitzaci\\\\u00f3\\",\\"description\\":\\"Temes, disposici\\\\u00f3 i apps de canvi d\\\\u20

19UX\\"},\\"cs\\":{\\"name\\":\\"P\\\\u0159izp\\\\u016fsoben\\\\u00ed\\",\\"description\\":\\"Motivy vzhledu, sch\\\\u00e9mata rozvr\\\\u017een\\\\u00ed a aplikace m\\\\u

011bn\\\\u00edc\\\\u00ed dojem z pou\\\\u017e\\\\u00edv\\\\u00e1n\\\\u00ed u\\\\u017eivatelsk\\\\u00e9ho rozhran\\\\u00ed\\"},\\"cy\\":{\\"name\\":\\"Customization\\",\\"de

scription\\":\\"Themes, layout and UX change apps\\"},\\"da\\":{\\"name\\":\\"Tilpasning\\",\\"description\\":\\"Apps til at \\\\u00e6ndre temaer, layout og UX\\

"},\\"de\\":{\\"name\\":\\"Anpassung\\",\\"description\\":\\"Apps zur \\\\u00c4nderung von Design, Layout und Benutzererfahrung\\"},\\"dsb\\":{\\"name\\":\\"Custom

ization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"el\\":{\\"name\\":\\"\\\\u03a0\\\\u03c1\\\\u03bf\\\\u03c3\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b

3\\\\u03ae\\",\\"description\\":\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03b1\\\\u03bb\\\\u03bb\\\\u03b1\\\\u03b3\\\\u03ae\\\\u03c2 \\\\u

03b8\\\\u03ad\\\\u03bc\\\\u03b1\\\\u03c4\\\\u03bf\\\\u03c2, \\\\u03b4\\\\u03b9\\\\u03ac\\\\u03c4\\\\u03b1\\\\u03be\\\\u03b7\\\\u03c2 \\\\u03ba\\\\u03b1\\\\u03b9 UX\\"},\\"eo\\":{\\"nam

e\\":\\"Adaptado\\",\\"description\\":\\"Etosoj, aspekto kaj fasonado\\"},\\"es\\":{\\"name\\":\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Apps de temas, apa

riencia y cambio de interfaz\\"},\\"es-ar\\":{\\"name\\":\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Los temas, la disposici\\\\u00f3n y UX cambian las a

plicaciones\\"},\\"es-co\\":{\\"name\\":\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Los temas, la disposici\\\\u00f3n y UX cambian las aplicaciones\\"},\\"

es-mx\\":{\\"name\\":\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Los temas, la disposici\\\\u00f3n y UX cambian las aplicaciones\\"},\\"es-ni\\":{\\"name\\"

:\\"Personalizaci\\\\u00f3n\\",\\"description\\":\\"Los temas, la disposici\\\\u00f3n y UX cambian las aplicaciones\\"},\\"es-ve\\":{\\"name\\":\\"Personalizaci\\

\\u00f3n\\",\\"description\\":\\"Apps de temas, apariencia y cambio de interfaz\\"},\\"et\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout 

and UX change apps\\"},\\"eu\\":{\\"name\\":\\"Pertsonalizazioa\\",\\"description\\":\\"Gaiak, diseinua eta UX aldaketentzako app-ak\\"},\\"fa\\":{\\"name\\":\\"\\

\\u0633\\\\u0641\\\\u0627\\\\u0631\\\\u0634\\\\u06cc \\\\u0633\\\\u0627\\\\u0632\\\\u06cc\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u06

27 \\\\u060c \\\\u0637\\\\u0631\\\\u062d \\\\u0628\\\\u0646\\\\u062f\\\\u06cc \\\\u0648 \\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u062a\\\\u0

63a\\\\u06cc\\\\u06cc\\\\u0631 UX\\"},\\"nn\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"fi\\":{\\"name\\":\\"Mukaut

us\\",\\"description\\":\\"Teemat, asettelu ja k\\\\u00e4ytt\\\\u00e4j\\\\u00e4kokemusta muuttavat sovellukset\\"},\\"os\\":{\\"name\\":\\"Customization\\",\\"descr

iption\\":\\"Themes, layout and UX change apps\\"},\\"fr\\":{\\"name\\":\\"Personnalisation\\",\\"description\\":\\"Th\\\\u00e8mes et applications modifiant le 

style et l'exp\\\\u00e9rience utilisateur\\"},\\"pa\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"pl\\":{\\"nam

e\\":\\"Dostosowywanie\\",\\"description\\":\\"Style, wygl\\\\u0105d i zmniany UX\\"},\\"pt\\":{\\"name\\":\\"Personalizar\\",\\"description\\":\\"Temas, disposi\\\\u

00e7\\\\u00e3o e aplica\\\\u00e7\\\\u00f5es de altera\\\\u00e7\\\\u00e3o de UX\\"},\\"pt-br\\":{\\"name\\":\\"Personaliza\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplic

ativos para mudar Temas, layout e UX \\"},\\"ro\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"ru\\":{\\"name\\

":\\"\\\\u041d\\\\u0430\\\\u0441\\\\u0442\\\\u0440\\\\u043e\\\\u0439\\\\u043a\\\\u0430\\",\\"description\\":\\"\\\\u0422\\\\u0435\\\\u043c\\\\u044b, \\\\u0440\\\\u0430\\\\u0441\\\\u043a

\\\\u043b\\\\u0430\\\\u0434\\\\u043a\\\\u0438 \\\\u0438 \\\\u043f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f \\\\u0434\\\\u043b\\\\u044f \\\\u0438\\\\

u0437\\\\u043c\\\\u0435\\\\u043d\\\\u0435\\\\u043d\\\\u0438\\\\u044f \\\\u0438\\\\u043d\\\\u0442\\\\u0435\\\\u0440\\\\u0444\\\\u0435\\\\u0439\\\\u0441\\\\u0430\\"},\\"he\\":{\\"name\\":

\\"\\\\u05d4\\\\u05ea\\\\u05d0\\\\u05de\\\\u05d4 \\\\u05d0\\\\u05d9\\\\u05e9\\\\u05d9\\\\u05ea\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u

05d9 \\\\u05e2\\\\u05e8\\\\u05db\\\\u05d5\\\\u05ea \\\\u05e2\\\\u05d9\\\\u05e6\\\\u05d5\\\\u05d1, \\\\u05e4\\\\u05e8\\\\u05d9\\\\u05e1\\\\u05d4 \\\\u05d5\\\\u05e9\\\\u05d9\\\\u05e0\\\\u0

5d5\\\\u05d9\\\\u05d9 \\\\u05d7\\\\u05d5\\\\u05d5\\\\u05d9\\\\u05d9\\\\u05ea \\\\u05de\\\\u05e9\\\\u05ea\\\\u05de\\\\u05e9\\"},\\"hi\\":{\\"name\\":\\"Customization\\",\\"descripti

on\\":\\"Themes, layout and UX change apps\\"},\\"hr\\":{\\"name\\":\\"Prilago\\\\u0111avanje\\",\\"description\\":\\"Aplikacije za teme, izgled i promjene UX-a

\\"},\\"hsb\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"},\\"hu\\":{\\"name\\":\\"Testreszab\\\\u00e1s\\",\\"descripti

on\\":\\"T\\\\u00e9m\\\\u00e1k, elrendez\\\\u00e9sek \\\\u00e9s felhaszn\\\\u00e1l\\\\u00f3i fel\\\\u00fcletet m\\\\u00f3dos\\\\u00edt\\\\u00f3 alkalmaz\\\\u00e1sok\\"},\\"

sr-latn\\":{\\"name\\":\\"\\\\u041f\\\\u0440\\\\u0438\\\\u043b\\\\u0430\\\\u0433\\\\u043e\\\\u0452\\\\u0430\\\\u0432\\\\u0430\\\\u045a\\\\u0435\\",\\"description\\":\\"\\\\u0422\\\\u04

35\\\\u043c\\\\u0435, \\\\u0440\\\\u0430\\\\u0441\\\\u043f\\\\u043e\\\\u0440\\\\u0435\\\\u0434 \\\\u0435\\\\u043b\\\\u0435\\\\u043c\\\\u0435\\\\u043d\\\\u0430\\\\u0442\\\\u0430 \\\\u0438

 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u043c\\\\u0435\\\\u045a\\\\u0430\\\\u0458\\\\u0443 \\\\

u043a\\\\u043e\\\\u0440\\\\u0438\\\\u0441\\\\u043d\\\\u0438\\\\u0447\\\\u043a\\\\u0438 \\\\u0438\\\\u043d\\\\u0442\\\\u0435\\\\u0440\\\\u0444\\\\u0435\\\\u0458\\\\u0441\\"},\\"sv\\":{\\"

name\\":\\"Anpassa\\",\\"description\\":\\"Tema, layout och UX-\\\\u00e4ndringsappar\\"},\\"sw\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layou

t and UX change apps\\"},\\"ta\\":{\\"name\\":\\"Customization\\",\\"description\\":\\"Themes, layout and UX change apps\\"}}},{\\"id\\":\\"dashboard\\",\\"transl

ations\\":{\\"en\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"fy\\":{\\"name\\":\\"Dashboard\\",\\"descript

ion\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ga\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\

"},\\"gd\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"gl\\":{\\"name\\":\\"Taboleiro\\",\\"description\\":\\

"Aplicaci\\\\u00f3ns que incl\\\\u00faen trebellos do Taboleiro do Nextcloud\\"},\\"af\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcl

oud Dashboard widgets\\"},\\"hu\\":{\\"name\\":\\"Ir\\\\u00e1ny\\\\u00edt\\\\u00f3pult\\",\\"description\\":\\"Alkalmaz\\\\u00e1sok, bele\\\\u00e9rtve a Nextcloud Ir\\

\\u00e1ny\\\\u00edt\\\\u00f3pult widgeteket\\"},\\"sk\\":{\\"name\\":\\"Informa\\\\u010dn\\\\u00fd panel\\",\\"description\\":\\"Aplik\\\\u00e1cie vr\\\\u00e1tane ovl\\\\u

00e1dac\\\\u00edch prvkov pre Nextcloud\\"},\\"sl\\":{\\"name\\":\\"Nadzorna plo\\\\u0161\\\\u010da\\",\\"description\\":\\"Programi, vklju\\\\u010dno z gradniki Na

dzorne plo\\\\u0161\\\\u010de\\"},\\"sq\\":{\\"name\\":\\"Tabel\\\\u00eb\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"sr\\":{\\"name\\":\\"

\\\\u041a\\\\u043e\\\\u043d\\\\u0442\\\\u0440\\\\u043e\\\\u043b\\\\u043d\\\\u0430 \\\\u0442\\\\u0430\\\\u0431\\\\u043b\\\\u0430\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u04

38\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u0443\\\\u043a\\\\u0459\\\\u0443\\\\u0447\\\\u0443\\\\u0458\\\\u0443 \\\\u0441\\\\u043f\\

\\u0440\\\\u0430\\\\u0432\\\\u0438\\\\u0446\\\\u0435 \\\\u043d\\\\u0430 \\\\u043a\\\\u043e\\\\u043d\\\\u0442\\\\u0440\\\\u043e\\\\u043b\\\\u043d\\\\u043e\\\\u0458 \\\\u0442\\\\u0430\\\\u0

431\\\\u043b\\\\u0438\\"},\\"hy\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ia\\":{\\"name\\":\\"Dashboard\\"

,\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"id\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboa

rd widgets\\"},\\"io\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"is\\":{\\"name\\":\\"Stj\\\\u00f3rnbor\\\\u

00f0\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"it\\":{\\"name\\":\\"Cruscotto\\",\\"description\\":\\"Applicazioni che includono

 i widget del cruscotto di Nextcloud\\"},\\"ja\\":{\\"name\\":\\"\\\\u30c0\\\\u30c3\\\\u30b7\\\\u30e5\\\\u30dc\\\\u30fc\\\\u30c9\\",\\"description\\":\\"Nextcloud\\\\u30c0\\

\\u30c3\\\\u30b7\\\\u30e5\\\\u30dc\\\\u30fc\\\\u30c9\\\\u30a6\\\\u30a3\\\\u30b8\\\\u30a7\\\\u30c3\\\\u30c8\\\\u3092\\\\u542b\\\\u3093\\\\u3060\\\\u30a2\\\\u30d7\\\\u30ea\\"},\\"ka\\":{\\"

name\\":\\"\\\\u10db\\\\u10d7\\\\u10d0\\\\u10d5\\\\u10d0\\\\u10e0\\\\u10d8 \\\\u10d3\\\\u10d0\\\\u10e4\\\\u10d0\\",\\"description\\":\\"Apps including Nextcloud Dashboard wid

gets\\"},\\"kab\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"kk\\":{\\"name\\":\\"Dashboard\\",\\"descripti

on\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"km\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"

},\\"kn\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ko\\":{\\"name\\":\\"\\\\ub300\\\\uc2dc\\\\ubcf4\\\\ub4dc\\"

,\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"lb\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboa

rd widgets\\"},\\"lt\\":{\\"name\\":\\"Skydelis\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"lv\\":{\\"name\\":\\"Dashboard\\",\\"descr

iption\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"mk\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widge

ts\\"},\\"ml\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"mn\\":{\\"name\\":\\"Dashboard\\",\\"description\\

":\\"Apps including Nextcloud Dashboard widgets\\"},\\"mr\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\

"te\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"my\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"App

s including Nextcloud Dashboard widgets\\"},\\"nb\\":{\\"name\\":\\"Instrumentpanel\\",\\"description\\":\\"Apper som inkluderer Dashboard-widgets\\"},\\"ne\\"

:{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"nl\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps inc

lusief Nextcloud Dashboard-widgets\\"},\\"th\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"tr\\":{\\"nam

e\\":\\"Pano\\",\\"description\\":\\"Nextcloud pano bile\\\\u015fenleri bulunan uygulamalar\\"},\\"tt\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps inclu

ding Nextcloud Dashboard widgets\\"},\\"udm\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"uk\\":{\\"name

\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ur\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including N

extcloud Dashboard widgets\\"},\\"ar\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ast\\":{\\"name\\":\\"D

ashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"az\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextclo

ud Dashboard widgets\\"},\\"bg\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"be\\":{\\"name\\":\\"Dashboar

d\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"bn\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dash

board widgets\\"},\\"vi\\":{\\"name\\":\\"B\\\\u1ea3ng th\\\\u00f4ng tin\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"zh-hans\\":{\\"na

me\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"zh-hant\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps incl

uding Nextcloud Dashboard widgets\\"},\\"br\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"bs\\":{\\"name

\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ca\\":{\\"name\\":\\"Panell de control\\",\\"description\\":\\"Aplicaci

ons que inclouen ginys del tauler de Nextcloud\\"},\\"cs\\":{\\"name\\":\\"N\\\\u00e1st\\\\u011bnka\\",\\"description\\":\\"Aplikace v\\\\u010detn\\\\u011b ovl\\\\u00

e1dac\\\\u00edch prvk\\\\u016f pro Nextcloud P\\\\u0159ehled\\"},\\"cy\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widg

ets\\"},\\"da\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"de\\":{\\"name\\":\\"Dashboard\\",\\"description

\\":\\"Apps einschlie\\\\u00dflich Nextcloud Dashboard-Widgets\\"},\\"dsb\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard

 widgets\\"},\\"el\\":{\\"name\\":\\"\\\\u03a0\\\\u03af\\\\u03bd\\\\u03b1\\\\u03ba\\\\u03b1\\\\u03c2 \\\\u03b5\\\\u03bb\\\\u03ad\\\\u03b3\\\\u03c7\\\\u03bf\\\\u03c5\\",\\"description

\\":\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03c0\\\\u03bf\\\\u03c5 \\\\u03c0\\\\u03b5\\\\u03c1\\\\u03b9\\\\u03bb\\\\u03b1\\\\u03bc\\\\u03b

2\\\\u03ac\\\\u03bd\\\\u03bf\\\\u03c5\\\\u03bd \\\\u03b3\\\\u03c1\\\\u03b1\\\\u03c6\\\\u03b9\\\\u03ba\\\\u03ac \\\\u03c3\\\\u03c4\\\\u03bf\\\\u03b9\\\\u03c7\\\\u03b5\\\\u03af\\\\u03b1 \\\\

u03b3\\\\u03b9\\\\u03b1 \\\\u03c4\\\\u03bf\\\\u03bd \\\\u03c0\\\\u03af\\\\u03bd\\\\u03b1\\\\u03ba\\\\u03b1 \\\\u03b5\\\\u03bb\\\\u03ad\\\\u03b3\\\\u03c7\\\\u03bf\\\\u03c5 \\\\u03c4\\\\u0

3bf\\\\u03c5 Nextcloud\\"},\\"eo\\":{\\"name\\":\\"Regpanelo\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"es\\":{\\"name\\":\\"Dashboar

d\\",\\"description\\":\\"Apps que incluyen widgets para Nextcloud Dashboard\\"},\\"es-ar\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps que incluyen 

widgets para Nextcloud Dashboard\\"},\\"es-co\\":{\\"name\\":\\"Tablero de control\\",\\"description\\":\\"Apps que incluyen widgets para Nextcloud Dashboar

d\\"},\\"es-mx\\":{\\"name\\":\\"Tablero de control\\",\\"description\\":\\"Apps que incluyen widgets para Nextcloud Dashboard\\"},\\"es-ni\\":{\\"name\\":\\"Tabl

ero de control\\",\\"description\\":\\"Apps que incluyen widgets para Nextcloud Dashboard\\"},\\"es-ve\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps 

que incluyen widgets para Nextcloud Dashboard\\"},\\"et\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"

eu\\":{\\"name\\":\\"Mahaia\\",\\"description\\":\\"Nextclouden aginte-panel widgetak dauzkaten aplikazioak\\"},\\"fa\\":{\\"name\\":\\"\\\\u062f\\\\u0627\\\\u0634\\\\u

0628\\\\u0648\\\\u0631\\\\u062f\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"nn\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps 

including Nextcloud Dashboard widgets\\"},\\"fi\\":{\\"name\\":\\"Konsoli\\",\\"description\\":\\"Sovellukset, mukaan lukien konsolin pienoissovellukset\\"},

\\"os\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"fr\\":{\\"name\\":\\"Tableau de bord\\",\\"description\\

":\\"Applications qui incluent un widget de tableau de bord\\"},\\"pa\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard 

widgets\\"},\\"pl\\":{\\"name\\":\\"Pulpit\\",\\"description\\":\\"Aplikacje, w tym wid\\\\u017cety Nextcloud Dashboard\\"},\\"pt\\":{\\"name\\":\\"Painel de contro

lo\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"pt-br\\":{\\"name\\":\\"Painel\\",\\"description\\":\\"Aplicativos incluindo widget

s do Nextcloud Dashboard\\"},\\"ro\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"ru\\":{\\"name\\":\\"\\\\u0

41f\\\\u0430\\\\u043d\\\\u0435\\\\u043b\\\\u044c \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u043b\\\\u0435\\\\u043d\\\\u0438\\\\u044f\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\

u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f, \\\\u0432\\\\u043a\\\\u043b\\\\u044e\\\\u0447\\\\u0430\\\\u044f \\\\u0432\\\\u0438\\\\u0434\\\\u0436\\\\u0435\\\\u04

42\\\\u044b Nextcloud Dashboard\\"},\\"he\\":{\\"name\\":\\"\\\\u05dc\\\\u05d5\\\\u05d7 \\\\u05d1\\\\u05e7\\\\u05e8\\\\u05d4\\",\\"description\\":\\"Apps including Nextclou

d Dashboard widgets\\"},\\"hi\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"hr\\":{\\"name\\":\\"Nadzorna 

plo\\\\u010da\\",\\"description\\":\\"Aplikacije uklju\\\\u010duju\\\\u0107i widgete za nadzornu plo\\\\u010du Nextclouda\\"},\\"hsb\\":{\\"name\\":\\"Dashboard\\",\\

"description\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041a\\\\u043e\\\\u043d\\\\u0442\\\\u0440\\\\u043e\\\\u043b\\\\u043d\\\\u

0430 \\\\u0442\\\\u0430\\\\u0431\\\\u043b\\\\u0430\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e

\\\\u0458\\\\u0435 \\\\u0443\\\\u043a\\\\u0459\\\\u0443\\\\u0447\\\\u0443\\\\u0458\\\\u0443 \\\\u0441\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0438\\\\u0446\\\\u0435 \\\\u043d\\\\u0430 \\\\

u043a\\\\u043e\\\\u043d\\\\u0442\\\\u0440\\\\u043e\\\\u043b\\\\u043d\\\\u043e\\\\u0458 \\\\u0442\\\\u0430\\\\u0431\\\\u043b\\\\u0438\\"},\\"sv\\":{\\"name\\":\\"Dashboard\\",\\"descr

iption\\":\\"Apps including Nextcloud Dashboard widgets\\"},\\"sw\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widge

ts\\"},\\"ta\\":{\\"name\\":\\"Dashboard\\",\\"description\\":\\"Apps including Nextcloud Dashboard widgets\\"}}},{\\"id\\":\\"files\\",\\"translations\\":{\\"en\\":

{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"fy\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management

 and Files app extension apps\\"},\\"ga\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"gd\\":{\\"name\\":\\"F

iles\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"gl\\":{\\"name\\":\\"Ficheiros\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de ext

ensi\\\\u00f3n da xesti\\\\u00f3n de ficheiros e da aplicaci\\\\u00f3n Ficheiros\\"},\\"af\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Fil

es app extension apps\\"},\\"hu\\":{\\"name\\":\\"F\\\\u00e1jlok\\",\\"description\\":\\"F\\\\u00e1jlkezel\\\\u0151 \\\\u00e9s kieg\\\\u00e9sz\\\\u00edt\\\\u0151 alkalmaz

\\\\u00e1sok\\"},\\"sk\\":{\\"name\\":\\"S\\\\u00fabory\\",\\"description\\":\\"Spr\\\\u00e1va s\\\\u00faborov a aplik\\\\u00e1cia S\\\\u00fabory na roz\\\\u0161\\\\u00edre

nie aplik\\\\u00e1ci\\\\u00ed\\"},\\"sl\\":{\\"name\\":\\"Datoteke\\",\\"description\\":\\"Upravljanje z datotekami in raz\\\\u0161iritvami\\"},\\"sq\\":{\\"name\\":\\"

Skedar\\\\u00eb\\",\\"description\\":\\"Aplikacion i menaxhimit t\\\\u00eb skedarit dhe skedar\\\\u00ebve p\\\\u00ebr zgjerim t\\\\u00eb aplikacioneve\\"},\\"sr\\"

:{\\"name\\":\\"\\\\u0424\\\\u0430\\\\u0458\\\\u043b\\\\u043e\\\\u0432\\\\u0438\\",\\"description\\":\\"\\\\u0423\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0459\\\\u0430\\\\u045a\\\\u0435

 \\\\u0444\\\\u0430\\\\u0458\\\\u043b\\\\u043e\\\\u0432\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\

u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u043f\\\\u0440\\\\u043e\\\\u0448\\\\u0438\\\\u0440\\\\u0443\\\\u0458\\\\u0443 \\\\u043e\\\\u0441\\\\u043d\\\\u043e\\\\u0432\\\\u043d\\\\u0443 \\\\u04

30\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0443 \\\\u0424\\\\u0430\\\\u0458\\\\u043b\\\\u043e\\\\u0432\\\\u0430\\"},\\"hy\\":{\\"name\\":\\"Files\\",

\\"description\\":\\"File management and Files app extension apps\\"},\\"ia\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app exten

sion apps\\"},\\"id\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"io\\":{\\"name\\":\\"Files\\",\\"description

\\":\\"File management and Files app extension apps\\"},\\"is\\":{\\"name\\":\\"Skr\\\\u00e1r\\",\\"description\\":\\"Skr\\\\u00e1astj\\\\u00f3rnun og forrit til me

\\\\u00f0h\\\\u00f6ndlunar skr\\\\u00e1aendinga\\"},\\"it\\":{\\"name\\":\\"File\\",\\"description\\":\\"Applicazioni di gestione dei file ed estensione dell'appl

icazione File\\"},\\"ja\\":{\\"name\\":\\"\\\\u30d5\\\\u30a1\\\\u30a4\\\\u30eb\\",\\"description\\":\\"\\\\u30d5\\\\u30a1\\\\u30a4\\\\u30eb\\\\u7ba1\\\\u7406\\\\u3068\\\\u30d5\\\\u30

a1\\\\u30a4\\\\u30eb\\\\u30a2\\\\u30d7\\\\u30ea\\\\u62e1\\\\u5f35\\\\u30a2\\\\u30d7\\\\u30ea\\"},\\"ka\\":{\\"name\\":\\"\\\\u10e4\\\\u10d0\\\\u10d8\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\"

,\\"description\\":\\"\\\\u10e4\\\\u10d0\\\\u10d8\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10db\\\\u10d4\\\\u10dc\\\\u10d4\\\\u10ef\\\\u10db\\\\u10d4\\\\u10dc\\\\u10e2\\\\u10d8

 \\\\u10d3\\\\u10d0 \\\\u10e4\\\\u10d0\\\\u10d8\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d8\\\\u10e1 \\\\

u10d2\\\\u10d0\\\\u10e4\\\\u10d0\\\\u10e0\\\\u10d7\\\\u10dd\\\\u10d4\\\\u10d1\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8

\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"kk\\":{\\"name\\":\\"Files\\",

\\"description\\":\\"File management and Files app extension apps\\"},\\"km\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app exten

sion apps\\"},\\"kn\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"ko\\":{\\"name\\":\\"\\\\ud30c\\\\uc77c\\",\\"de

scription\\":\\"\\\\ud30c\\\\uc77c \\\\uad00\\\\ub9ac \\\\ubc0f \\\\ud30c\\\\uc77c \\\\uc571\\\\uc758 \\\\ud655\\\\uc7a5 \\\\uae30\\\\ub2a5\\"},\\"lb\\":{\\"name\\":\\"Files\\",\\"de

scription\\":\\"File management and Files app extension apps\\"},\\"lt\\":{\\"name\\":\\"Failai\\",\\"description\\":\\"Fail\\\\u0173 tvarkymo ir fail\\\\u0173 pr

ogram\\\\u0173 pl\\\\u0117tini\\\\u0173 programos\\"},\\"lv\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"mk\\"

:{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"ml\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File managemen

t and Files app extension apps\\"},\\"mn\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"mr\\":{\\"name\\":\\"

Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"te\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files a

pp extension apps\\"},\\"my\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"nb\\":{\\"name\\":\\"Filer\\",\\"des

cription\\":\\"App for filh\\\\u00e5ndtering og utvidelser til Filer\\"},\\"ne\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app ext

ension apps\\"},\\"nl\\":{\\"name\\":\\"Bestanden\\",\\"description\\":\\"Bestandsbeheer en uitbreidingen van bestand apps\\"},\\"th\\":{\\"name\\":\\"Files\\",\\"d

escription\\":\\"File management and Files app extension apps\\"},\\"tr\\":{\\"name\\":\\"Dosyalar\\",\\"description\\":\\"Dosya y\\\\u00f6netimi ve Dosya uygul

amas\\\\u0131 eklentileri\\"},\\"tt\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"udm\\":{\\"name\\":\\"Files\\

",\\"description\\":\\"File management and Files app extension apps\\"},\\"uk\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app ext

ension apps\\"},\\"ur\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"ar\\":{\\"name\\":\\"Files\\",\\"descripti

on\\":\\"File management and Files app extension apps\\"},\\"ast\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\

"},\\"az\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"bg\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File 

management and Files app extension apps\\"},\\"be\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"bn\\":{\\"

name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"vi\\":{\\"name\\":\\"T\\\\u1ec7p tin\\",\\"description\\":\\"Qu\\\\u1ea3n

 l\\\\u00fd t\\\\u1ec7p v\\\\u00e0 c\\\\u00e1c \\\\u1ee9ng d\\\\u1ee5ng m\\\\u1edf r\\\\u1ed9ng cho \\\\u1ee9ng d\\\\u1ee5ng T\\\\u1eadp tin\\"},\\"zh-hans\\":{\\"name\\":\\"

Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"zh-hant\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Fi

les app extension apps\\"},\\"br\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"bs\\":{\\"name\\":\\"Files\\",

\\"description\\":\\"File management and Files app extension apps\\"},\\"ca\\":{\\"name\\":\\"Fitxers\\",\\"description\\":\\"Apps de gesti\\\\u00f3 de fitxers i

 fitxers d\\\\u2019extensi\\\\u00f3 d\\\\u2019apps\\"},\\"cs\\":{\\"name\\":\\"Soubory\\",\\"description\\":\\"Aplikace roz\\\\u0161i\\\\u0159uj\\\\u00edc\\\\u00ed spr\\\\u

00e1vu soubor\\\\u016f a aplikaci Soubory\\"},\\"cy\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"da\\":{\\"

name\\":\\"Filer\\",\\"description\\":\\"Filh\\\\u00e5ndtering og Files app udvidelses apps\\"},\\"de\\":{\\"name\\":\\"Dateien\\",\\"description\\":\\"Dateimanagem

ent sowie Erweiterungs-Apps f\\\\u00fcr die Dateien-App\\"},\\"dsb\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension app

s\\"},\\"el\\":{\\"name\\":\\"\\\\u0391\\\\u03c1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03b1\\",\\"description\\":\\"\\\\u0394\\\\u03b9\\\\u03b1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03c1\\\\u03b9\\\\u

03c3\\\\u03b7 \\\\u03b1\\\\u03c1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03c9\\\\u03bd \\\\u03ba\\\\u03b1\\\\u03b9 \\\\u03b5\\\\u03c0\\\\u03ad\\\\u03ba\\\\u03c4\\\\u03b1\\\\u03c3\\\\u03b7 \\\\u03

b5\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ae\\\\u03c2 \\\\u0391\\\\u03c1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03b1 \\\\u03b3\\\\u03b9\\\\u03b1 \\\\u03b5\\\\u03c6\\\\u03b1\\

\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2\\"},\\"eo\\":{\\"name\\":\\"Dosieroj\\",\\"description\\":\\"Dosieradministrado kaj kromprogramoj por la aplika\\\\u

0135o \\\\u201eDosieroj\\\\u201c\\"},\\"es\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Apps de manejo de archivos y de extensi\\\\u00f3n de la app Archivos

\\"},\\"es-ar\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Aplicaciones de Administraci\\\\u00f3n de archivos y extensi\\\\u00f3n a la aplicaci\\\\u00f3n de

 Archivos\\"},\\"es-co\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Aplicaciones de Administraci\\\\u00f3n de archivos y extensi\\\\u00f3n a la aplicaci\\\\

u00f3n de Archivos\\"},\\"es-mx\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Aplicaciones de Administraci\\\\u00f3n de archivos y extensi\\\\u00f3n a la a

plicaci\\\\u00f3n de Archivos\\"},\\"es-ni\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Aplicaciones de Administraci\\\\u00f3n de archivos y extensi\\\\u00f

3n a la aplicaci\\\\u00f3n de Archivos\\"},\\"es-ve\\":{\\"name\\":\\"Archivos\\",\\"description\\":\\"Apps de manejo de archivos y de extensi\\\\u00f3n de la a

pp Archivos\\"},\\"et\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"eu\\":{\\"name\\":\\"Fitxategiak\\",\\"des

cription\\":\\"Fitxategien kudeaketa eta Fitxategi app-aren luzapen app-ak\\"},\\"fa\\":{\\"name\\":\\"\\\\u0641\\\\u0627\\\\u06cc\\\\u0644\\",\\"description\\":\\"\\\\

u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u0645\\\\u062f\\\\u06cc\\\\u0631\\\\u06cc\\\\u062a \\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u06

47 \\\\u0645\\\\u062f\\\\u06cc\\\\u0631\\\\u06cc\\\\u062a \\\\u0641\\\\u0627\\\\u06cc\\\\u0644\\\\u0647\\\\u0627 \\\\u0648 \\\\u067e\\\\u0631\\\\u0648\\\\u0646\\\\u062f\\\\u0647 \\\\u064

7\\\\u0627\\"},\\"nn\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"fi\\":{\\"name\\":\\"Tiedostot\\",\\"descript

ion\\":\\"Tiedostojenhallintasovellukset ja Tiedostot-sovelluksen lis\\\\u00e4osat\\"},\\"os\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and

 Files app extension apps\\"},\\"fr\\":{\\"name\\":\\"Fichiers\\",\\"description\\":\\"Applications de gestion de fichiers et extensions de l'application Fi

chiers\\"},\\"pa\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"pl\\":{\\"name\\":\\"Pliki\\",\\"description\\":

\\"Aplikacje do zarz\\\\u0105dzania plikiem i dodatki aplikacji Pliki\\"},\\"pt\\":{\\"name\\":\\"Ficheiros\\",\\"description\\":\\"Gest\\\\u00e3o de ficheiros e

 aplica\\\\u00e7\\\\u00f5es de extens\\\\u00e3o \\\\u00e0 aplica\\\\u00e7\\\\u00e3o Ficheiros\\"},\\"pt-br\\":{\\"name\\":\\"Arquivos\\",\\"description\\":\\"Gerenciame

nto de arquivos e extens\\\\u00e3o de aplicativo\\"},\\"ro\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"r

u\\":{\\"name\\":\\"\\\\u0424\\\\u0430\\\\u0439\\\\u043b\\\\u044b\\",\\"description\\":\\"\\\\u0420\\\\u0430\\\\u0441\\\\u0448\\\\u0438\\\\u0440\\\\u0435\\\\u043d\\\\u0438\\\\u0435: \\\\

u0444\\\\u0430\\\\u0439\\\\u043b\\\\u044b \\\\u0438 \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u043b\\\\u0435\\\\u043d\\\\u0438\\\\u0435 \\\\u0444\\\\u0430\\\\u0439\\\\u043b\\\\u04

30\\\\u043c\\\\u0438\\"},\\"he\\":{\\"name\\":\\"\\\\u05e7\\\\u05d1\\\\u05e6\\\\u05d9\\\\u05dd\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\

u05d9 \\\\u05e0\\\\u05d9\\\\u05d4\\\\u05d5\\\\u05dc \\\\u05e7\\\\u05d1\\\\u05e6\\\\u05d9\\\\u05dd \\\\u05d5\\\\u05d4\\\\u05e8\\\\u05d7\\\\u05d1\\\\u05d5\\\\u05ea \\\\u05d9\\\\u05d9\\\\u0

5e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9 \\\\u05e7\\\\u05d1\\\\u05e6\\\\u05d9\\\\u05dd\\"},\\"hi\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Fil

es app extension apps\\"},\\"hr\\":{\\"name\\":\\"Datoteke\\",\\"description\\":\\"Aplikacije za upravljanje datotekama i pro\\\\u0161irenjima za aplikaciju D

atoteke\\"},\\"hsb\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0424\\\\u0430\\\\u

0458\\\\u043b\\\\u043e\\\\u0432\\\\u0438\\",\\"description\\":\\"\\\\u0423\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0459\\\\u0430\\\\u045a\\\\u0435 \\\\u0444\\\\u0430\\\\u0458\\\\u043b\\

\\u043e\\\\u0432\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u

043f\\\\u0440\\\\u043e\\\\u0448\\\\u0438\\\\u0440\\\\u0443\\\\u0458\\\\u0443 \\\\u043e\\\\u0441\\\\u043d\\\\u043e\\\\u0432\\\\u043d\\\\u0443 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a

\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0443 \\\\u0424\\\\u0430\\\\u0458\\\\u043b\\\\u043e\\\\u0432\\\\u0430\\"},\\"sv\\":{\\"name\\":\\"Filer\\",\\"description\\":\\"Filhantering

 och Filers till\\\\u00e4ggsappar\\"},\\"sw\\":{\\"name\\":\\"Files\\",\\"description\\":\\"File management and Files app extension apps\\"},\\"ta\\":{\\"name\\":\\

"Files\\",\\"description\\":\\"File management and Files app extension apps\\"}}},{\\"id\\":\\"games\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Games\\",\\"desc

ription\\":\\"Games run in your Nextcloud\\"},\\"fy\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ga\\":{\\"name\\":\\"Games\\",

\\"description\\":\\"Games run in your Nextcloud\\"},\\"gd\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"gl\\":{\\"name\\":\\"Xo

gos\\",\\"description\\":\\"Xogos funcionando no seu Nextcloud\\"},\\"af\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"sk\\":{

\\"name\\":\\"Hry\\",\\"description\\":\\"Hry be\\\\u017eia vo va\\\\u0161om Nextcloude\\"},\\"sl\\":{\\"name\\":\\"Igre\\",\\"description\\":\\"Igre, ki se izvajajo v

 oblaku Nextcloud\\"},\\"sq\\":{\\"name\\":\\"Loj\\\\u00ebra\\",\\"description\\":\\"Lojer\\\\u00ebt n\\\\u00eb Nextcloud-in tuaj\\"},\\"sr\\":{\\"name\\":\\"\\\\u0418\\\\u

0433\\\\u0440\\\\u0438\\\\u0446\\\\u0435\\",\\"description\\":\\"\\\\u0418\\\\u0433\\\\u0440\\\\u0438\\\\u0446\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u0441\\\\u0435 \\\\u043

f\\\\u043e\\\\u043a\\\\u0440\\\\u0435\\\\u045b\\\\u0443 \\\\u0438\\\\u0437 \\\\u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043b\\\\u0430\\\\u0443\\\\u0434\\\\u0430\\"},\\"hu\\"

:{\\"name\\":\\"J\\\\u00e1t\\\\u00e9kok\\",\\"description\\":\\"J\\\\u00e1t\\\\u00e9kok a Nextcloudj\\\\u00e1ban\\"},\\"hy\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Ga

mes run in your Nextcloud\\"},\\"ia\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"id\\":{\\"name\\":\\"Games\\",\\"description\\

":\\"Games run in your Nextcloud\\"},\\"io\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"is\\":{\\"name\\":\\"Leikir\\",\\"descr

iption\\":\\"Leikir keyr\\\\u00f0ir \\\\u00ed \\\\u00fe\\\\u00ednu eigin Nextcloud\\"},\\"it\\":{\\"name\\":\\"Giochi\\",\\"description\\":\\"Giochi da far girare nel

 tuo Nextcloud\\"},\\"ja\\":{\\"name\\":\\"\\\\u30b2\\\\u30fc\\\\u30e0\\",\\"description\\":\\"Nextcloud\\\\u3067\\\\u52d5\\\\u304f\\\\u30b2\\\\u30fc\\\\u30e0\\"},\\"ka\\":{\\"na

me\\":\\"\\\\u10d7\\\\u10d0\\\\u10db\\\\u10d0\\\\u10e8\\\\u10d4\\\\u10d1\\\\u10d8\\",\\"description\\":\\"\\\\u10d7\\\\u10d0\\\\u10db\\\\u10d0\\\\u10e8\\\\u10d4\\\\u10d1\\\\u10d8, \\\\u1

0e0\\\\u10dd\\\\u10db\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10ea \\\\u10db\\\\u10e3\\\\u10e8\\\\u10d0\\\\u10dd\\\\u10d1\\\\u10d4\\\\u10dc \\\\u10d7\\\\u10e5\\\\u10d5\\\\u10d4\\\\u10dc\\

\\u10e1 Nextcloud-\\\\u10e8\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"kk\\":{\\"name\\":\\"Games\\",\\"descr

iption\\":\\"Games run in your Nextcloud\\"},\\"km\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"kn\\":{\\"name\\":\\"Games\\",\\

"description\\":\\"Games run in your Nextcloud\\"},\\"ko\\":{\\"name\\":\\"\\\\uac8c\\\\uc784\\",\\"description\\":\\"\\\\ub0b4 Nextcloud\\\\uc5d0\\\\uc11c \\\\uc2e4\\\\ud5

89\\\\ud558\\\\ub294 \\\\uac8c\\\\uc784\\"},\\"lb\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"lt\\":{\\"name\\":\\"\\\\u017daidimai\\"

,\\"description\\":\\"\\\\u017daidimai J\\\\u016bs\\\\u0173 Nextcloud\\"},\\"lv\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"mk\\"

:{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ml\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},

\\"mn\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"mr\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextclo

ud\\"},\\"te\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"my\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your N

extcloud\\"},\\"nb\\":{\\"name\\":\\"Spill\\",\\"description\\":\\"Spillbare spill i din Nextcloud\\"},\\"ne\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run

 in your Nextcloud\\"},\\"nl\\":{\\"name\\":\\"Spelen\\",\\"description\\":\\"Spellen draaiend in je Nextcloud\\"},\\"th\\":{\\"name\\":\\"Games\\",\\"description\\"

:\\"Games run in your Nextcloud\\"},\\"tr\\":{\\"name\\":\\"Oyunlar\\",\\"description\\":\\"Nextcloud hesab\\\\u0131n\\\\u0131zda \\\\u00e7al\\\\u0131\\\\u015fan oyunl

ar\\"},\\"tt\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"udm\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your 

Nextcloud\\"},\\"uk\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ar\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in

 your Nextcloud\\"},\\"ast\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"az\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games

 run in your Nextcloud\\"},\\"bg\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"be\\":{\\"name\\":\\"Games\\",\\"description\\":\\

"Games run in your Nextcloud\\"},\\"bn\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ur\\":{\\"name\\":\\"Games\\",\\"descripti

on\\":\\"Games run in your Nextcloud\\"},\\"vi\\":{\\"name\\":\\"Tr\\\\u00f2 ch\\\\u01a1i\\",\\"description\\":\\"C\\\\u00e1c tr\\\\u00f2 ch\\\\u01a1i ch\\\\u1ea1y tr\\\\u0

0ean Nextcloud c\\\\u1ee7a b\\\\u1ea1n\\"},\\"zh-hans\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"zh-hant\\":{\\"name\\":\\"Gam

es\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"br\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"bs\\":{\\"name\\"

:\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ca\\":{\\"name\\":\\"Jocs\\",\\"description\\":\\"Jocs que s'executaran en el vostre Nextclo

ud\\"},\\"cs\\":{\\"name\\":\\"Hry\\",\\"description\\":\\"Hry spustiteln\\\\u00e9 v r\\\\u00e1mci Nextcloud\\"},\\"cy\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Gam

es run in your Nextcloud\\"},\\"da\\":{\\"name\\":\\"Spil\\",\\"description\\":\\"Spil der k\\\\u00f8res i din Nextcloud\\"},\\"de\\":{\\"name\\":\\"Spiele\\",\\"desc

ription\\":\\"Spiele f\\\\u00fcr Deine Nextcloud\\"},\\"dsb\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"el\\":{\\"name\\":\\"\\\\

u03a0\\\\u03b1\\\\u03b9\\\\u03c7\\\\u03bd\\\\u03af\\\\u03b4\\\\u03b9\\\\u03b1\\",\\"description\\":\\"\\\\u03a0\\\\u03b1\\\\u03b9\\\\u03c7\\\\u03bd\\\\u03af\\\\u03b4\\\\u03b9\\\\u03b1 

\\\\u03c0\\\\u03bf\\\\u03c5 \\\\u03c4\\\\u03c1\\\\u03ad\\\\u03c7\\\\u03bf\\\\u03c5\\\\u03bd \\\\u03c3\\\\u03c4\\\\u03bf Nextcloud \\\\u03c3\\\\u03b1\\\\u03c2\\"},\\"eo\\":{\\"name\\":

\\"Ludoj\\",\\"description\\":\\"Ludoj ene de via Nextcloud\\"},\\"es\\":{\\"name\\":\\"Juegos\\",\\"description\\":\\"Juegos que funcionan en tu Nextcloud\\"},\\"

es-ar\\":{\\"name\\":\\"Juegos\\",\\"description\\":\\"Los juegos se ejecutan en tu Nextcloud\\"},\\"es-co\\":{\\"name\\":\\"Juegos\\",\\"description\\":\\"Juegos q

ue corren en tu Nextcloud\\"},\\"es-mx\\":{\\"name\\":\\"Juegos\\",\\"description\\":\\"Juegos que corren en tu Nextcloud\\"},\\"es-ni\\":{\\"name\\":\\"Juegos\\",

\\"description\\":\\"Juegos que corren en tu Nextcloud\\"},\\"es-ve\\":{\\"name\\":\\"Juegos\\",\\"description\\":\\"Juegos que funcionan en tu Nextcloud\\"},\\"

et\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"eu\\":{\\"name\\":\\"Jokuak\\",\\"description\\":\\"Zure Nextcloudean exekuta 

daitezkeen jokuak\\"},\\"fa\\":{\\"name\\":\\"\\\\u0628\\\\u0627\\\\u0632\\\\u06cc \\\\u0647\\\\u0627\\",\\"description\\":\\"\\\\u0628\\\\u0627\\\\u0632\\\\u06cc \\\\u0647\\\\u062

7 \\\\u062f\\\\u0631 \\\\u0646\\\\u06a9\\\\u0633\\\\u062a \\\\u06a9\\\\u0644\\\\u0648\\\\u062f \\\\u0634\\\\u0645\\\\u0627 \\\\u0627\\\\u062c\\\\u0631\\\\u0627 \\\\u0645\\\\u06cc \\\\u06

34\\\\u0648\\\\u0646\\\\u062f\\"},\\"nn\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"fi\\":{\\"name\\":\\"Pelit\\",\\"description\\":

\\"Pelit suoritetaan Nextcloudissasi\\"},\\"os\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"fr\\":{\\"name\\":\\"Jeux\\",\\"des

cription\\":\\"Les jeux fonctionnant dans votre Nextcloud\\"},\\"pa\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"pl\\":{\\"n

ame\\":\\"Gry\\",\\"description\\":\\"Gry dla Nextcloud\\"},\\"pt\\":{\\"name\\":\\"Jogos\\",\\"description\\":\\"Jogos executados na sua Nextcloud\\"},\\"pt-br\\":{

\\"name\\":\\"Jogos\\",\\"description\\":\\"Os jogos rodam em seu Nextcloud\\"},\\"ro\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"

},\\"ru\\":{\\"name\\":\\"\\\\u0418\\\\u0433\\\\u0440\\\\u044b\\",\\"description\\":\\"\\\\u0412 Nextcloud \\\\u0437\\\\u0430\\\\u043f\\\\u0443\\\\u0441\\\\u043a\\\\u0430\\\\u044e\\\\

u0442\\\\u0441\\\\u044f \\\\u0438\\\\u0433\\\\u0440\\\\u044b\\"},\\"he\\":{\\"name\\":\\"\\\\u05de\\\\u05e9\\\\u05d7\\\\u05e7\\\\u05d9\\\\u05dd\\",\\"description\\":\\"\\\\u05de\\\\u05

e9\\\\u05d7\\\\u05e7\\\\u05d9\\\\u05dd \\\\u05e9\\\\u05e4\\\\u05d5\\\\u05e2\\\\u05dc\\\\u05d9\\\\u05dd \\\\u05d1\\\\u05beNextcloud \\\\u05e9\\\\u05dc\\\\u05da\\"},\\"hi\\":{\\"name\\"

:\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"hr\\":{\\"name\\":\\"Igre\\",\\"description\\":\\"Igre koje se izvode u va\\\\u0161em Nextclou

du\\"},\\"hsb\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0418\\\\u0433\\\\u0440\\\\u0438\\\\u0446\\\\u0

435\\",\\"description\\":\\"\\\\u0418\\\\u0433\\\\u0440\\\\u0438\\\\u0446\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u0441\\\\u0435 \\\\u043f\\\\u043e\\\\u043a\\\\u0440\\\\u0435

\\\\u045b\\\\u0443 \\\\u0438\\\\u0437 \\\\u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043b\\\\u0430\\\\u0443\\\\u0434\\\\u0430\\"},\\"sv\\":{\\"name\\":\\"Spel\\",\\"descrip

tion\\":\\"Spel k\\\\u00f6r i ditt Nextcloud\\"},\\"sw\\":{\\"name\\":\\"Games\\",\\"description\\":\\"Games run in your Nextcloud\\"},\\"ta\\":{\\"name\\":\\"Games\\"

,\\"description\\":\\"Games run in your Nextcloud\\"}}},{\\"id\\":\\"integration\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"A

pps that connect Nextcloud with other services and platforms\\"},\\"fy\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud wit

h other services and platforms\\"},\\"ga\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms

\\"},\\"gd\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"af\\":{\\"name\\":\\"Integra

tion\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"sk\\":{\\"name\\":\\"Integr\\\\u00e1cia\\",\\"description\\":\\"

Apky, ktor\\\\u00e9 prep\\\\u00e1jaj\\\\u00fa Nextcloud s in\\\\u00fdmi slu\\\\u017ebami a platformami\\"},\\"sl\\":{\\"name\\":\\"Sodelovanje in delo\\",\\"descrip

tion\\":\\"Programi, ki povezujejo Nextcloud z drugimi storitvami in okolji\\"},\\"sq\\":{\\"name\\":\\"Integrimi\\",\\"description\\":\\"Aplikacionet q\\\\u00e

b lidhen me Nextcloud me an\\\\u00ebn e  sh\\\\u00ebrbimeve dhe platformave t\\\\u00eb tjera\\"},\\"sr\\":{\\"name\\":\\"\\\\u0418\\\\u043d\\\\u0442\\\\u0435\\\\u0433\\\\

u0440\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e

\\\\u0458\\\\u0435 \\\\u043f\\\\u043e\\\\u0432\\\\u0435\\\\u0437\\\\u0443\\\\u0458\\\\u0443 \\\\u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043b\\\\u0430\\\\u0443\\\\u0434 \\\\u

0441\\\\u0430 \\\\u0434\\\\u0440\\\\u0443\\\\u0433\\\\u0438\\\\u043c \\\\u0441\\\\u0435\\\\u0440\\\\u0432\\\\u0438\\\\u0441\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u043f\\\\u043b\\\\u04

30\\\\u0442\\\\u0444\\\\u043e\\\\u0440\\\\u043c\\\\u0430\\\\u043c\\\\u0430\\"},\\"hu\\":{\\"name\\":\\"Integr\\\\u00e1ci\\\\u00f3\\",\\"description\\":\\"Alkalmaz\\\\u00e1sok, me

lyek a Nextcloudot m\\\\u00e1s szolg\\\\u00e1ltat\\\\u00e1sokhoz \\\\u00e9s platformokhoz kapcsolj\\\\u00e1k\\"},\\"hy\\":{\\"name\\":\\"Integration\\",\\"descripti

on\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ia\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextc

loud with other services and platforms\\"},\\"id\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and p

latforms\\"},\\"io\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"is\\":{\\"name\\":\\

"Sam\\\\u00fe\\\\u00e6tting\\",\\"description\\":\\"Forrit sem tengja Nextcloud vi\\\\u00f0 a\\\\u00f0rar \\\\u00fej\\\\u00f3nustur og kerfi\\"},\\"it\\":{\\"name\\":\\

"Integrazione\\",\\"description\\":\\"Applicazioni che collegano Nextcloud con altri servizi e piattaforme\\"},\\"ja\\":{\\"name\\":\\"\\\\u9023\\\\u643a\\",\\"de

scription\\":\\"NextCloud\\\\u3068\\\\u4ed6\\\\u306e\\\\u30b5\\\\u30fc\\\\u30d3\\\\u30b9\\\\u3084\\\\u30d7\\\\u30e9\\\\u30c3\\\\u30c8\\\\u30d5\\\\u30a9\\\\u30fc\\\\u30e0\\\\u3092\\\\u6

3a5\\\\u7d9a\\\\u3059\\\\u308b\\\\u30a2\\\\u30d7\\\\u30ea\\\\u30b1\\\\u30fc\\\\u30b7\\\\u30e7\\\\u30f3\\"},\\"ka\\":{\\"name\\":\\"\\\\u10d8\\\\u10dc\\\\u10e2\\\\u10d4\\\\u10d2\\\\u10e0\\

\\u10d0\\\\u10ea\\\\u10d8\\\\u10d0\\",\\"description\\":\\"\\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8 \\\\u10e0\\\\u10dd\\\\u10d

b\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10ea \\\\u10d0\\\\u10d9\\\\u10d0\\\\u10d5\\\\u10e8\\\\u10d8\\\\u10e0\\\\u10d4\\\\u10d1\\\\u10d4\\\\u10dc Nextcloud-\\\\u10e1 \\\\u10e1\\\\u10e

e\\\\u10d5\\\\u10d0 \\\\u10e1\\\\u10d4\\\\u10e0\\\\u10d5\\\\u10d8\\\\u10e1\\\\u10d4\\\\u10d1\\\\u10e1\\\\u10d0 \\\\u10d3\\\\u10d0 \\\\u10de\\\\u10da\\\\u10d0\\\\u10e2\\\\u10e4\\\\u10dd\\\\

u10e0\\\\u10db\\\\u10d4\\\\u10d1\\\\u10d7\\\\u10d0\\\\u10dc \\"},\\"kab\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other ser

vices and platforms\\"},\\"kk\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"km\\":

{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"kn\\":{\\"name\\":\\"Integration\\",\\"de

scription\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ko\\":{\\"name\\":\\"\\\\ud1b5\\\\ud569\\",\\"description\\":\\"Nextcloud\\\\uc

640 \\\\ub2e4\\\\ub978 \\\\uc11c\\\\ube44\\\\uc2a4 \\\\ubc0f \\\\ud50c\\\\ub7ab\\\\ud3fc\\\\uc744 \\\\ud1b5\\\\ud569\\\\ud558\\\\ub294 \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Integrati

on\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"lt\\":{\\"name\\":\\"Integracija\\",\\"description\\":\\"Program

os, jungian\\\\u010dios Nextcloud su kitomis paslaugomis ir platformomis\\"},\\"lv\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nex

tcloud with other services and platforms\\"},\\"mk\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and

 platforms\\"},\\"ml\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"mn\\":{\\"name\\"

:\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"mr\\":{\\"name\\":\\"Integration\\",\\"description

\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"te\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextclo

ud with other services and platforms\\"},\\"my\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and pla

tforms\\"},\\"nb\\":{\\"name\\":\\"Integrasjon\\",\\"description\\":\\"Apper som kobler Nextcloud med andre tjenester og plattformer\\"},\\"ne\\":{\\"name\\":\\"I

ntegration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"nl\\":{\\"name\\":\\"Integratie\\",\\"description\\":\\"

Apps die Nextcloud verbinden met andere services en platformen\\"},\\"th\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud w

ith other services and platforms\\"},\\"tr\\":{\\"name\\":\\"B\\\\u00fct\\\\u00fcnle\\\\u015ftirme\\",\\"description\\":\\"Nextcloud ile di\\\\u011fer hizmet ve pla

tformlar\\\\u0131 b\\\\u00fct\\\\u00fcnle\\\\u015ftiren uygulamalar\\"},\\"tt\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with

 other services and platforms\\"},\\"udm\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms

\\"},\\"uk\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ar\\":{\\"name\\":\\"Integra

tion\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ast\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps

 that connect Nextcloud with other services and platforms\\"},\\"az\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with o

ther services and platforms\\"},\\"bg\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"}

,\\"be\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"bn\\":{\\"name\\":\\"Integratio

n\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ur\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps tha

t connect Nextcloud with other services and platforms\\"},\\"vi\\":{\\"name\\":\\"T\\\\u00edch h\\\\u1ee3p\\",\\"description\\":\\"C\\\\u00e1c \\\\u1ee9ng d\\\\u1ee5n

g k\\\\u1ebft n\\\\u1ed1i Nextcloud v\\\\u1edbi c\\\\u00e1c d\\\\u1ecbch v\\\\u1ee5 v\\\\u00e0 n\\\\u1ec1n t\\\\u1ea3ng kh\\\\u00e1c\\"},\\"zh-hans\\":{\\"name\\":\\"Integr

ation\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"zh-hant\\":{\\"name\\":\\"Integration\\",\\"description\\":\\

"Apps that connect Nextcloud with other services and platforms\\"},\\"br\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud w

ith other services and platforms\\"},\\"bs\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platfor

ms\\"},\\"ca\\":{\\"name\\":\\"Integraci\\\\u00f3\\",\\"description\\":\\"Aplicacions que es connecten a Nextcloud amb altres serveis i plataformes\\"},\\"cs\\":

{\\"name\\":\\"Propojen\\\\u00ed\\",\\"description\\":\\"Aplikace kter\\\\u00e9 NextCloud propojuj\\\\u00ed s dal\\\\u0161\\\\u00edmi slu\\\\u017ebami a platformami\\

"},\\"cy\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"da\\":{\\"name\\":\\"Integrat

ion\\",\\"description\\":\\"Apps der forbinder Nextcloud med andre services og platforme\\"},\\"de\\":{\\"name\\":\\"Einbindung\\",\\"description\\":\\"Apps die

 Nextcloud mit anderen Diensten und Plattformen verbinden\\"},\\"dsb\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with 

other services and platforms\\"},\\"el\\":{\\"name\\":\\"\\\\u0395\\\\u03bd\\\\u03c3\\\\u03c9\\\\u03bc\\\\u03ac\\\\u03c4\\\\u03c9\\\\u03c3\\\\u03b7\\",\\"description\\":\\"\\\\u0

395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03c0\\\\u03bf\\\\u03c5 \\\\u03c3\\\\u03c5\\\\u03bd\\\\u03b4\\\\u03ad\\\\u03bf\\\\u03c5\\\\u03bd \\\\u03c4

\\\\u03bf Nextcloud \\\\u03bc\\\\u03b5 \\\\u03ac\\\\u03bb\\\\u03bb\\\\u03b5\\\\u03c2 \\\\u03c5\\\\u03c0\\\\u03b7\\\\u03c1\\\\u03b5\\\\u03c3\\\\u03af\\\\u03b5\\\\u03c2 \\\\u03ba\\\\u03b

1\\\\u03b9 \\\\u03c0\\\\u03bb\\\\u03b1\\\\u03c4\\\\u03c6\\\\u03cc\\\\u03c1\\\\u03bc\\\\u03b5\\\\u03c2\\"},\\"eo\\":{\\"name\\":\\"Integrigo\\",\\"description\\":\\"Aplika\\\\u0135o

j, kiuj interligas Nextcloud-on kun aliaj servoj kaj platformoj\\"},\\"es\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Apps que conectan Next

cloud con otros servicios y plataformas\\"},\\"es-ar\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones que conectan a Nextcloud con o

tros servicios y plataformas\\"},\\"es-co\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones que conectan a Nextcloud con otros servic

ios y plataformas\\"},\\"es-mx\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones que conectan a Nextcloud con otros servicios y plata

formas\\"},\\"es-ni\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones que conectan a Nextcloud con otros servicios y plataformas\\"},\\

"es-ve\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Apps que conectan Nextcloud con otros servicios y plataformas\\"},\\"et\\":{\\"name\\":\\"Int

egration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"eu\\":{\\"name\\":\\"Integrazioa\\",\\"description\\":\\"N

extcloud beste zerbitzu eta plataformekin konektatzeko app-ak\\"},\\"fa\\":{\\"name\\":\\"\\\\u0627\\\\u062f\\\\u063a\\\\u0627\\\\u0645\\",\\"description\\":\\"\\\\u062

8\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc\\\\u06cc \\\\u06a9\\\\u0647 \\\\u0646\\\\u06a9\\\\u0633\\\\u062a \\\\u06a9\\\\u0644\\\\u0648\\\\u062f \\\\u0631

\\\\u0627 \\\\u0628\\\\u0627 \\\\u0633\\\\u0627\\\\u06cc\\\\u0631 \\\\u0633\\\\u0631\\\\u0648\\\\u06cc\\\\u0633 \\\\u0647\\\\u0627 \\\\u0648 \\\\u0633\\\\u06cc\\\\u0633\\\\u062a\\\\u0645

 \\\\u0639\\\\u0627\\\\u0645\\\\u0644 \\\\u0647\\\\u0627 \\\\u0645\\\\u062a\\\\u0635\\\\u0644 \\\\u0645\\\\u06cc \\\\u06a9\\\\u0646\\\\u062f\\"},\\"nn\\":{\\"name\\":\\"Integration\\"

,\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"fi\\":{\\"name\\":\\"Integraatio\\",\\"description\\":\\"Sovellukset

, jotka yhdist\\\\u00e4v\\\\u00e4t Nextcloudin muihin palveluihin ja sovellusalustoihin\\"},\\"os\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps tha

t connect Nextcloud with other services and platforms\\"},\\"fr\\":{\\"name\\":\\"Int\\\\u00e9gration\\",\\"description\\":\\"Applications qui connectent Next

cloud avec d'autres services et plateformes\\"},\\"pa\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services 

and platforms\\"},\\"pl\\":{\\"name\\":\\"Integracja\\",\\"description\\":\\"Po\\\\u0142\\\\u0105czenie Nextcloud z innymi us\\\\u0142ugami i platformami\\"},\\"pt\\

":{\\"name\\":\\"Integra\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00f5es que ligam a sua Nextcloud a outros servi\\\\u00e7os e plataformas\\"}

,\\"pt-br\\":{\\"name\\":\\"Integra\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplicativos que conectam ao Nextcloud com outros servi\\\\u00e7os e plataformas\\"}

,\\"ro\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ru\\":{\\"name\\":\\"\\\\u0418\\\\u

043d\\\\u0442\\\\u0435\\\\u0433\\\\u0440\\\\u0430\\\\u0446\\\\u0438\\\\u044f\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\

u044f, \\\\u0441\\\\u043e\\\\u0435\\\\u0434\\\\u0438\\\\u043d\\\\u044f\\\\u044e\\\\u0449\\\\u0438\\\\u0435 Nextcloud \\\\u0441 \\\\u0434\\\\u0440\\\\u0443\\\\u0433\\\\u0438\\\\u043c\\

\\u0438 \\\\u0441\\\\u043b\\\\u0443\\\\u0436\\\\u0431\\\\u0430\\\\u043c\\\\u0438 \\\\u0438 \\\\u043f\\\\u043b\\\\u0430\\\\u0442\\\\u0444\\\\u043e\\\\u0440\\\\u043c\\\\u0430\\\\u043c\\\\u0

438\\"},\\"gl\\":{\\"name\\":\\"Integraci\\\\u00f3n\\",\\"description\\":\\"Aplicaci\\\\u00f3ns que conectan o Nextcloud con outros servizos e plataformas\\"},\\"

he\\":{\\"name\\":\\"\\\\u05e9\\\\u05d9\\\\u05dc\\\\u05d5\\\\u05d1\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9\\\\u05dd \\\\u05e9\\\\

u05de\\\\u05d7\\\\u05d1\\\\u05e8\\\\u05d9\\\\u05dd \\\\u05d0\\\\u05ea Nextcloud \\\\u05e2\\\\u05dd \\\\u05e9\\\\u05d9\\\\u05e8\\\\u05d5\\\\u05ea\\\\u05d9\\\\u05dd \\\\u05d5\\\\u05e4\\

\\u05dc\\\\u05d8\\\\u05e4\\\\u05d5\\\\u05e8\\\\u05de\\\\u05d5\\\\u05ea \\\\u05d0\\\\u05d7\\\\u05e8\\\\u05d9\\\\u05dd\\"},\\"hi\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"

Apps that connect Nextcloud with other services and platforms\\"},\\"hr\\":{\\"name\\":\\"Integracija\\",\\"description\\":\\"Aplikacije koje povezuju Nextc

loud s drugim uslugama i platformama\\"},\\"hsb\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that connect Nextcloud with other services and pl

atforms\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0418\\\\u043d\\\\u0442\\\\u0435\\\\u0433\\\\u0440\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\u0410\\\\u043

f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u043f\\\\u043e\\\\u0432\\\\u0435\\\\u0437\\\\u0443\\\\u0458\\\\u0443 \\\\

u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043b\\\\u0430\\\\u0443\\\\u0434 \\\\u0441\\\\u0430 \\\\u0434\\\\u0440\\\\u0443\\\\u0433\\\\u0438\\\\u043c \\\\u0441\\\\u0435\\\\u04

40\\\\u0432\\\\u0438\\\\u0441\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u043f\\\\u043b\\\\u0430\\\\u0442\\\\u0444\\\\u043e\\\\u0440\\\\u043c\\\\u0430\\\\u043c\\\\u0430\\"},\\"sv\\":{\\"na

me\\":\\"Integration\\",\\"description\\":\\"Appar som ansluter Nextcloud med andra tj\\\\u00e4nster och plattformar\\"},\\"sw\\":{\\"name\\":\\"Integration\\",\\

"description\\":\\"Apps that connect Nextcloud with other services and platforms\\"},\\"ta\\":{\\"name\\":\\"Integration\\",\\"description\\":\\"Apps that con

nect Nextcloud with other services and platforms\\"}}},{\\"id\\":\\"monitoring\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"D

ata statistics, system diagnostics and activity apps\\"},\\"fy\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and 

activity apps\\"},\\"ga\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"gd\\":{\\"name\\":\\"Mon

itoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"af\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statis

tics, system diagnostics and activity apps\\"},\\"sk\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"\\\\u0160tatistika d\\\\u00e1t, diagnostika syst\\\\u00e

9mu a aktivity aplik\\\\u00e1ci\\\\u00ed\\"},\\"sl\\":{\\"name\\":\\"Nadzor in delovanje\\",\\"description\\":\\"Statistika podatkov, sistemska diagnostika in p

rogrami za spremljanje dejavnosti\\"},\\"sq\\":{\\"name\\":\\"V\\\\u00ebzhgim\\",\\"description\\":\\"Statistikat e t\\\\u00eb dh\\\\u00ebnave, diagnostikimi i si

stemit dhe aplikacionet e aktivitetit\\"},\\"sr\\":{\\"name\\":\\"\\\\u041d\\\\u0430\\\\u0434\\\\u0433\\\\u043b\\\\u0435\\\\u0434\\\\u0430\\\\u045a\\\\u0435\\",\\"description

\\":\\"\\\\u0421\\\\u0442\\\\u0430\\\\u0442\\\\u0438\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0435 \\\\u043e \\\\u043f\\\\u043e\\\\u0434\\\\u0430\\\\u0446\\\\u0438\\\\u043c\\\\u0430, \\\\u0

434\\\\u0438\\\\u0458\\\\u0430\\\\u0433\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0430 \\\\u0441\\\\u0438\\\\u0441\\\\u0442\\\\u0435\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430

\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0430\\\\u043a\\\\u0442\\\\u0438\\\\u0432\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\\\u0438\\"},\\"hu\\":{

\\"name\\":\\"Rendszerfel\\\\u00fcgyelet\\",\\"description\\":\\"Adatstatisztika, rendszerdiagnosztika \\\\u00e9s tev\\\\u00e9kenys\\\\u00e9gk\\\\u00f6vet\\\\u0151 a

lkalmaz\\\\u00e1sok\\"},\\"hy\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"ia\\":{\\"name\\":\\

"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"id\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data st

atistics, system diagnostics and activity apps\\"},\\"io\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activi

ty apps\\"},\\"is\\":{\\"name\\":\\"V\\\\u00f6ktun\\",\\"description\\":\\"T\\\\u00f6lfr\\\\u00e6\\\\u00f0i gagna, greining kerfis og virkniforrit\\"},\\"it\\":{\\"name

\\":\\"Monitoraggio\\",\\"description\\":\\"Applicazioni di statistiche, diagnostica di sistema e attivit\\\\u00e0\\"},\\"ja\\":{\\"name\\":\\"\\\\u30e2\\\\u30cb\\\\u

30bf\\\\u30ea\\\\u30f3\\\\u30b0\\",\\"description\\":\\"\\\\u30c7\\\\u30fc\\\\u30bf\\\\u7d71\\\\u8a08\\\\u3001\\\\u30b7\\\\u30b9\\\\u30c6\\\\u30e0\\\\u8a3a\\\\u65ad\\\\u304a\\\\u3088\\\\

u3073\\\\u30a2\\\\u30af\\\\u30c6\\\\u30a3\\\\u30d3\\\\u30c6\\\\u30a3\\\\u30a2\\\\u30d7\\\\u30ea\\\\u30b1\\\\u30fc\\\\u30b7\\\\u30e7\\\\u30f3\\"},\\"ka\\":{\\"name\\":\\"\\\\u10db\\\\u10d

8\\\\u10dc\\\\u10d8\\\\u10e2\\\\u10dd\\\\u10e0\\\\u10d8\\\\u10dc\\\\u10d2\\\\u10d8\\",\\"description\\":\\"\\\\u10db\\\\u10dd\\\\u10dc\\\\u10d0\\\\u10ea\\\\u10d4\\\\u10db\\\\u10d7\\\\u10

d0 \\\\u10e1\\\\u10e2\\\\u10d0\\\\u10e2\\\\u10d8\\\\u10e1\\\\u10e2\\\\u10d8\\\\u10d9\\\\u10d0, \\\\u10e1\\\\u10d8\\\\u10e1\\\\u10e2\\\\u10d4\\\\u10db\\\\u10d8\\\\u10e1 \\\\u10d3\\\\u10d8

\\\\u10d0\\\\u10d2\\\\u10dc\\\\u10dd\\\\u10d6\\\\u10d8 \\\\u10d3\\\\u10d0 \\\\u10d0\\\\u10e5\\\\u10e2\\\\u10d8\\\\u10d5\\\\u10dd\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u

10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics an

d activity apps\\"},\\"kk\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"km\\":{\\"name\\":\\"M

onitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"kn\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data stat

istics, system diagnostics and activity apps\\"},\\"ko\\":{\\"name\\":\\"\\\\ubaa8\\\\ub2c8\\\\ud130\\\\ub9c1\\",\\"description\\":\\"\\\\ub370\\\\uc774\\\\ud130 \\\\ud1b5\\

\\uacc4, \\\\uc2dc\\\\uc2a4\\\\ud15c \\\\uc9c4\\\\ub2e8 \\\\ubc0f \\\\ud65c\\\\ub3d9 \\\\uad00\\\\ub9ac \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Da

ta statistics, system diagnostics and activity apps\\"},\\"lt\\":{\\"name\\":\\"Steb\\\\u0117sena\\",\\"description\\":\\"Duomen\\\\u0173 statistikos, sistemos 

diagnostikos ir veiklos programos\\"},\\"lv\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"

mk\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"ml\\":{\\"name\\":\\"Monitoring\\",\\"descrip

tion\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"mn\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagno

stics and activity apps\\"},\\"mr\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"my\\":{\\"na

me\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"nb\\":{\\"name\\":\\"Overv\\\\u00e5king\\",\\"description

\\":\\"Apper for statistikk, systemdiagnose og aktivitet\\"},\\"ne\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics an

d activity apps\\"},\\"te\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"th\\":{\\"name\\":\\"M

onitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"tr\\":{\\"name\\":\\"\\\\u0130zleme\\",\\"description\\":\\"Veri is

tatistikleri, sistem tan\\\\u0131lama ve i\\\\u015flem uygulamalar\\\\u0131\\"},\\"tt\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system

 diagnostics and activity apps\\"},\\"udm\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"uk

\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"ar\\":{\\"name\\":\\"Monitoring\\",\\"descripti

on\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"ast\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnos

tics and activity apps\\"},\\"az\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"bg\\":{\\"nam

e\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"be\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Da

ta statistics, system diagnostics and activity apps\\"},\\"ur\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and a

ctivity apps\\"},\\"vi\\":{\\"name\\":\\"Gi\\\\u00e1m s\\\\u00e1t\\",\\"description\\":\\"C\\\\u00e1c th\\\\u1ed1ng k\\\\u00ea d\\\\u1eef li\\\\u1ec7u, c\\\\u00e1c chu\\\\u1e

a9n \\\\u0111o\\\\u00e1n h\\\\u1ec7 th\\\\u1ed1ng v\\\\u00e0 ho\\\\u1ea1t \\\\u0111\\\\u1ed9ng c\\\\u1ee7a c\\\\u00e1c \\\\u1ee9ng d\\\\u1ee5ng\\"},\\"zh-hans\\":{\\"name\\":\\

"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"zh-hant\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Da

ta statistics, system diagnostics and activity apps\\"},\\"bn\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and a

ctivity apps\\"},\\"br\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"bs\\":{\\"name\\":\\"Moni

toring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"nl\\":{\\"name\\":\\"Monitoren\\",\\"description\\":\\"Gegevensstati

stiek, systeem diagnose en activiteit apps\\"},\\"ca\\":{\\"name\\":\\"Seguiment\\",\\"description\\":\\"Apps sobre dades estad\\\\u00edstiques, diagnosis de 

sistema i activitat\\"},\\"cs\\":{\\"name\\":\\"Dohled\\",\\"description\\":\\"Datov\\\\u00e9 statistiky, diagnostiky syst\\\\u00e9mu a aktivity aplikac\\\\u00ed\\

"},\\"cy\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"da\\":{\\"name\\":\\"Monitorering\\",\\"

description\\":\\"Datastatistik, systemdiagnoser og -aktivitets apps\\"},\\"de\\":{\\"name\\":\\"\\\\u00dcberwachung\\",\\"description\\":\\"Datenstatistiken-, 

Systemdiagnose- und Aktivit\\\\u00e4ten-Apps\\"},\\"dsb\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity 

apps\\"},\\"el\\":{\\"name\\":\\"\\\\u03a0\\\\u03b1\\\\u03c1\\\\u03b1\\\\u03ba\\\\u03bf\\\\u03bb\\\\u03bf\\\\u03cd\\\\u03b8\\\\u03b7\\\\u03c3\\\\u03b7\\",\\"description\\":\\"\\\\u03a3

\\\\u03c4\\\\u03b1\\\\u03c4\\\\u03b9\\\\u03c3\\\\u03c4\\\\u03b9\\\\u03ba\\\\u03ac \\\\u03b4\\\\u03b5\\\\u03b4\\\\u03bf\\\\u03bc\\\\u03ad\\\\u03bd\\\\u03c9\\\\u03bd, \\\\u03b4\\\\u03b9\\\\u

03b1\\\\u03b3\\\\u03bd\\\\u03c9\\\\u03c3\\\\u03c4\\\\u03b9\\\\u03ba\\\\u03ac \\\\u03c3\\\\u03c5\\\\u03c3\\\\u03c4\\\\u03ae\\\\u03bc\\\\u03b1\\\\u03c4\\\\u03bf\\\\u03c2 \\\\u03ba\\\\u03b1

\\\\u03b9 \\\\u03b4\\\\u03c1\\\\u03b1\\\\u03c3\\\\u03c4\\\\u03b7\\\\u03c1\\\\u03b9\\\\u03cc\\\\u03c4\\\\u03b7\\\\u03c4\\\\u03b1 \\\\u03b5\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u0

3b3\\\\u03ce\\\\u03bd\\"},\\"eo\\":{\\"name\\":\\"Observado\\",\\"description\\":\\"Statistiko, sistema diagnozo kaj aktiva\\\\u0135oj\\"},\\"es\\":{\\"name\\":\\"Monit

orizaci\\\\u00f3n\\",\\"description\\":\\"Apps de estad\\\\u00edsticas, diagn\\\\u00f3sticos del sistema y actividad\\"},\\"es-ar\\":{\\"name\\":\\"Monitoreo\\",\\"

description\\":\\"Aplicaciones de estad\\\\u00edstica de datos, diagn\\\\u00f3stico del sistema y actividad\\"},\\"es-co\\":{\\"name\\":\\"Monitoreo\\",\\"descr

iption\\":\\"Aplicaciones de estad\\\\u00edstica de datos, diagn\\\\u00f3stico del sistema y actividad\\"},\\"es-mx\\":{\\"name\\":\\"Monitoreo\\",\\"descriptio

n\\":\\"Aplicaciones de estad\\\\u00edstica de datos, diagn\\\\u00f3stico del sistema y actividad\\"},\\"es-ni\\":{\\"name\\":\\"Monitoreo\\",\\"description\\":\\

"Aplicaciones de estad\\\\u00edstica de datos, diagn\\\\u00f3stico del sistema y actividad\\"},\\"es-ve\\":{\\"name\\":\\"Monitorizaci\\\\u00f3n\\",\\"descripti

on\\":\\"Apps de estad\\\\u00edsticas, diagn\\\\u00f3sticos del sistema y actividad\\"},\\"et\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics

, system diagnostics and activity apps\\"},\\"eu\\":{\\"name\\":\\"Monitorizazioa\\",\\"description\\":\\"Datu estatiktikak, sistema diagnostikoa eta jardue

ra app-ak\\"},\\"fa\\":{\\"name\\":\\"\\\\u0646\\\\u0638\\\\u0627\\\\u0631\\\\u062a \\\\u0628\\\\u0631\\",\\"description\\":\\"\\\\u0622\\\\u0645\\\\u0627\\\\u0631 \\\\u062f\\\\u0627

\\\\u062f\\\\u0647 \\\\u0647\\\\u0627 \\\\u060c \\\\u062a\\\\u0634\\\\u062e\\\\u06cc\\\\u0635 \\\\u0633\\\\u06cc\\\\u0633\\\\u062a\\\\u0645 \\\\u0648 \\\\u0628\\\\u0631\\\\u0646\\\\u0627

\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u0641\\\\u0639\\\\u0627\\\\u0644\\\\u06cc\\\\u062a\\"},\\"nn\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statisti

cs, system diagnostics and activity apps\\"},\\"fi\\":{\\"name\\":\\"Monitorointi\\",\\"description\\":\\"Data tilastot, j\\\\u00e4rjestelm\\\\u00e4diagnostiikk

a ja aktiviteettisovellukset\\"},\\"os\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"fr\\":

{\\"name\\":\\"Supervision\\",\\"description\\":\\"Applications de statistiques sur les donn\\\\u00e9es, de diagnostics syst\\\\u00e8mes et d'activit\\\\u00e9.

\\"},\\"pa\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"pl\\":{\\"name\\":\\"Monitorowanie\\",

\\"description\\":\\"Statystyki, diagnostyka i aktywno\\\\u015bci\\"},\\"pt\\":{\\"name\\":\\"Monitoriza\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Estat\\\\u00edstica

s de dados, diagn\\\\u00f3sticos de sistema e aplica\\\\u00e7\\\\u00f5es de actividade \\"},\\"pt-br\\":{\\"name\\":\\"Monitoramento\\",\\"description\\":\\"Estat

\\\\u00edsticas de dados, diagn\\\\u00f3sticos de sistema e atividades de aplicativos\\"},\\"ro\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statis

tics, system diagnostics and activity apps\\"},\\"gl\\":{\\"name\\":\\"Supervisando\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de estat\\\\u00edstica de datos,

 diagn\\\\u00f3stico do sistema e actividade\\"},\\"he\\":{\\"name\\":\\"\\\\u05de\\\\u05e2\\\\u05e7\\\\u05d1\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u0

5de\\\\u05d5\\\\u05e0\\\\u05d9\\\\u05dd \\\\u05dc\\\\u05e0\\\\u05d9\\\\u05ea\\\\u05d5\\\\u05d7 \\\\u05e1\\\\u05d8\\\\u05d8\\\\u05d9\\\\u05e1\\\\u05d8\\\\u05d9, \\\\u05d1\\\\u05d3\\\\u05d

9\\\\u05e7\\\\u05ea \\\\u05d4\\\\u05de\\\\u05e2\\\\u05e8\\\\u05db\\\\u05ea \\\\u05d5\\\\u05e4\\\\u05e2\\\\u05d9\\\\u05dc\\\\u05d5\\\\u05d9\\\\u05d5\\\\u05ea\\"},\\"hi\\":{\\"name\\":\\"M

onitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"hr\\":{\\"name\\":\\"Pra\\\\u0107enje\\",\\"description\\":\\"Aplik

acije za statistiku podataka, dijagnostiku sustava i aktivnosti\\"},\\"hsb\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diag

nostics and activity apps\\"},\\"ru\\":{\\"name\\":\\"\\\\u041c\\\\u043e\\\\u043d\\\\u0438\\\\u0442\\\\u043e\\\\u0440\\\\u0438\\\\u043d\\\\u0433\\",\\"description\\":\\"\\\\u0421

\\\\u0442\\\\u0430\\\\u0442\\\\u0438\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0430 \\\\u0434\\\\u0430\\\\u043d\\\\u043d\\\\u044b\\\\u0445, \\\\u0434\\\\u0438\\\\u0430\\\\u0433\\\\u043d\\\\u

043e\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0430 \\\\u0441\\\\u0438\\\\u0441\\\\u0442\\\\u0435\\\\u043c\\\\u044b \\\\u0438 \\\\u0430\\\\u043a\\\\u0442\\\\u0438\\\\u0432\\\\u043d\\\\u043

e\\\\u0441\\\\u0442\\\\u044c \\\\u043f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u0439\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041d\\\\u0430\\\\u0434\\\\u0

433\\\\u043b\\\\u0435\\\\u0434\\\\u0430\\\\u045a\\\\u0435\\",\\"description\\":\\"\\\\u0421\\\\u0442\\\\u0430\\\\u0442\\\\u0438\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0435 \\\\u043e \\

\\u043f\\\\u043e\\\\u0434\\\\u0430\\\\u0446\\\\u0438\\\\u043c\\\\u0430, \\\\u0434\\\\u0438\\\\u0458\\\\u0430\\\\u0433\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\\\u0438\\\\u043a\\\\u0430 \\\\u0

441\\\\u0438\\\\u0441\\\\u0442\\\\u0435\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0430\\\\u043a\\\\u0442

\\\\u0438\\\\u0432\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\\\u0438\\"},\\"sv\\":{\\"name\\":\\"\\\\u00d6vervakning\\",\\"description\\":\\"Datastatistik, systemdiagnostik och 

aktivitetsappar\\"},\\"sw\\":{\\"name\\":\\"Monitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"},\\"ta\\":{\\"name\\":\\"M

onitoring\\",\\"description\\":\\"Data statistics, system diagnostics and activity apps\\"}}},{\\"id\\":\\"multimedia\\",\\"translations\\":{\\"en\\":{\\"name\\"

:\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"fy\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps

\\"},\\"ga\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"gd\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, vi

deo and picture apps\\"},\\"af\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ru\\":{\\"name\\":\\"\\\\u041c\\\\u0443\\\\u043

b\\\\u044c\\\\u0442\\\\u0438\\\\u043c\\\\u0435\\\\u0434\\\\u0438\\\\u0430\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u04

35 \\\\u0430\\\\u0443\\\\u0434\\\\u0438\\\\u043e, \\\\u0432\\\\u0438\\\\u0434\\\\u0435\\\\u043e \\\\u0438 \\\\u0438\\\\u0437\\\\u043e\\\\u0431\\\\u0440\\\\u0430\\\\u0436\\\\u0435\\\\u043

d\\\\u0438\\\\u044f\\"},\\"sk\\":{\\"name\\":\\"Multim\\\\u00e9di\\\\u00e1\\",\\"description\\":\\"Aplik\\\\u00e1cie pre audio, video a obr\\\\u00e1zky\\"},\\"sl\\":{\\"nam

e\\":\\"Ve\\\\u010dpredstavnost\\",\\"description\\":\\"Programi za zvok, video in slike\\"},\\"sq\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Aplikacione 

audio, video dhe fotosh\\"},\\"sr\\":{\\"name\\":\\"\\\\u041c\\\\u0443\\\\u043b\\\\u0442\\\\u0438\\\\u043c\\\\u0435\\\\u0434\\\\u0438\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\

u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0437\\\\u0430 \\\\u0430\\\\u0443\\\\u0434\\\\u0438\\\\u043e, \\\\u0432\\\\u0438\\\\u0434\\\\u0

435\\\\u043e \\\\u0438 \\\\u0441\\\\u043b\\\\u0438\\\\u043a\\\\u0435\\"},\\"hu\\":{\\"name\\":\\"Multim\\\\u00e9dia\\",\\"description\\":\\"Hang-, vide\\\\u00f3- \\\\u00e9s k\\\\

u00e9palkalmaz\\\\u00e1sok\\"},\\"hy\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ia\\":{\\"name\\":\\"Multimedia\\",\\"d

escription\\":\\"Audio, video and picture apps\\"},\\"id\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"io\\":{\\"name\\

":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"is\\":{\\"name\\":\\"Margmi\\\\u00f0lun\\",\\"description\\":\\"Forrit fyrir hj\\\\u00f3

\\\\u00f0, myndir og myndskei\\\\u00f0\\"},\\"it\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Applicazioni per audio, video e immagini\\"},\\"ja\\":{\\"name

\\":\\"\\\\u30de\\\\u30eb\\\\u30c1\\\\u30e1\\\\u30c7\\\\u30a3\\\\u30a2\\",\\"description\\":\\"\\\\u30aa\\\\u30fc\\\\u30c7\\\\u30a3\\\\u30aa\\\\u3001\\\\u30d3\\\\u30c7\\\\u30aa\\\\u3001\\

\\u753b\\\\u50cf\\\\u30a2\\\\u30d7\\\\u30ea\\"},\\"ka\\":{\\"name\\":\\"\\\\u10db\\\\u10e3\\\\u10da\\\\u10e2\\\\u10d8\\\\u10db\\\\u10d4\\\\u10d3\\\\u10d8\\\\u10d0\\",\\"description\\":

\\"\\\\u10d0\\\\u10e3\\\\u10d3\\\\u10d8\\\\u10dd, \\\\u10d5\\\\u10d8\\\\u10d3\\\\u10d4\\\\u10dd \\\\u10d3\\\\u10d0 \\\\u10e1\\\\u10e3\\\\u10e0\\\\u10d0\\\\u10d7\\\\u10d4\\\\u10d1\\\\u10d8

\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio,

 video and picture apps\\"},\\"kk\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"km\\":{\\"name\\":\\"Multimedia\\",\\"de

scription\\":\\"Audio, video and picture apps\\"},\\"kn\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ko\\":{\\"name\\"

:\\"\\\\uba40\\\\ud2f0\\\\ubbf8\\\\ub514\\\\uc5b4\\",\\"description\\":\\"\\\\uc624\\\\ub514\\\\uc624, \\\\ube44\\\\ub514\\\\uc624, \\\\uc0ac\\\\uc9c4 \\\\uc571\\"},\\"lb\\":{\\"name\\

":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"lt\\":{\\"name\\":\\"Multimedija\\",\\"description\\":\\"Garso, vaizdo ir paveiksl\\\\

u0117li\\\\u0173 program\\\\u0117l\\\\u0117s\\"},\\"lv\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"mk\\":{\\"name\\":\\"Mu

ltimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ml\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\

"mn\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"mr\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video a

nd picture apps\\"},\\"my\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"nb\\":{\\"name\\":\\"Multimedia\\",\\"descriptio

n\\":\\"Apper for lyd, film og bilde\\"},\\"ne\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"te\\":{\\"name\\":\\"Multim

edia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"th\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"tr\\

":{\\"name\\":\\"\\\\u00c7oklu Ortam\\",\\"description\\":\\"Ses, g\\\\u00f6r\\\\u00fcnt\\\\u00fc ve foto\\\\u011fraf uygulamalar\\\\u0131\\"},\\"tt\\":{\\"name\\":\\"Mult

imedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"udm\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"

uk\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ar\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video an

d picture apps\\"},\\"ast\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"az\\":{\\"name\\":\\"Multimedia\\",\\"descriptio

n\\":\\"Audio, video and picture apps\\"},\\"bg\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"be\\":{\\"name\\":\\"Multi

media\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"ur\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"vi

\\":{\\"name\\":\\"Gi\\\\u1ea3i tr\\\\u00ed \\\\u0111a ph\\\\u01b0\\\\u01a1ng ti\\\\u1ec7n\\",\\"description\\":\\"\\\\u1ee8ng d\\\\u1ee5ng \\\\u00e2m thanh, video v\\\\u00e0

 \\\\u1ea3nh\\"},\\"zh-hans\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"zh-hant\\":{\\"name\\":\\"Multimedia\\",\\"descr

iption\\":\\"Audio, video and picture apps\\"},\\"bn\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"br\\":{\\"name\\":\\"

Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"bs\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"}

,\\"ca\\":{\\"name\\":\\"Multim\\\\u00e8dia\\",\\"description\\":\\"Aplicacions d'\\\\u00e0udio, v\\\\u00eddeo i fotografies\\"},\\"cs\\":{\\"name\\":\\"Multim\\\\u00e9d

ia\\",\\"description\\":\\"Aplikace pro zvuk, video a obr\\\\u00e1zky\\"},\\"nl\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video en afbeelding ap

ps\\"},\\"cy\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"da\\":{\\"name\\":\\"Multimedie\\",\\"description\\":\\"Lyd, bi

llede og video apps\\"},\\"de\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio-, Video- und Bilder-Apps\\"},\\"dsb\\":{\\"name\\":\\"Multimedia\\",\\"desc

ription\\":\\"Audio, video and picture apps\\"},\\"el\\":{\\"name\\":\\"\\\\u03a0\\\\u03bf\\\\u03bb\\\\u03c5\\\\u03bc\\\\u03ad\\\\u03c3\\\\u03b1\\",\\"description\\":\\"\\\\u03

95\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03ae\\\\u03c7\\\\u03bf\\\\u03c5, \\\\u03b2\\\\u03af\\\\u03bd\\\\u03c4\\\\u03b5\\\\u03bf \\\\u03ba\\\\u03b1

\\\\u03b9 \\\\u03b5\\\\u03b9\\\\u03ba\\\\u03cc\\\\u03bd\\\\u03b1\\\\u03c2\\"},\\"eo\\":{\\"name\\":\\"A\\\\u016ddvida\\\\u0135oj\\",\\"description\\":\\"A\\\\u016dda\\\\u0135o, vid

ea\\\\u0135o kaj bildoj\\"},\\"es\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Apps de sonido, video e im\\\\u00e1genes\\"},\\"es-ar\\":{\\"name\\":\\"Multime

dia\\",\\"description\\":\\"Aplicaciones de audio, video e imagenes\\"},\\"es-co\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Aplicaciones de audio, vid

eo e im\\\\u00e1genes\\"},\\"es-mx\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Aplicaciones de audio, video e im\\\\u00e1genes\\"},\\"es-ni\\":{\\"name\\":\\

"Multimedia\\",\\"description\\":\\"Aplicaciones de audio, video e im\\\\u00e1genes\\"},\\"es-ve\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Apps de soni

do, video e im\\\\u00e1genes\\"},\\"et\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"eu\\":{\\"name\\":\\"Multimedia\\",\\

"description\\":\\"Audio, bideo eta argazki app-ak\\"},\\"fa\\":{\\"name\\":\\"\\\\u0686\\\\u0646\\\\u062f \\\\u0631\\\\u0633\\\\u0627\\\\u0646\\\\u0647 \\\\u0627\\\\u06cc\\",

\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u0635\\\\u0648\\\\u062a\\\\u06cc \\\\u060c \\\\u0648\\\\u06cc\\\\u062f\\\\u06

cc\\\\u0648\\\\u06cc\\\\u06cc \\\\u0648 \\\\u062a\\\\u0635\\\\u0648\\\\u06cc\\\\u0631\\\\u06cc\\"},\\"nn\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and p

icture apps\\"},\\"fi\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"\\\\u00c4\\\\u00e4ni-, video- ja kuvasovellukset\\"},\\"os\\":{\\"name\\":\\"Multimedia\\",\\

"description\\":\\"Audio, video and picture apps\\"},\\"pa\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"fr\\":{\\"nam

e\\":\\"Multim\\\\u00e9dia\\",\\"description\\":\\"Applications audio, vid\\\\u00e9o et image\\"},\\"pl\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Aplikacje

 graficzne, audio i wideo\\"},\\"pt\\":{\\"name\\":\\"Multim\\\\u00e9dia\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00f5es de \\\\u00c1udio, V\\\\u00eddeo e Imagens\\

"},\\"pt-br\\":{\\"name\\":\\"Multim\\\\u00eddia\\",\\"description\\":\\"Aplicativos de \\\\u00e1udio, v\\\\u00eddeo e imagem\\"},\\"ro\\":{\\"name\\":\\"Multimedia\\",

\\"description\\":\\"Audio, video and picture apps\\"},\\"gl\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de son, v\\\\u00eddeo e imaxe

s\\"},\\"he\\":{\\"name\\":\\"\\\\u05de\\\\u05d5\\\\u05dc\\\\u05d8\\\\u05d9\\\\u05de\\\\u05d3\\\\u05d9\\\\u05d4\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u

05d5\\\\u05e0\\\\u05d9 \\\\u05e9\\\\u05de\\\\u05e2, \\\\u05d5\\\\u05d9\\\\u05d3\\\\u05d0\\\\u05d5 \\\\u05d5\\\\u05ea\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d5\\\\u05ea\\"},\\"hi\\":{\\"name\\

":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"hr\\":{\\"name\\":\\"Multimedija\\",\\"description\\":\\"Audio, video i slikovne apl

ikacije\\"},\\"hsb\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041c\\\\u0443\\\\u043b\\\\u044

2\\\\u0438\\\\u043c\\\\u0435\\\\u0434\\\\u0438\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0

437\\\\u0430 \\\\u0430\\\\u0443\\\\u0434\\\\u0438\\\\u043e, \\\\u0432\\\\u0438\\\\u0434\\\\u0435\\\\u043e \\\\u0438 \\\\u0441\\\\u043b\\\\u0438\\\\u043a\\\\u0435\\"},\\"sv\\":{\\"name\\

":\\"Multimedia\\",\\"description\\":\\"Ljud, video, och bildappar\\"},\\"sw\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"

},\\"ta\\":{\\"name\\":\\"Multimedia\\",\\"description\\":\\"Audio, video and picture apps\\"}}},{\\"id\\":\\"office\\",\\"translations\\":{\\"ga\\":{\\"name\\":\\"Off

ice & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"fy\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing 

apps\\"},\\"gd\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"en\\":{\\"name\\":\\"Office & text\\",\\"description\\"

:\\"Office and text processing apps\\"},\\"af\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ru\\":{\\"name\\":\\"\\

\\u041e\\\\u0444\\\\u0438\\\\u0441 \\\\u0438 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\",\\"description\\":\\"\\\\u041e\\\\u0444\\\\u0438\\\\u0441\\\\u043d\\\\u044b\\\\u0435 \\\\u0

43f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f \\\\u0438 \\\\u043f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f 

\\\\u0434\\\\u043b\\\\u044f \\\\u043e\\\\u0431\\\\u0440\\\\u0430\\\\u0431\\\\u043e\\\\u0442\\\\u043a\\\\u0438 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u0430\\"},\\"sk\\":{\\"name

\\":\\"Kancel\\\\u00e1ria & text\\",\\"description\\":\\"Kancel\\\\u00e1rske a textov\\\\u00e9 aplik\\\\u00e1cie\\"},\\"sl\\":{\\"name\\":\\"Pisarni\\\\u0161ka orodja\\"

,\\"description\\":\\"Programi za pisarni\\\\u0161ke naloge\\"},\\"sq\\":{\\"name\\":\\"Zyre dhe tekst\\",\\"description\\":\\"Aplikacione p\\\\u00ebr zyra dhe pro

cesimin e teksteve\\"},\\"hu\\":{\\"name\\":\\"Iroda \\\\u00e9s sz\\\\u00f6veg\\",\\"description\\":\\"Irodai \\\\u00e9s sz\\\\u00f6vegfeldolgoz\\\\u00f3 alkalmaz\\\\u0

0e1sok\\"},\\"hy\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ia\\":{\\"name\\":\\"Office & text\\",\\"description

\\":\\"Office and text processing apps\\"},\\"id\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"io\\":{\\"name\\":\\

"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"is\\":{\\"name\\":\\"Skrifstofuforrit og texti\\",\\"description\\":\\"Skrifstofuf

orrit og textavinnsluforrit\\"},\\"it\\":{\\"name\\":\\"Ufficio e testo\\",\\"description\\":\\"Applicazione per ufficio ed elaborazione di testi\\"},\\"ja\\":

{\\"name\\":\\"Office & \\\\u30c6\\\\u30ad\\\\u30b9\\\\u30c8\\",\\"description\\":\\"Office\\\\u3068\\\\u30c6\\\\u30ad\\\\u30b9\\\\u30c8\\\\u51e6\\\\u7406\\\\u30a2\\\\u30d7\\\\u30ea

\\\\u30b1\\\\u30fc\\\\u30b7\\\\u30e7\\\\u30f3\\"},\\"ka\\":{\\"name\\":\\"\\\\u10dd\\\\u10e4\\\\u10d8\\\\u10e1\\\\u10d8 \\\\u10d3\\\\u10d0 \\\\u10e2\\\\u10d4\\\\u10e5\\\\u10e1\\\\u10e2\\\\

u10d8\\",\\"description\\":\\"\\\\u10dd\\\\u10e4\\\\u10d8\\\\u10e1\\\\u10d8 \\\\u10d3\\\\u10d0 \\\\u10e2\\\\u10d4\\\\u10e5\\\\u10e1\\\\u10e2\\\\u10d8\\\\u10e1 \\\\u10d3\\\\u10d0\\\\u10

db\\\\u10e3\\\\u10e8\\\\u10d0\\\\u10d5\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\

":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"kk\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and

 text processing apps\\"},\\"km\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"kn\\":{\\"name\\":\\"Office & text\\

",\\"description\\":\\"Office and text processing apps\\"},\\"ko\\":{\\"name\\":\\"\\\\uc624\\\\ud53c\\\\uc2a4 \\\\ubc0f \\\\ud14d\\\\uc2a4\\\\ud2b8\\",\\"description\\":\\"

\\\\uc624\\\\ud53c\\\\uc2a4 \\\\ubc0f \\\\ud14d\\\\uc2a4\\\\ud2b8 \\\\ucc98\\\\ub9ac \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text

 processing apps\\"},\\"lt\\":{\\"name\\":\\"Ra\\\\u0161tin\\\\u0117 ir tekstas\\",\\"description\\":\\"Ra\\\\u0161tin\\\\u0117s ir teksto apdorojimo program\\\\u0117

l\\\\u0117s\\"},\\"lv\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"mk\\":{\\"name\\":\\"Office & text\\",\\"descript

ion\\":\\"Office and text processing apps\\"},\\"ml\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"mn\\":{\\"name\\

":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"mr\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text proc

essing apps\\"},\\"my\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"nb\\":{\\"name\\":\\"Kontorst\\\\u00f8tte og te

kst\\",\\"description\\":\\"Apper for kontorst\\\\u00f8tte og tekstbehandling\\"},\\"ne\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text pr

ocessing apps\\"},\\"te\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"th\\":{\\"name\\":\\"Office & text\\",\\"desc

ription\\":\\"Office and text processing apps\\"},\\"tr\\":{\\"name\\":\\"Ofis ve Metin\\",\\"description\\":\\"Ofis ve metin i\\\\u015fleme uygulamalar\\\\u0131\\

"},\\"tt\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"udm\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"O

ffice and text processing apps\\"},\\"uk\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ar\\":{\\"name\\":\\"Offic

e & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ast\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing a

pps\\"},\\"az\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"bg\\":{\\"name\\":\\"Office & text\\",\\"description\\":

\\"Office and text processing apps\\"},\\"be\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ur\\":{\\"name\\":\\"Of

fice & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"vi\\":{\\"name\\":\\"V\\\\u0103n ph\\\\u00f2ng v\\\\u00e0 v\\\\u0103n b\\\\u1ea3n\\",\\"descr

iption\\":\\"\\\\u1ee8ng d\\\\u1ee5ng x\\\\u1eed l\\\\u00fd cho v\\\\u0103n ph\\\\u00f2ng v\\\\u00e0 v\\\\u0103n b\\\\u1ea3n\\"},\\"zh-hans\\":{\\"name\\":\\"Office & text\\

",\\"description\\":\\"Office and text processing apps\\"},\\"zh-hant\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"

},\\"bn\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"br\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Off

ice and text processing apps\\"},\\"bs\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ca\\":{\\"name\\":\\"Oficina

 i textos\\",\\"description\\":\\"Apps d\\\\u2019oficina i processament de textos\\"},\\"cs\\":{\\"name\\":\\"Kancel\\\\u00e1\\\\u0159 a text\\",\\"description\\":\\"

Aplikace pro kancel\\\\u00e1\\\\u0159 a zpracov\\\\u00e1n\\\\u00ed textu\\"},\\"cy\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processin

g apps\\"},\\"da\\":{\\"name\\":\\"Kontor & tekstbehandling\\",\\"description\\":\\"Apps til kontor og tekstbehandling\\"},\\"de\\":{\\"name\\":\\"B\\\\u00fcro & Te

xt\\",\\"description\\":\\"B\\\\u00fcro- und Textverarbeitungs-Apps\\"},\\"dsb\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing 

apps\\"},\\"el\\":{\\"name\\":\\"\\\\u0393\\\\u03c1\\\\u03b1\\\\u03c6\\\\u03b5\\\\u03af\\\\u03bf & \\\\u03ba\\\\u03b5\\\\u03af\\\\u03bc\\\\u03b5\\\\u03bd\\\\u03bf\\",\\"description\\"

:\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03b3\\\\u03c1\\\\u03b1\\\\u03c6\\\\u03b5\\\\u03af\\\\u03bf\\\\u03c5 \\\\u03ba\\\\u03b1\\\\u03b9 

\\\\u03b5\\\\u03c0\\\\u03b5\\\\u03be\\\\u03b5\\\\u03c1\\\\u03b3\\\\u03b1\\\\u03c3\\\\u03af\\\\u03b1\\\\u03c2 \\\\u03ba\\\\u03b5\\\\u03b9\\\\u03bc\\\\u03ad\\\\u03bd\\\\u03bf\\\\u03c5 \\"},

\\"eo\\":{\\"name\\":\\"Oficejo kaj teksto\\",\\"description\\":\\"Oficeja programaro kaj tekstotraktado\\"},\\"es\\":{\\"name\\":\\"Oficina y texto\\",\\"descript

ion\\":\\"Apps de oficina y procesado de texto\\"},\\"es-ar\\":{\\"name\\":\\"Oficina & texto\\",\\"description\\":\\"Aplicaciones de procesamiento de texto y

 oficina\\"},\\"es-co\\":{\\"name\\":\\"Oficina & texto\\",\\"description\\":\\"Aplicaciones de procesamiento de texto y oficina\\"},\\"es-mx\\":{\\"name\\":\\"Of

icina & texto\\",\\"description\\":\\"Aplicaciones de procesamiento de texto y oficina\\"},\\"nl\\":{\\"name\\":\\"Office & tekst\\",\\"description\\":\\"Office

 en tekstverwerkingsapps\\"},\\"es-ni\\":{\\"name\\":\\"Oficina & texto\\",\\"description\\":\\"Aplicaciones de procesamiento de texto y oficina\\"},\\"es-ve\\

":{\\"name\\":\\"Oficina y texto\\",\\"description\\":\\"Apps de oficina y procesado de texto\\"},\\"et\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Off

ice and text processing apps\\"},\\"eu\\":{\\"name\\":\\"Bulegoa eta testua\\",\\"description\\":\\"Bulegoak eta testu prozesatzaileen app-ak\\"},\\"fa\\":{\\"n

ame\\":\\"\\\\u062f\\\\u0641\\\\u062a\\\\u0631 \\\\u0648 \\\\u0645\\\\u062a\\\\u0646\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\

u06cc \\\\u0627\\\\u062f\\\\u0627\\\\u0631\\\\u06cc \\\\u0648 \\\\u067e\\\\u0631\\\\u062f\\\\u0627\\\\u0632\\\\u0634 \\\\u0645\\\\u062a\\\\u0646\\"},\\"nn\\":{\\"name\\":\\"Office & 

text\\",\\"description\\":\\"Office and text processing apps\\"},\\"fi\\":{\\"name\\":\\"Toimisto & teksti\\",\\"description\\":\\"Toimisto- ja tekstink\\\\u00e4s

ittelysovellukset\\"},\\"os\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"pa\\":{\\"name\\":\\"Office & text\\",\\"

description\\":\\"Office and text processing apps\\"},\\"pl\\":{\\"name\\":\\"Biuro i tekst\\",\\"description\\":\\"Aplikacje biurowe i przetwarzania tekstu\\"

},\\"pt\\":{\\"name\\":\\"Escrit\\\\u00f3rio & texto\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00f5es de escrit\\\\u00f3rio e processamento de texto\\"},\\"pt-br\\"

:{\\"name\\":\\"Escrit\\\\u00f3rio & texto\\",\\"description\\":\\"Aplicativos para processamento de Office e texto\\"},\\"ro\\":{\\"name\\":\\"Office & text\\",\\

"description\\":\\"Office and text processing apps\\"},\\"fr\\":{\\"name\\":\\"Bureautique & texte\\",\\"description\\":\\"Applications de bureautique et de t

raitement de texte\\"},\\"gl\\":{\\"name\\":\\"Oficina e texto\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de oficina e de procesamento de texto\\"},\\"he\\":{\\"

name\\":\\"\\\\u05db\\\\u05dc\\\\u05d9\\\\u05dd \\\\u05de\\\\u05e9\\\\u05e8\\\\u05d3\\\\u05d9\\\\u05d9\\\\u05dd \\\\u05d5\\\\u05d8\\\\u05e7\\\\u05e1\\\\u05d8\\",\\"description\\":\\"\\\\

u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9\\\\u05dd \\\\u05dc\\\\u05e2\\\\u05d9\\\\u05d1\\\\u05d5\\\\u05d3 \\\\u05d8\\\\u05e7\\\\u05e1\\\\u05d8 \\\\u05d5\\\\u05

db\\\\u05dc\\\\u05d9\\\\u05dd \\\\u05de\\\\u05e9\\\\u05e8\\\\u05d3\\\\u05d9\\\\u05d9\\\\u05dd\\"},\\"hi\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text 

processing apps\\"},\\"hr\\":{\\"name\\":\\"Ured i tekst\\",\\"description\\":\\"Uredske aplikacije i aplikacije obradu teksta\\"},\\"hsb\\":{\\"name\\":\\"Office

 & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"sr\\":{\\"name\\":\\"\\\\u041a\\\\u0430\\\\u043d\\\\u0446\\\\u0435\\\\u043b\\\\u0430\\\\u0440\\\\u0438\\

\\u0458\\\\u0430 \\\\u0438 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u04

35 \\\\u0437\\\\u0430 \\\\u043e\\\\u0431\\\\u0440\\\\u0430\\\\u0434\\\\u0443 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u0430 \\\\u0438 \\\\u0440\\\\u0430\\\\u0434 \\\\u0443 \\\\u0

43a\\\\u0430\\\\u043d\\\\u0446\\\\u0435\\\\u043b\\\\u0430\\\\u0440\\\\u0438\\\\u0458\\\\u0438\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041a\\\\u0430\\\\u043d\\\\u0446\\\\u0435\\\\u043b\\\\u

0430\\\\u0440\\\\u0438\\\\u0458\\\\u0430 \\\\u0438 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446

\\\\u0438\\\\u0458\\\\u0435 \\\\u0437\\\\u0430 \\\\u043e\\\\u0431\\\\u0440\\\\u0430\\\\u0434\\\\u0443 \\\\u0442\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u0430 \\\\u0438 \\\\u0440\\\\u0430\\

\\u0434 \\\\u0443 \\\\u043a\\\\u0430\\\\u043d\\\\u0446\\\\u0435\\\\u043b\\\\u0430\\\\u0440\\\\u0438\\\\u0458\\\\u0438\\"},\\"sv\\":{\\"name\\":\\"Kontor & text\\",\\"description\\"

:\\"Appar f\\\\u00f6r kontor och texthantering\\"},\\"sw\\":{\\"name\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"},\\"ta\\":{\\"n

ame\\":\\"Office & text\\",\\"description\\":\\"Office and text processing apps\\"}}},{\\"id\\":\\"organization\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Organ

ization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"fr\\":{\\"name\\":\\"Organisation\\",\\"description\\":\\"Applications de ge

stion du temps, de listes de t\\\\u00e2ches et d'agendas\\"},\\"fy\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calen

dar apps\\"},\\"ga\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"gd\\":{\\"name\\":\\"Organization\\",

\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"af\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list a

nd calendar apps\\"},\\"ru\\":{\\"name\\":\\"\\\\u041e\\\\u0440\\\\u0433\\\\u0430\\\\u043d\\\\u0438\\\\u0437\\\\u0430\\\\u0446\\\\u0438\\\\u044f\\",\\"description\\":\\"\\\\u041f\\\\

u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f \\\\u043f\\\\u043e \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u043b\\\\u0435\\\\u043d\\\\u0438\\\\u044

e \\\\u0432\\\\u0440\\\\u0435\\\\u043c\\\\u0435\\\\u043d\\\\u0435\\\\u043c, \\\\u0441\\\\u043f\\\\u0438\\\\u0441\\\\u043e\\\\u043a \\\\u0437\\\\u0430\\\\u0434\\\\u0430\\\\u0447 \\\\u0438

 \\\\u043a\\\\u0430\\\\u043b\\\\u0435\\\\u043d\\\\u0434\\\\u0430\\\\u0440\\\\u044c\\"},\\"sk\\":{\\"name\\":\\"Organiz\\\\u00e1cia\\",\\"description\\":\\"Aplik\\\\u00e1cie na or

ganiz\\\\u00e1ciu \\\\u010dasu, spr\\\\u00e1vu \\\\u00faloh a kalend\\\\u00e1rov\\"},\\"sl\\":{\\"name\\":\\"Organizacija\\",\\"description\\":\\"Upravljanje s \\\\u010

dasom, seznami nalog in koledarji\\"},\\"sq\\":{\\"name\\":\\"Organizate\\",\\"description\\":\\"Aplikacion per menaxhimin e kohes , listat per gjerat qe du

hen bere dhe kalendar\\"},\\"hu\\":{\\"name\\":\\"Szervezet\\",\\"description\\":\\"Id\\\\u0151beoszt\\\\u00e1s, teend\\\\u0151lista \\\\u00e9s napt\\\\u00e1r alkalma

z\\\\u00e1sok\\"},\\"hy\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"ia\\":{\\"name\\":\\"Organization

\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"id\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo lis

t and calendar apps\\"},\\"io\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"is\\":{\\"name\\":\\"Stof

nun\\\\\\/Samt\\\\u00f6k\\\\\\/F\\\\u00e9lag\\",\\"description\\":\\"T\\\\u00edmastj\\\\u00f3rnun, verkefnalistar og dagatalaforrit\\"},\\"it\\":{\\"name\\":\\"Organizzaz

ione\\",\\"description\\":\\"Applicazioni di gestione del tempo, elenco delle cose da fare e calendario\\"},\\"ja\\":{\\"name\\":\\"\\\\u5171\\\\u540c\\\\u4f5c\\\\u

696d\\",\\"description\\":\\"\\\\u6642\\\\u9593\\\\u7ba1\\\\u7406\\\\u3001Todo\\\\u30ea\\\\u30b9\\\\u30c8\\\\u3001\\\\u30ab\\\\u30ec\\\\u30f3\\\\u30c0\\\\u30fc\\\\u30a2\\\\u30d7\\\\u30

ea\\"},\\"ka\\":{\\"name\\":\\"\\\\u10dd\\\\u10e0\\\\u10d2\\\\u10d0\\\\u10dc\\\\u10d8\\\\u10d6\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d0\\",\\"description\\":\\"\\\\u10d3\\\\u10e0\\\\u10dd\\\\

u10d8\\\\u10e1 \\\\u10db\\\\u10d4\\\\u10dc\\\\u10d4\\\\u10ef\\\\u10db\\\\u10d4\\\\u10dc\\\\u10e2\\\\u10d8, \\\\u10d3\\\\u10d0\\\\u10d5\\\\u10d0\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d4\\\\u10

d1\\\\u10d8\\\\u10e1 \\\\u10e1\\\\u10d8\\\\u10d0 \\\\u10d3\\\\u10d0 \\\\u10d9\\\\u10d0\\\\u10da\\\\u10d4\\\\u10dc\\\\u10d3\\\\u10e0\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8

\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"kab\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar 

apps\\"},\\"kk\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"km\\":{\\"name\\":\\"Organization\\",\\"de

scription\\":\\"Time management, Todo list and calendar apps\\"},\\"kn\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and c

alendar apps\\"},\\"ko\\":{\\"name\\":\\"\\\\uac1c\\\\uc778 \\\\uc815\\\\ubcf4 \\\\uad00\\\\ub9ac\\",\\"description\\":\\"\\\\uc2dc\\\\uac04 \\\\uad00\\\\ub9ac, \\\\ud560 \\\\uc77c

, \\\\uce98\\\\ub9b0\\\\ub354 \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"lt\\":{\\"n

ame\\":\\"Organizavimas\\",\\"description\\":\\"Laiko planavimo, darb\\\\u0173 s\\\\u0105ra\\\\u0161o ir kalendoriaus programos\\"},\\"lv\\":{\\"name\\":\\"Organiza

tion\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"mk\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo

 list and calendar apps\\"},\\"ml\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"mn\\":{\\"name\\":\\"

Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"mr\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time manageme

nt, Todo list and calendar apps\\"},\\"my\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"nb\\":{\\"n

ame\\":\\"Organisering\\",\\"description\\":\\"Apper for tidsstyring, oppgaveliste og kalender\\"},\\"ne\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Ti

me management, Todo list and calendar apps\\"},\\"te\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},

\\"th\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"tr\\":{\\"name\\":\\"Kurulu\\\\u015f\\",\\"descripti

on\\":\\"Zaman y\\\\u00f6netimi,\\\\u00a0g\\\\u00f6rev listesi ve takvim uygulamalar\\\\u0131\\"},\\"tt\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time ma

nagement, Todo list and calendar apps\\"},\\"udm\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"uk

\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"ar\\":{\\"name\\":\\"Organization\\",\\"description\\":

\\"Time management, Todo list and calendar apps\\"},\\"ast\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar app

s\\"},\\"az\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"bg\\":{\\"name\\":\\"Organization\\",\\"descr

iption\\":\\"Time management, Todo list and calendar apps\\"},\\"be\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and cale

ndar apps\\"},\\"ur\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"vi\\":{\\"name\\":\\"T\\\\u1ed5 ch\\\\u

1ee9c\\",\\"description\\":\\"\\\\u1ee8ng d\\\\u1ee5ng u\\\\u1ea3n l\\\\u00fd th\\\\u1eddi gian, danh s\\\\u00e1ch c\\\\u1ea7n l\\\\u00e0m v\\\\u00e0 l\\\\u1ecbch\\"},\\"zh

\-hans\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"zh-hant\\":{\\"name\\":\\"Organization\\",\\"desc

ription\\":\\"Time management, Todo list and calendar apps\\"},\\"bn\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and cal

endar apps\\"},\\"br\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"bs\\":{\\"name\\":\\"Organization\\

",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"ca\\":{\\"name\\":\\"Organitzaci\\\\u00f3\\",\\"description\\":\\"Aplicacions de gesti

\\\\u00f3 del temps, llista de tasques i calendari\\"},\\"cs\\":{\\"name\\":\\"Organizov\\\\u00e1n\\\\u00ed\\",\\"description\\":\\"Aplikace pro spr\\\\u00e1vu \\\\u0

10dasu, pl\\\\u00e1nov\\\\u00e1n\\\\u00ed a kalend\\\\u00e1\\\\u0159e\\"},\\"cy\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and 

calendar apps\\"},\\"da\\":{\\"name\\":\\"Organisering\\",\\"description\\":\\"Tidsstyring, todo list og kalender apps\\"},\\"de\\":{\\"name\\":\\"Organisation\\",

\\"description\\":\\"Zeitmanagement-, Aufgabenlisten- und Kalender-Apps\\"},\\"dsb\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo

 list and calendar apps\\"},\\"el\\":{\\"name\\":\\"\\\\u039f\\\\u03c1\\\\u03b3\\\\u03b1\\\\u03bd\\\\u03b9\\\\u03c3\\\\u03bc\\\\u03cc\\\\u03c2\\",\\"description\\":\\"\\\\u0395\\\\

u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03b4\\\\u03b9\\\\u03b1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03c1\\\\u03b9\\\\u03c3\\\\u03b7\\\\u03c2 \\\\u03c7\\\\u03c

1\\\\u03cc\\\\u03bd\\\\u03bf\\\\u03c5, \\\\u03bb\\\\u03b9\\\\u03c3\\\\u03c4\\\\u03ce\\\\u03bd \\\\u03b5\\\\u03ba\\\\u03ba\\\\u03c1\\\\u03b5\\\\u03bc\\\\u03bf\\\\u03c4\\\\u03ae\\\\u03c4\\\\

u03c9\\\\u03bd \\\\u03ba\\\\u03b1\\\\u03b9 \\\\u03b7\\\\u03bc\\\\u03b5\\\\u03c1\\\\u03bf\\\\u03bb\\\\u03cc\\\\u03b3\\\\u03b9\\\\u03b1\\"},\\"eo\\":{\\"name\\":\\"Organiza\\\\u0135o\\"

,\\"description\\":\\"Tempadministrado, listo de farenda\\\\u0135oj kaj kalendaro\\"},\\"es\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Apps de 

manejo del tiempo, listas de tareas y calendarios\\"},\\"es-ar\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones de adminsitraci\\\\u0

0f3n del tiempo, lista de pendientes y calendario\\"},\\"es-co\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones de adminsitraci\\\\u0

0f3n del tiempo, lista de pendientes y calendario\\"},\\"es-mx\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones de adminsitraci\\\\u0

0f3n del tiempo, lista de pendientes y calendario\\"},\\"es-ni\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones de adminsitraci\\\\u0

0f3n del tiempo, lista de pendientes y calendario\\"},\\"es-ve\\":{\\"name\\":\\"Organizaci\\\\u00f3n\\",\\"description\\":\\"Apps de manejo del tiempo, lista

s de tareas y calendarios\\"},\\"et\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"eu\\":{\\"name\\":

\\"Antolakuntza\\",\\"description\\":\\"Denboraren kudeaketa, egitekoen zerrenda eta egutegi aplikazioak\\"},\\"nl\\":{\\"name\\":\\"Organisatie\\",\\"descript

ion\\":\\"Tijdmanagement, takenlijsten en agenda apps\\"},\\"fa\\":{\\"name\\":\\"\\\\u0633\\\\u0627\\\\u0632\\\\u0645\\\\u0627\\\\u0646\\",\\"description\\":\\"\\\\u0645\\\\

u062f\\\\u06cc\\\\u0631\\\\u06cc\\\\u062a \\\\u0632\\\\u0645\\\\u0627\\\\u0646 \\\\u060c \\\\u0644\\\\u06cc\\\\u0633\\\\u062a Todo \\\\u0648 \\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u06

45\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u062a\\\\u0642\\\\u0648\\\\u06cc\\\\u0645\\"},\\"nn\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo l

ist and calendar apps\\"},\\"fi\\":{\\"name\\":\\"Organisaatio\\",\\"description\\":\\"Ajanhallinta-, todo-lista- ja kalenterisovellukset\\"},\\"os\\":{\\"name\\

":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"pa\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time mana

gement, Todo list and calendar apps\\"},\\"pl\\":{\\"name\\":\\"Organizacja\\",\\"description\\":\\"Aplikacje do zarz\\\\u0105dzania czasem, listami zada\\\\u01

44 i kalendarze\\"},\\"pt\\":{\\"name\\":\\"Organiza\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00f5es de Gest\\\\u00e3o de tempo, lista de tarefa

s e calend\\\\u00e1rio\\"},\\"pt-br\\":{\\"name\\":\\"Organiza\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplicativos de gerenciamento de tempo, lista de tarefas 

e calend\\\\u00e1rios\\"},\\"ro\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"gl\\":{\\"name\\":\\"Orga

nizaci\\\\u00f3n\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de xesti\\\\u00f3n do tempo, listas de tarefas e calendarios\\"},\\"he\\":{\\"name\\":\\"\\\\u05d0\\\\u05

e8\\\\u05d2\\\\u05d5\\\\u05df\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9 \\\\u05e0\\\\u05d9\\\\u05d4\\\\u05d5\\\\u05dc \\\\u05d6\\\\

u05de\\\\u05e0\\\\u05d9\\\\u05dd, \\\\u05e8\\\\u05e9\\\\u05d9\\\\u05de\\\\u05ea \\\\u05de\\\\u05d8\\\\u05dc\\\\u05d5\\\\u05ea \\\\u05d5\\\\u05dc\\\\u05d5\\\\u05d7 \\\\u05e9\\\\u05e0\\\\u

05d4\\"},\\"hi\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"hr\\":{\\"name\\":\\"Organizacija\\",\\"de

scription\\":\\"Aplikacije za upravljanje vremenom, zadacima i kalendarom\\"},\\"hsb\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, T

odo list and calendar apps\\"},\\"sr\\":{\\"name\\":\\"\\\\u041e\\\\u0440\\\\u0433\\\\u0430\\\\u043d\\\\u0438\\\\u0437\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0430\\",\\"descript

ion\\":\\"\\\\u0423\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0459\\\\u0430\\\\u045a\\\\u0435 \\\\u0432\\\\u0440\\\\u0435\\\\u043c\\\\u0435\\\\u043d\\\\u043e\\\\u043c, TODO \\\\u043b\\\\u0

438\\\\u0441\\\\u0442\\\\u0435 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0441\\\\u0430 \\\\u043a\\\\u0430\\\\u043b\\\\u043

5\\\\u043d\\\\u0434\\\\u0430\\\\u0440\\\\u0438\\\\u043c\\\\u0430\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041e\\\\u0440\\\\u0433\\\\u0430\\\\u043d\\\\u0438\\\\u0437\\\\u0430\\\\u0446\\\\u04

38\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\u0423\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0459\\\\u0430\\\\u045a\\\\u0435 \\\\u0432\\\\u0440\\\\u0435\\\\u043c\\\\u0435\\\\u043d\\\\u

043e\\\\u043c, TODO \\\\u043b\\\\u0438\\\\u0441\\\\u0442\\\\u0435 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0441\\\\u043

0 \\\\u043a\\\\u0430\\\\u043b\\\\u0435\\\\u043d\\\\u0434\\\\u0430\\\\u0440\\\\u0438\\\\u043c\\\\u0430\\"},\\"sv\\":{\\"name\\":\\"Organisering\\",\\"description\\":\\"Tidshanteri

ng, uppgifter och kalender appar\\"},\\"sw\\":{\\"name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"},\\"ta\\":{\\"

name\\":\\"Organization\\",\\"description\\":\\"Time management, Todo list and calendar apps\\"}}},{\\"id\\":\\"search\\",\\"translations\\":{\\"en\\":{\\"name\\":

\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"fr\\":{\\"name\\":\\"Rechercher\\",\\"description\\":\\"Rechercher des applications similaires\\"},\\"

fy\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"ga\\":{\\"name\\":\\"Cuardach\\",\\"description\\":\\"Search related apps\\"},\\"gd\\":{

\\"name\\":\\"Lorg\\",\\"description\\":\\"Search related apps\\"},\\"af\\":{\\"name\\":\\"Soek\\",\\"description\\":\\"Search related apps\\"},\\"ru\\":{\\"name\\":\\"\\

\\u041f\\\\u043e\\\\u0438\\\\u0441\\\\u043a\\",\\"description\\":\\"\\\\u041f\\\\u043e\\\\u0438\\\\u0441\\\\u043a \\\\u043f\\\\u043e\\\\u0434\\\\u0445\\\\u043e\\\\u0434\\\\u044f\\\\u044

9\\\\u0438\\\\u0445 \\\\u043f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u0439\\"},\\"sk\\":{\\"name\\":\\"H\\\\u013eada\\\\u0165\\",\\"description\\":

\\"Vyh\\\\u013eada\\\\u0165 s\\\\u00favisiace aplik\\\\u00e1cie\\"},\\"sl\\":{\\"name\\":\\"Iskanje\\",\\"description\\":\\"Iskalniki in sorodni programi\\"},\\"sq\\":{

\\"name\\":\\"K\\\\u00ebrko\\",\\"description\\":\\"K\\\\u00ebrko aplikacione t\\\\u00eb ngjashme\\"},\\"hu\\":{\\"name\\":\\"Keres\\\\u00e9s\\",\\"description\\":\\"Hason

l\\\\u00f3 alkalmaz\\\\u00e1sok keres\\\\u00e9se\\"},\\"hy\\":{\\"name\\":\\"\\\\u0548\\\\u0580\\\\u0578\\\\u0576\\\\u0578\\\\u0582\\\\u0574\\",\\"description\\":\\"Search rela

ted apps\\"},\\"ia\\":{\\"name\\":\\"Cercar\\",\\"description\\":\\"Search related apps\\"},\\"id\\":{\\"name\\":\\"Cari\\",\\"description\\":\\"Search related apps\\"

},\\"io\\":{\\"name\\":\\"Serchar\\",\\"description\\":\\"Search related apps\\"},\\"is\\":{\\"name\\":\\"Leita\\",\\"description\\":\\"Leita a\\\\u00f0 tengdum forrit

um\\"},\\"it\\":{\\"name\\":\\"Cerca\\",\\"description\\":\\"Cerca le applicazioni correlate\\"},\\"ja\\":{\\"name\\":\\"\\\\u691c\\\\u7d22\\",\\"description\\":\\"\\\\u95a

2\\\\u9023\\\\u30a2\\\\u30d7\\\\u30ea\\\\u3092\\\\u691c\\\\u7d22\\"},\\"ka\\":{\\"name\\":\\"\\\\u10eb\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d0\\",\\"description\\":\\"Search related ap

ps\\"},\\"kab\\":{\\"name\\":\\"Anadi\\",\\"description\\":\\"Search related apps\\"},\\"kk\\":{\\"name\\":\\"\\\\u0406\\\\u0437\\\\u0434\\\\u0435\\\\u0443\\",\\"description\\

":\\"Search related apps\\"},\\"km\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"kn\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Sear

ch related apps\\"},\\"ko\\":{\\"name\\":\\"\\\\uac80\\\\uc0c9\\",\\"description\\":\\"\\\\uad00\\\\ub828\\\\ub41c \\\\uc571\\\\uc744 \\\\uac80\\\\uc0c9\\\\ud569\\\\ub2c8\\\\ub2e4\\

"},\\"lb\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"lt\\":{\\"name\\":\\"Paie\\\\u0161ka\\",\\"description\\":\\"Ie\\\\u0161koti susijus

i\\\\u0173 program\\\\u0117li\\\\u0173\\"},\\"lv\\":{\\"name\\":\\"Mekl\\\\u0113t\\",\\"description\\":\\"Search related apps\\"},\\"mk\\":{\\"name\\":\\"\\\\u041f\\\\u0440\\\\

u0435\\\\u0431\\\\u0430\\\\u0440\\\\u0430\\\\u0458\\",\\"description\\":\\"Search related apps\\"},\\"ml\\":{\\"name\\":\\"\\\\u0d2a\\\\u0d30\\\\u0d24\\\\u0d41\\\\u0d15\\",\\"des

cription\\":\\"Search related apps\\"},\\"mn\\":{\\"name\\":\\"\\\\u0425\\\\u0430\\\\u0439\\\\u043b\\\\u0442\\",\\"description\\":\\"Search related apps\\"},\\"mr\\":{\\"na

me\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"my\\":{\\"name\\":\\"\\\\u101b\\\\u103e\\\\u102c\\\\u1016\\\\u103d\\\\u1031\\",\\"description\\":\\"Search 

related apps\\"},\\"nb\\":{\\"name\\":\\"S\\\\u00f8k\\",\\"description\\":\\"S\\\\u00f8k etter relaterte apper\\"},\\"ne\\":{\\"name\\":\\"\\\\u0916\\\\u094b\\\\u091c\\\\u094

d\\\\u0928\\\\u0941\\\\u0939\\\\u094b\\\\u0938\\",\\"description\\":\\"Search related apps\\"},\\"te\\":{\\"name\\":\\"\\\\u0c35\\\\u0c46\\\\u0c24\\\\u0c41\\\\u0c15\\\\u0c41\\",\\"

description\\":\\"Search related apps\\"},\\"th\\":{\\"name\\":\\"\\\\u0e04\\\\u0e49\\\\u0e19\\\\u0e2b\\\\u0e32\\",\\"description\\":\\"Search related apps\\"},\\"tr\\":{\\

"name\\":\\"Ara\\",\\"description\\":\\"\\\\u0130li\\\\u015fkili uygulamalarda arama\\"},\\"tt\\":{\\"name\\":\\"\\\\u042d\\\\u0437\\\\u043b\\\\u04d9\\\\u0440\\\\u0433\\\\u04d9

\\",\\"description\\":\\"Search related apps\\"},\\"udm\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"uk\\":{\\"name\\":\\"\\\\u041f\\\\u043

e\\\\u0448\\\\u0443\\\\u043a\\",\\"description\\":\\"Search related apps\\"},\\"ar\\":{\\"name\\":\\"\\\\u0628\\\\u062d\\\\u062b\\",\\"description\\":\\"Search related apps

\\"},\\"ast\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search related apps\\"},\\"az\\":{\\"name\\":\\"Axtar\\\\u0131\\\\u015f\\",\\"description\\":\\"Search relate

d apps\\"},\\"bg\\":{\\"name\\":\\"\\\\u0422\\\\u044a\\\\u0440\\\\u0441\\\\u0435\\\\u043d\\\\u0435\\",\\"description\\":\\"Search related apps\\"},\\"be\\":{\\"name\\":\\"\\\\u04

28\\\\u0443\\\\u043a\\\\u0430\\\\u0446\\\\u044c\\",\\"description\\":\\"Search related apps\\"},\\"ur\\":{\\"name\\":\\"\\\\u062a\\\\u0644\\\\u0627\\\\u0634 \\\\u06a9\\\\u0631\\\\u

06cc\\\\u06ba\\",\\"description\\":\\"Search related apps\\"},\\"vi\\":{\\"name\\":\\"T\\\\u00ecm\\",\\"description\\":\\"T\\\\u00ecm ki\\\\u1ebfm c\\\\u00e1c \\\\u1ee9ng d

\\\\u1ee5ng li\\\\u00ean quan\\"},\\"zh-hans\\":{\\"name\\":\\" \\\\u641c\\\\u7d22\\",\\"description\\":\\"Search related apps\\"},\\"zh-hant\\":{\\"name\\":\\"\\\\u641c\\\\u

5c0b\\",\\"description\\":\\"Search related apps\\"},\\"bn\\":{\\"name\\":\\"\\\\u09b8\\\\u09be\\\\u09b0\\\\u09cd\\\\u099a\\",\\"description\\":\\"Search related apps\\"},

\\"br\\":{\\"name\\":\\"Klask\\",\\"description\\":\\"Search related apps\\"},\\"bs\\":{\\"name\\":\\"Pretraga\\",\\"description\\":\\"Search related apps\\"},\\"ca\\":

{\\"name\\":\\"Cerca\\",\\"description\\":\\"Cerca aplicacions relacionades\\"},\\"cs\\":{\\"name\\":\\"Hled\\\\u00e1n\\\\u00ed\\",\\"description\\":\\"Hledat souvisej

\\\\u00edc\\\\u00ed aplikace\\"},\\"cy\\":{\\"name\\":\\"Chwilio\\",\\"description\\":\\"Search related apps\\"},\\"da\\":{\\"name\\":\\"S\\\\u00f8g\\",\\"description\\":\\

"S\\\\u00f8gnings relaterede apps\\"},\\"de\\":{\\"name\\":\\"Suche\\",\\"description\\":\\"Verwandte Apps durchsuchen\\"},\\"dsb\\":{\\"name\\":\\"Pyta\\\\u015b\\",\\"

description\\":\\"Search related apps\\"},\\"el\\":{\\"name\\":\\"\\\\u0391\\\\u03bd\\\\u03b1\\\\u03b6\\\\u03ae\\\\u03c4\\\\u03b7\\\\u03c3\\\\u03b7\\",\\"description\\":\\"\\\\u0

391\\\\u03bd\\\\u03b1\\\\u03b6\\\\u03ae\\\\u03c4\\\\u03b7\\\\u03c3\\\\u03b7 \\\\u03c3\\\\u03c7\\\\u03b5\\\\u03c4\\\\u03b9\\\\u03ba\\\\u03ce\\\\u03bd \\\\u03b5\\\\u03c6\\\\u03b1\\\\u03c1\\

\\u03bc\\\\u03bf\\\\u03b3\\\\u03ce\\\\u03bd\\"},\\"eo\\":{\\"name\\":\\"Ser\\\\u0109i\\",\\"description\\":\\"Ser\\\\u0109i rilatajn aplika\\\\u0135ojn\\"},\\"es\\":{\\"name\\"

:\\"Buscar\\",\\"description\\":\\"Buscar apps relacionadas\\"},\\"es-ar\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\"Buscar aplicaciones relacionadas\\"},\\"e

s-co\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\"Buscar aplicaciones relacionadas\\"},\\"es-mx\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\"Buscar aplicaci

ones relacionadas\\"},\\"es-ni\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\"Buscar apps relacionadas\\"},\\"es-ve\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\

"Buscar apps relacionadas\\"},\\"et\\":{\\"name\\":\\"Otsing\\",\\"description\\":\\"Search related apps\\"},\\"eu\\":{\\"name\\":\\"Bilatu\\",\\"description\\":\\"Ze

rikusia duten aplikazioak bilatu\\"},\\"nl\\":{\\"name\\":\\"Zoek\\",\\"description\\":\\"Zoek gerelateerde apps\\"},\\"fa\\":{\\"name\\":\\"\\\\u062c\\\\u0633\\\\u062a

\\\\u062c\\\\u0648\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u0645\\\\u0631\\\\u062a\\\\u0628\\\\u0637 \\\\u0631\\\\u

0627 \\\\u062c\\\\u0633\\\\u062a\\\\u062c\\\\u0648 \\\\u06a9\\\\u0646\\\\u06cc\\\\u062f\\"},\\"nn\\":{\\"name\\":\\"S\\\\u00f8k\\",\\"description\\":\\"Search related apps\\"},\\

"fi\\":{\\"name\\":\\"Etsi\\",\\"description\\":\\"Hakuun liittyv\\\\u00e4t sovellukset\\"},\\"os\\":{\\"name\\":\\"\\\\u0410\\\\u0433\\\\u0443\\\\u0440\\\\u044b\\\\u043d\\",\\

"description\\":\\"Search related apps\\"},\\"pa\\":{\\"name\\":\\"\\\\u0a16\\\\u0a4b\\\\u0a1c\\",\\"description\\":\\"Search related apps\\"},\\"pl\\":{\\"name\\":\\"Wys

zukiwanie\\",\\"description\\":\\"Wyszukaj powi\\\\u0105zane aplikacje\\"},\\"pt\\":{\\"name\\":\\"Pesquisar\\",\\"description\\":\\"Search related apps\\"},\\"pt-b

r\\":{\\"name\\":\\"Busca\\",\\"description\\":\\"Pesquisar aplicativos relacionados\\"},\\"ro\\":{\\"name\\":\\"C\\\\u0103utare\\",\\"description\\":\\"Search relate

d apps\\"},\\"gl\\":{\\"name\\":\\"Buscar\\",\\"description\\":\\"Buscar aplicaci\\\\u00f3ns relacionadas\\"},\\"he\\":{\\"name\\":\\"\\\\u05d7\\\\u05d9\\\\u05e4\\\\u05d5\\\\

u05e9\\",\\"description\\":\\"\\\\u05d7\\\\u05d9\\\\u05e4\\\\u05d5\\\\u05e9 \\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9\\\\u05dd \\\\u05ea\\\\u05d5\\\\u05d

0\\\\u05de\\\\u05d9\\\\u05dd\\"},\\"hi\\":{\\"name\\":\\"\\\\u0916\\\\u094b\\\\u091c\\",\\"description\\":\\"Search related apps\\"},\\"hr\\":{\\"name\\":\\"Tra\\\\u017ei\\",\\"d

escription\\":\\"Pretra\\\\u017ei povezane aplikacije\\"},\\"hsb\\":{\\"name\\":\\"Pyta\\\\u0107\\",\\"description\\":\\"Search related apps\\"},\\"sr\\":{\\"name\\":\\

"\\\\u041f\\\\u0440\\\\u0435\\\\u0442\\\\u0440\\\\u0430\\\\u0433\\\\u0430\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\u0435\\\\u0442\\\\u0440\\\\u0430\\\\u0436\\\\u0438 \\\\u0441\\\\u0

43b\\\\u0438\\\\u0447\\\\u043d\\\\u0435 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041f\\\\u0440\\\\

u0435\\\\u0442\\\\u0440\\\\u0430\\\\u0433\\\\u0430\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\u0435\\\\u0442\\\\u0440\\\\u0430\\\\u0436\\\\u0438 \\\\u0441\\\\u043b\\\\u0438\\\\u0447

\\\\u043d\\\\u0435 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435\\"},\\"sv\\":{\\"name\\":\\"S\\\\u00f6k\\",\\"description\\":\\"S\\\\u00f6

k relaterade appar\\"},\\"sw\\":{\\"name\\":\\"Tafuta\\",\\"description\\":\\"Search related apps\\"},\\"ta\\":{\\"name\\":\\"Search\\",\\"description\\":\\"Search re

lated apps\\"}}},{\\"id\\":\\"security\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mecha

nisms like authentication, authorization, encryption, etc.\\"},\\"fr\\":{\\"name\\":\\"S\\\\u00e9curit\\\\u00e9\\",\\"description\\":\\"Des applications qui fou

rnissent des m\\\\u00e9canismes de s\\\\u00e9curit\\\\u00e9 suppl\\\\u00e9mentaires comme l'authentification, les autorisation, le chiffrement, etc.\\"},\\"

fy\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc

.\\"},\\"ga\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encrypti

on, etc.\\"},\\"gd\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, e

ncryption, etc.\\"},\\"ru\\":{\\"name\\":\\"\\\\u0411\\\\u0435\\\\u0437\\\\u043e\\\\u043f\\\\u0430\\\\u0441\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\\\u044c\\",\\"description\\":\\"\\\\u

041f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f, \\\\u043a\\\\u043e\\\\u0442\\\\u043e\\\\u0440\\\\u044b\\\\u0435 \\\\u043f\\\\u0440\\\\u0435\\\\u043

4\\\\u043e\\\\u0441\\\\u0442\\\\u0430\\\\u0432\\\\u043b\\\\u044f\\\\u044e\\\\u0442 \\\\u0434\\\\u043e\\\\u043f\\\\u043e\\\\u043b\\\\u043d\\\\u0438\\\\u0442\\\\u0435\\\\u043b\\\\u044c\\\\u0

43d\\\\u044b\\\\u0435 \\\\u043c\\\\u0435\\\\u0445\\\\u0430\\\\u043d\\\\u0438\\\\u0437\\\\u043c\\\\u044b \\\\u0431\\\\u0435\\\\u0437\\\\u043e\\\\u043f\\\\u0430\\\\u0441\\\\u043d\\\\u043e\\

\\u0441\\\\u0442\\\\u0438, \\\\u0442\\\\u0430\\\\u043a\\\\u0438\\\\u0435, \\\\u043a\\\\u0430\\\\u043a \\\\u0430\\\\u0443\\\\u0442\\\\u0435\\\\u043d\\\\u0442\\\\u0438\\\\u0444\\\\u0438\\\\

u043a\\\\u0430\\\\u0446\\\\u0438\\\\u044f, \\\\u0430\\\\u0432\\\\u0442\\\\u043e\\\\u0440\\\\u0438\\\\u0437\\\\u0430\\\\u0446\\\\u0438\\\\u044f, \\\\u0448\\\\u0438\\\\u0444\\\\u0440\\\\u0

43e\\\\u0432\\\\u0430\\\\u043d\\\\u0438\\\\u0435 \\\\u0438\\\\u0442\\\\u0434.\\"},\\"sk\\":{\\"name\\":\\"Zabezpe\\\\u010denie\\",\\"description\\":\\"Aplik\\\\u00e1cie, ktor\\\\

u00e9 poskytuj\\\\u00fa \\\\u010fal\\\\u0161ie bezpe\\\\u010dnostn\\\\u00e9 mechanizmy, ako je autentifik\\\\u00e1cia, autoriz\\\\u00e1cia, \\\\u0161ifrovanie at\\

\\u010f.\\"},\\"sl\\":{\\"name\\":\\"Varnost\\",\\"description\\":\\"Programi za zagotavljanje varnosti delovanja, overjanje, \\\\u0161ifriranje in podobno.\\"}

,\\"sq\\":{\\"name\\":\\"Siguria\\",\\"description\\":\\"Aplikacione q\\\\u00eb ofrojn\\\\u00eb mekanizma shtes\\\\u00eb sigurie si autentikim, autorizim, enkrip

tim, etj.\\"},\\"hu\\":{\\"name\\":\\"Biztons\\\\u00e1g\\",\\"description\\":\\"Alkalmaz\\\\u00e1sok, melyek tov\\\\u00e1bbi biztons\\\\u00e1gi mechanizmusokat bizt

os\\\\u00edtanak az hiteles\\\\u00edt\\\\u00e9shez, enged\\\\u00e9lyez\\\\u00e9shez, titkos\\\\u00edt\\\\u00e1shoz, stb.\\"},\\"hy\\":{\\"name\\":\\"Security\\",\\"desc

ription\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"ia\\":{\\"name\\":\\"Security\\"

,\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"id\\":{\\"name\\":\\"Sec

urity\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"io\\":{\\"name\\

":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"is\\":{

\\"name\\":\\"\\\\u00d6ryggi\\",\\"description\\":\\"Forrit sem gefa stu\\\\u00f0ning vi\\\\u00f0 vi\\\\u00f0b\\\\u00f3tar\\\\u00f6ryggiseiginleika, eins og au\\\\u00f

0kenningu, heimilda\\\\u00fej\\\\u00f3nustur, dulritun o.s.frv.\\"},\\"it\\":{\\"name\\":\\"Sicurezza\\",\\"description\\":\\"Apps che forniscono meccanismi agg

iuntivi di sicurezza come autenticazioni, autorizzazioni, crittografia, ecc.\\"},\\"ja\\":{\\"name\\":\\"\\\\u30bb\\\\u30ad\\\\u30e5\\\\u30ea\\\\u30c6\\\\u30a3\\",\\"

description\\":\\"\\\\u30a2\\\\u30d7\\\\u30ea\\\\u306f\\\\u3001\\\\u8a8d\\\\u8a3c\\\\u3001\\\\u627f\\\\u8a8d\\\\u3001\\\\u6697\\\\u53f7\\\\u5316\\\\u306a\\\\u3069\\\\u306b\\\\u3088\\\\u3

08a\\\\u8ffd\\\\u52a0\\\\u306e\\\\u30bb\\\\u30ad\\\\u30e5\\\\u30ea\\\\u30c6\\\\u30a3\\\\u5bfe\\\\u7b56\\\\u304c\\\\u63d0\\\\u4f9b\\\\u3055\\\\u308c\\\\u307e\\\\u3059\\\\u3002\\"},\\"ka\\"

:{\\"name\\":\\"\\\\u10e3\\\\u10e1\\\\u10d0\\\\u10e4\\\\u10e0\\\\u10d7\\\\u10ee\\\\u10dd\\\\u10d4\\\\u10d1\\\\u10d0\\",\\"description\\":\\"\\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9

\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8 \\\\u10e0\\\\u10dd\\\\u10db\\\\u10da\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10ea \\\\u10e3\\\\u10d6\\\\u10e0\\\\u10e3\\\\u10dc\\\\u10d5\\\\u1

0d4\\\\u10da\\\\u10e7\\\\u10dd\\\\u10e4\\\\u10d4\\\\u10dc \\\\u10d3\\\\u10d0\\\\u10db\\\\u10d0\\\\u10e2\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10d7 \\\\u10e3\\\\u10e1\\\\u10d0\\\\u10e4\\\\u10e0\\

\\u10d7\\\\u10ee\\\\u10dd\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10e1 \\\\u10db\\\\u10d4\\\\u10e5\\\\u10d0\\\\u10dc\\\\u10d8\\\\u10d6\\\\u10db\\\\u10d4\\\\u10d1\\\\u10e1, \\\\u10d8\\\\u10e1\\\\u1

0d4\\\\u10d7\\\\u10d4\\\\u10d1\\\\u10e1 \\\\u10e0\\\\u10dd\\\\u10d2\\\\u10dd\\\\u10e0\\\\u10d4\\\\u10d1\\\\u10d8\\\\u10ea\\\\u10d0\\\\u10d0 \\\\u10d0\\\\u10d5\\\\u10e2\\\\u10dd\\\\u10e0\\

\\u10d8\\\\u10d6\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d0, \\\\u10d0\\\\u10e3\\\\u10e2\\\\u10d4\\\\u10dc\\\\u10e2\\\\u10d8\\\\u10e4\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d0, \\\\u

10d9\\\\u10dd\\\\u10d3\\\\u10d8\\\\u10e0\\\\u10d4\\\\u10d1\\\\u10d0, \\\\u10d0.\\\\u10e8.\\"},\\"kab\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide addi

tional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"kk\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provi

de additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"km\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps tha

t provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"kn\\":{\\"name\\":\\"Security\\",\\"description\\":\\"A

pps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"ko\\":{\\"name\\":\\"\\\\ubcf4\\\\uc548\\",\\"desc

ription\\":\\"\\\\uc778\\\\uc99d, \\\\uc554\\\\ud638\\\\ud654 \\\\ub4f1 \\\\ucd94\\\\uac00 \\\\ubcf4\\\\uc548 \\\\uae30\\\\ub2a5\\\\uc744 \\\\uc81c\\\\uacf5\\\\ud558\\\\ub294 \\\\uc571

\\"},\\"lb\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryptio

n, etc.\\"},\\"lt\\":{\\"name\\":\\"Saugumas\\",\\"description\\":\\"Taikomosios programos, kurios atsakingos u\\\\u017e papildomus saugos mechanizmus tokius,

 kaip tapatyb\\\\u0117s nustatymas, autorizacija, \\\\u0161ifravimas ir pan.\\"},\\"lv\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide addi

tional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"mk\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provi

de additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"ml\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps tha

t provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"mn\\":{\\"name\\":\\"Security\\",\\"description\\":\\"A

pps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"af\\":{\\"name\\":\\"Security\\",\\"descriptio

n\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"mr\\":{\\"name\\":\\"Security\\",\\"des

cription\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"my\\":{\\"name\\":\\"Security\\

",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"nb\\":{\\"name\\":\\"Si

kkerhet\\",\\"description\\":\\"Apper som tilbyr ekstra sikkerhetsmekanismer som autentisering, identitetsbekreftelse, kryptering, osv.\\"},\\"ne\\":{\\"n

ame\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"te

\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\

"},\\"th\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption

, etc.\\"},\\"tr\\":{\\"name\\":\\"G\\\\u00fcvenlik\\",\\"description\\":\\"Kimlik do\\\\u011frulama, \\\\u015fifreleme vb ek g\\\\u00fcvenlik mekanizmalar\\\\u0131 s

a\\\\u011flayan uygulamalar.\\"},\\"tt\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication

, authorization, encryption, etc.\\"},\\"udm\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authen

tication, authorization, encryption, etc.\\"},\\"uk\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like

 authentication, authorization, encryption, etc.\\"},\\"ar\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanis

ms like authentication, authorization, encryption, etc.\\"},\\"ast\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security 

mechanisms like authentication, authorization, encryption, etc.\\"},\\"az\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional se

curity mechanisms like authentication, authorization, encryption, etc.\\"},\\"bg\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additi

onal security mechanisms like authentication, authorization, encryption, etc.\\"},\\"be\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide

 additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"ur\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that 

provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"vi\\":{\\"name\\":\\"B\\\\u1ea3o m\\\\u1eadt\\",\\"descript

ion\\":\\"\\\\u1ee8ng d\\\\u1ee5ng cung c\\\\u1ea5p th\\\\u00eam c\\\\u00e1ch th\\\\u1ee9c b\\\\u1ea3o m\\\\u1eadt nh\\\\u01b0 m\\\\u00e3 h\\\\u00f3a, x\\\\u00e1c minh, cho

 ph\\\\u00e9p, vv.\\"},\\"zh-hans\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, aut

horization, encryption, etc.\\"},\\"zh-hant\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authent

ication, authorization, encryption, etc.\\"},\\"bn\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like 

authentication, authorization, encryption, etc.\\"},\\"br\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanism

s like authentication, authorization, encryption, etc.\\"},\\"bs\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security me

chanisms like authentication, authorization, encryption, etc.\\"},\\"ca\\":{\\"name\\":\\"Seguretat\\",\\"description\\":\\"Aplicacions que proporcionen mec

anismes addicionals de seguretat com l'autenticaci\\\\u00f3, autoritzaci\\\\u00f3, encriptaci\\\\u00f3, etc.\\"},\\"cs\\":{\\"name\\":\\"Zabezpe\\\\u010den\\\\u00

ed\\",\\"description\\":\\"Aplikace, kter\\\\u00e9 poskytuj\\\\u00ed dal\\\\u0161\\\\u00ed bezpe\\\\u010dnostn\\\\u00ed mechanismy, jako je ov\\\\u011b\\\\u0159ov\\\\u0

0e1n\\\\u00ed, pov\\\\u011b\\\\u0159ov\\\\u00e1n\\\\u00ed, \\\\u0161ifrov\\\\u00e1n\\\\u00ed, atd.\\"},\\"cy\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that pr

ovide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"da\\":{\\"name\\":\\"Sikkerhed\\",\\"description\\":\\"Apps

 der tilbyder yderligere sikkerhedsmekanismer s\\\\u00e5som autentifikation, bemyndigelse, kryptering osv.\\"},\\"de\\":{\\"name\\":\\"Sicherheit\\",\\"desc

ription\\":\\"Apps die zus\\\\u00e4tzliche Sicherheitsmechanismen bereitstellen, wie z.B. Authentifizierung, Autorisierung, Verschl\\\\u00fcsselung usw.

\\"},\\"dsb\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encrypti

on, etc.\\"},\\"el\\":{\\"name\\":\\"\\\\u0391\\\\u03c3\\\\u03c6\\\\u03ac\\\\u03bb\\\\u03b5\\\\u03b9\\\\u03b1\\",\\"description\\":\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u

03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03c0\\\\u03bf\\\\u03c5 \\\\u03c0\\\\u03b1\\\\u03c1\\\\u03ad\\\\u03c7\\\\u03bf\\\\u03c5\\\\u03bd \\\\u03c0\\\\u03c1\\\\u03cc\\\\u03c3\\\\u03b8\\\\u03b

5\\\\u03c4\\\\u03bf\\\\u03c5\\\\u03c2 \\\\u03bc\\\\u03b7\\\\u03c7\\\\u03b1\\\\u03bd\\\\u03b9\\\\u03c3\\\\u03bc\\\\u03bf\\\\u03cd\\\\u03c2 \\\\u03b1\\\\u03c3\\\\u03c6\\\\u03b1\\\\u03bb\\\\u

03b5\\\\u03af\\\\u03b1\\\\u03c2 \\\\u03cc\\\\u03c0\\\\u03c9\\\\u03c2 \\\\u03c0\\\\u03b9\\\\u03c3\\\\u03c4\\\\u03bf\\\\u03c0\\\\u03bf\\\\u03af\\\\u03b7\\\\u03c3\\\\u03b7, \\\\u03b5\\\\u03

be\\\\u03bf\\\\u03c5\\\\u03c3\\\\u03b9\\\\u03bf\\\\u03b4\\\\u03cc\\\\u03c4\\\\u03b7\\\\u03c3\\\\u03b7, \\\\u03ba\\\\u03c1\\\\u03c5\\\\u03c0\\\\u03c4\\\\u03bf\\\\u03b3\\\\u03c1\\\\u03ac\\\\

u03c6\\\\u03b7\\\\u03c3\\\\u03b7 \\\\u03ba.\\\\u03bb\\\\u03c0.\\"},\\"eo\\":{\\"name\\":\\"Sekurigo\\",\\"description\\":\\"Aplika\\\\u0135oj, kiuj aldonas plian sekuriga

n rimedaron, kiel a\\\\u016dtentigo, rajtigo, \\\\u0109ifrado, k.t.p.\\"},\\"es\\":{\\"name\\":\\"Seguridad\\",\\"description\\":\\"Apps que proporcionan mecani

smos de seguridad adicionales, como autenticaci\\\\u00f3n, autorizaci\\\\u00f3n, cifrado, etc.\\"},\\"es-ar\\":{\\"name\\":\\"Seguridad\\",\\"description\\":\\"

Aplicaciones que proporcionan mecanismos de seguridad adicionales como autenticaci\\\\u00f3n, autorizaci\\\\u00f3n, cifrado, etc.\\"},\\"es-co\\":{\\"name

\\":\\"Seguridad\\",\\"description\\":\\"Aplicaciones que proporcionan mecanismos de seguridad adicionales como autenticaci\\\\u00f3n, autorizaci\\\\u00f3n,

 encripci\\\\u00f3n, etc.\\"},\\"es-mx\\":{\\"name\\":\\"Seguridad\\",\\"description\\":\\"Aplicaciones que proporcionan mecanismos de seguridad adicionales c

omo autenticaci\\\\u00f3n, autorizaci\\\\u00f3n, encripci\\\\u00f3n, etc.\\"},\\"es-ni\\":{\\"name\\":\\"Seguridad\\",\\"description\\":\\"Aplicaciones que propor

cionan mecanismos de seguridad adicionales como autenticaci\\\\u00f3n, autorizaci\\\\u00f3n, encripci\\\\u00f3n, etc.\\"},\\"es-ve\\":{\\"name\\":\\"Seguridad

\\",\\"description\\":\\"Apps que proporcionan mecanismos de seguridad adicionales, como autenticaci\\\\u00f3n, autorizaci\\\\u00f3n, cifrado, etc.\\"},\\"e

t\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.

\\"},\\"eu\\":{\\"name\\":\\"Segurtasuna\\",\\"description\\":\\"Segurtasun gehiago emateko app-ak, adibidez autentikazioa, autorizazioa, enkriptazioa eta a

bar.\\"},\\"nl\\":{\\"name\\":\\"Beveiliging\\",\\"description\\":\\"Apps die extra beveiligingsmechanismen bieden zoals authenticatie, autorisatie, encrypt

ie, enz.\\"},\\"fa\\":{\\"name\\":\\"\\\\u0627\\\\u0645\\\\u0646\\\\u06cc\\\\u062a\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\

u06cc\\\\u06cc \\\\u06a9\\\\u0647 \\\\u0645\\\\u06a9\\\\u0627\\\\u0646\\\\u06cc\\\\u0632\\\\u0645 \\\\u0647\\\\u0627\\\\u06cc \\\\u0627\\\\u0645\\\\u0646\\\\u06cc\\\\u062a\\\\u06cc \\\\u

0627\\\\u0636\\\\u0627\\\\u0641\\\\u06cc \\\\u0645\\\\u0627\\\\u0646\\\\u0646\\\\u062f \\\\u062a\\\\u0623\\\\u06cc\\\\u06cc\\\\u062f \\\\u0627\\\\u0639\\\\u062a\\\\u0628\\\\u0627\\\\u063

1 \\\\u060c \\\\u0645\\\\u062c\\\\u0648\\\\u0632 \\\\u060c \\\\u0631\\\\u0645\\\\u0632\\\\u06af\\\\u0630\\\\u0627\\\\u0631\\\\u06cc \\\\u0648 \\\\u063a\\\\u06cc\\\\u0631\\\\u0647 \\\\u06

31\\\\u0627 \\\\u0627\\\\u0631\\\\u0627\\\\u0626\\\\u0647 \\\\u0645\\\\u06cc \\\\u062f\\\\u0647\\\\u0646\\\\u062f.\\"},\\"nn\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps

 that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"fi\\":{\\"name\\":\\"Tietoturva\\",\\"description

\\":\\"Sovellukset, jotka tarjoavat lis\\\\u00e4suojausmekanismeja, kuten todennusta, valtuutusta, salausta jne.\\"},\\"os\\":{\\"name\\":\\"Security\\",\\"de

scription\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"pa\\":{\\"name\\":\\"Security

\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"pl\\":{\\"name\\":\\"B

ezpiecze\\\\u0144stwo\\",\\"description\\":\\"Aplikacje zapewniaj\\\\u0105ce dodatkowe mechanizmy bezpiecze\\\\u0144stwa jak uwierzytelnianie, autoryzacja, 

szyfrowanie, itp.\\"},\\"pt\\":{\\"name\\":\\"Seguran\\\\u00e7a\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00f5es que oferecem mecanismos de seguran\\\\u00e7a adic

ional como autentica\\\\u00e7\\\\u00e3o, autoriza\\\\u00e7\\\\u00e3o, cifragem, etc.\\"},\\"pt-br\\":{\\"name\\":\\"Seguran\\\\u00e7a\\",\\"description\\":\\"Aplicati

vos que fornecem mecanismos de seguran\\\\u00e7a adicional como autentica\\\\u00e7\\\\u00e3o, autoriza\\\\u00e7\\\\u00e3o, criptografia, etc.\\"},\\"ro\\":{\\"n

ame\\":\\"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"gl

\\":{\\"name\\":\\"Seguridade\\",\\"description\\":\\"Aplicaci\\\\u00f3ns que fornecen mecanismos de seguridade adicionais, como autenticaci\\\\u00f3n, autori

zaci\\\\u00f3n, cifrado, etc.\\"},\\"he\\":{\\"name\\":\\"\\\\u05d0\\\\u05d1\\\\u05d8\\\\u05d7\\\\u05d4\\",\\"description\\":\\"\\\\u05d9\\\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05

d5\\\\u05e0\\\\u05d9\\\\u05dd \\\\u05e9\\\\u05de\\\\u05e1\\\\u05e4\\\\u05e7\\\\u05d9\\\\u05dd \\\\u05de\\\\u05e0\\\\u05d2\\\\u05e0\\\\u05d5\\\\u05e0\\\\u05d9 \\\\u05d0\\\\u05d1\\\\u05d8\\

\\u05d7\\\\u05d4 \\\\u05e0\\\\u05d5\\\\u05e1\\\\u05e4\\\\u05d9\\\\u05dd \\\\u05db\\\\u05d2\\\\u05d5\\\\u05df \\\\u05d0\\\\u05d9\\\\u05de\\\\u05d5\\\\u05ea, \\\\u05d0\\\\u05d9\\\\u05e9\\\\

u05d5\\\\u05e8, \\\\u05d4\\\\u05e6\\\\u05e4\\\\u05e0\\\\u05d4 \\\\u05d5\\\\u05e2\\\\u05d5\\\\u05d3.\\"},\\"hi\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that provi

de additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"hr\\":{\\"name\\":\\"Sigurnost\\",\\"description\\":\\"Aplikac

ije koje pru\\\\u017eaju dodatne sigurnosne mehanizme poput provjere autenti\\\\u010dnosti, autorizacije, \\\\u0161ifriranja itd.\\"},\\"hsb\\":{\\"name\\":\\

"Security\\",\\"description\\":\\"Apps that provide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"sr\\":{\\"n

ame\\":\\"\\\\u0411\\\\u0435\\\\u0437\\\\u0431\\\\u0435\\\\u0434\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u04

46\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\u043e\\\\u0458\\\\u0435 \\\\u043e\\\\u0431\\\\u0435\\\\u0437\\\\u0431\\\\u0435\\\\u0452\\\\u0443\\\\u0458\\\\u0443 \\\\u0434\\\\u043e\\\\u0434\\

\\u0430\\\\u0442\\\\u043d\\\\u0435 \\\\u0431\\\\u0435\\\\u0437\\\\u0431\\\\u0435\\\\u0434\\\\u043e\\\\u043d\\\\u043e\\\\u0441\\\\u043d\\\\u0435 \\\\u043c\\\\u0435\\\\u0445\\\\u0430\\\\u04

3d\\\\u0438\\\\u0437\\\\u043c\\\\u0435, \\\\u043a\\\\u0430\\\\u043e \\\\u0448\\\\u0442\\\\u043e \\\\u0441\\\\u0443 \\\\u043f\\\\u0440\\\\u0438\\\\u0458\\\\u0430\\\\u0432\\\\u0459\\\\u043

8\\\\u0432\\\\u0430\\\\u045a\\\\u0435, \\\\u043f\\\\u0440\\\\u043e\\\\u0432\\\\u0435\\\\u0440\\\\u0430 \\\\u0438\\\\u0434\\\\u0435\\\\u043d\\\\u0442\\\\u0438\\\\u0442\\\\u0435\\\\u0442\\\\

u0430, \\\\u0448\\\\u0438\\\\u0444\\\\u0440\\\\u043e\\\\u0432\\\\u0430\\\\u045a\\\\u0435 \\\\u0438\\\\u0442\\\\u0434.\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0411\\\\u0435\\\\u0437\\\\u0

431\\\\u0435\\\\u0434\\\\u043d\\\\u043e\\\\u0441\\\\u0442\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u043a\\\\

u043e\\\\u0458\\\\u0435 \\\\u043e\\\\u0431\\\\u0435\\\\u0437\\\\u0431\\\\u0435\\\\u0452\\\\u0443\\\\u0458\\\\u0443 \\\\u0434\\\\u043e\\\\u0434\\\\u0430\\\\u0442\\\\u043d\\\\u0435 \\\\u04

31\\\\u0435\\\\u0437\\\\u0431\\\\u0435\\\\u0434\\\\u043e\\\\u043d\\\\u043e\\\\u0441\\\\u043d\\\\u0435 \\\\u043c\\\\u0435\\\\u0445\\\\u0430\\\\u043d\\\\u0438\\\\u0437\\\\u043c\\\\u0435, \\

\\u043a\\\\u0430\\\\u043e \\\\u0448\\\\u0442\\\\u043e \\\\u0441\\\\u0443 \\\\u043f\\\\u0440\\\\u0438\\\\u0458\\\\u0430\\\\u0432\\\\u0459\\\\u0438\\\\u0432\\\\u0430\\\\u045a\\\\u0435, \\\\

u043f\\\\u0440\\\\u043e\\\\u0432\\\\u0435\\\\u0440\\\\u0430 \\\\u0438\\\\u0434\\\\u0435\\\\u043d\\\\u0442\\\\u0438\\\\u0442\\\\u0435\\\\u0442\\\\u0430, \\\\u0448\\\\u0438\\\\u0444\\\\u04

40\\\\u043e\\\\u0432\\\\u0430\\\\u045a\\\\u0435 \\\\u0438\\\\u0442\\\\u0434.\\"},\\"sv\\":{\\"name\\":\\"S\\\\u00e4kerhet\\",\\"description\\":\\"Appar som erbjuder ytterliga

re s\\\\u00e4kerhetsmekanismer som autentisering, tillst\\\\u00e5nd, kryptering, etc.\\"},\\"sw\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps that pro

vide additional security mechanisms like authentication, authorization, encryption, etc.\\"},\\"ta\\":{\\"name\\":\\"Security\\",\\"description\\":\\"Apps t

hat provide additional security mechanisms like authentication, authorization, encryption, etc.\\"}}},{\\"id\\":\\"social\\",\\"translations\\":{\\"en\\":{

\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"fr\\":{\\"name\\":\\"Social & communica

tion\\",\\"description\\":\\"Applications de messagerie, de gestion de contacts et de r\\\\u00e9seaux sociaux\\"},\\"fy\\":{\\"name\\":\\"Social & communicati

on\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"ga\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messag

ing, contact management and social media apps\\"},\\"gd\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and s

ocial media apps\\"},\\"ru\\":{\\"name\\":\\"\\\\u0421\\\\u043e\\\\u0446\\\\u0438\\\\u0430\\\\u043b\\\\u044c\\\\u043d\\\\u043e\\\\u0435 \\\\u0438 \\\\u0441\\\\u0432\\\\u044f\\\\u0437

\\\\u044c\\",\\"description\\":\\"\\\\u041e\\\\u0431\\\\u0449\\\\u0435\\\\u043d\\\\u0438\\\\u0435, \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u043b\\\\u0435\\\\u043d\\\\u0438\\\\u0

435 \\\\u043a\\\\u043e\\\\u043d\\\\u0442\\\\u0430\\\\u043a\\\\u0442\\\\u0430\\\\u043c\\\\u0438 \\\\u0438 \\\\u0441\\\\u043e\\\\u0446\\\\u0438\\\\u0430\\\\u043b\\\\u044c\\\\u043d\\\\u043e

\\\\u0435 \\\\u043c\\\\u0435\\\\u0434\\\\u0438\\\\u0430-\\\\u043f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u0435\\"},\\"sk\\":{\\"name\\":\\"Soci\\\\u00

e1lne siete a komunik\\\\u00e1cia\\",\\"description\\":\\"Aplik\\\\u00e1cie pre v\\\\u00fdmenu spr\\\\u00e1v, spr\\\\u00e1vu kontaktov a soci\\\\u00e1lne siete\\"}

,\\"sl\\":{\\"name\\":\\"Dru\\\\u017ebene dejavnosti\\",\\"description\\":\\"Sporo\\\\u010danje, upravljanje stikov in dru\\\\u017ebena omre\\\\u017eja\\"},\\"sq\\":{

\\"name\\":\\"Social & komunikim\\",\\"description\\":\\"Te shkruheni , kontaktoni menaxhimin dhe aplikacionet e mediave sociale\\"},\\"hu\\":{\\"name\\":\\"K\\

\\u00f6z\\\\u00f6ss\\\\u00e9g \\\\u00e9s kommunik\\\\u00e1ci\\\\u00f3\\",\\"description\\":\\"\\\\u00dczenetk\\\\u00fcld\\\\u0151, kapcsolatkezel\\\\u0151 \\\\u00e9s k\\\\u0

0f6z\\\\u00f6ss\\\\u00e9gi m\\\\u00e9dia alkalmaz\\\\u00e1sok\\"},\\"hy\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact manageme

nt and social media apps\\"},\\"ia\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\

"id\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"io\\":{\\"name\\":\\"Social & co

mmunication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"is\\":{\\"name\\":\\"Samskipti og samf\\\\u00e9lagsmi\\\\u00f0lar

\\",\\"description\\":\\"Samskipti, ums\\\\u00fdsla tengili\\\\u00f0a og samf\\\\u00e9lagsmi\\\\u00f0laforrit\\"},\\"it\\":{\\"name\\":\\"Sociale e comunicazione\\",

\\"description\\":\\"Applicazioni di messaggistica, gestione dei contatti e reti sociali\\"},\\"ja\\":{\\"name\\":\\"\\\\u30bd\\\\u30fc\\\\u30b7\\\\u30e3\\\\u30eb\\\\u

30fb\\\\u30b3\\\\u30df\\\\u30e5\\\\u30cb\\\\u30b1\\\\u30fc\\\\u30b7\\\\u30e7\\\\u30f3\\",\\"description\\":\\"\\\\u30e1\\\\u30c3\\\\u30bb\\\\u30fc\\\\u30b8\\\\u30f3\\\\u30b0\\\\u3001\\\\

u9023\\\\u7d61\\\\u5148\\\\u7ba1\\\\u7406\\\\u3001\\\\u30bd\\\\u30fc\\\\u30b7\\\\u30e3\\\\u30eb\\\\u30e1\\\\u30c7\\\\u30a3\\\\u30a2\\\\u30a2\\\\u30d7\\\\u30ea\\"},\\"ka\\":{\\"name\\":\\

"\\\\u10e1\\\\u10dd\\\\u10ea\\\\u10d0\\\\u10da\\\\u10e3\\\\u10e0\\\\u10d8 \\\\u10d3\\\\u10d0 \\\\u10d9\\\\u10dd\\\\u10db\\\\u10e3\\\\u10dc\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u

10d0\\",\\"description\\":\\"\\\\u10db\\\\u10d8\\\\u10db\\\\u10dd\\\\u10ec\\\\u10d4\\\\u10e0\\\\u10d0, \\\\u10d9\\\\u10dd\\\\u10dc\\\\u10e2\\\\u10d0\\\\u10e5\\\\u10e2\\\\u10d4\\\\u10d1

\\\\u10d8\\\\u10e1 \\\\u10db\\\\u10d4\\\\u10dc\\\\u10d4\\\\u10ef\\\\u10db\\\\u10d4\\\\u10dc\\\\u10e2\\\\u10d8 \\\\u10d3\\\\u10d0 \\\\u10e1\\\\u10dd\\\\u10ea\\\\u10d8\\\\u10d0\\\\u10da\\\\u

10e3\\\\u10e0\\\\u10d8 \\\\u10db\\\\u10d4\\\\u10d3\\\\u10d8\\\\u10d8\\\\u10e1 \\\\u10d0\\\\u10de\\\\u10da\\\\u10d8\\\\u10d9\\\\u10d0\\\\u10ea\\\\u10d8\\\\u10d4\\\\u10d1\\\\u10d8\\"},\\"k

ab\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"kk\\":{\\"name\\":\\"Social & com

munication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"km\\":{\\"name\\":\\"Social & communication\\",\\"description\\":

\\"Messaging, contact management and social media apps\\"},\\"kn\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact manageme

nt and social media apps\\"},\\"ko\\":{\\"name\\":\\"\\\\uc18c\\\\uc15c \\\\ubc0f \\\\ud1b5\\\\uc2e0\\",\\"description\\":\\"\\\\uba54\\\\uc2dc\\\\uc9d5, \\\\uc5f0\\\\ub77d\\\\uc

c98 \\\\uad00\\\\ub9ac, \\\\uc18c\\\\uc15c \\\\ubbf8\\\\ub514\\\\uc5b4 \\\\uc571\\"},\\"lb\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, conta

ct management and social media apps\\"},\\"lt\\":{\\"name\\":\\"Socialiniai reikalai ir bendravimas\\",\\"description\\":\\"Prane\\\\u0161im\\\\u0173, adresat\\\\

u0173 valdymo ir socialin\\\\u0117s \\\\u017einiasklaidos taikomosios programos\\"},\\"lv\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messa

ging, contact management and social media apps\\"},\\"mk\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and 

social media apps\\"},\\"ml\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"mn\\":{

\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"mr\\":{\\"name\\":\\"Social & communica

tion\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"my\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Mess

aging, contact management and social media apps\\"},\\"nb\\":{\\"name\\":\\"Sosialt og kommunikasjon\\",\\"description\\":\\"Apper for meldinger, kontakth\\\\

u00e5ndtering og sosiale medier\\"},\\"ne\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media ap

ps\\"},\\"te\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"th\\":{\\"name\\":\\"Soci

al & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"tr\\":{\\"name\\":\\"Sosyal A\\\\u011f ve \\\\u0130leti\\\\u

015fim\\",\\"description\\":\\"\\\\u0130leti\\\\u015fim, ki\\\\u015fi y\\\\u00f6netimi ve sosyal a\\\\u011f uygulamalar\\\\u0131\\"},\\"tt\\":{\\"name\\":\\"Social & co

mmunication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"udm\\":{\\"name\\":\\"Social & communication\\",\\"description\\

":\\"Messaging, contact management and social media apps\\"},\\"uk\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact manage

ment and social media apps\\"},\\"af\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"}

,\\"ar\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"ast\\":{\\"name\\":\\"Social &

 communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"az\\":{\\"name\\":\\"Social & communication\\",\\"descriptio

n\\":\\"Messaging, contact management and social media apps\\"},\\"bg\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact mana

gement and social media apps\\"},\\"be\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\

"},\\"ur\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"vi\\":{\\"name\\":\\"X\\\\u00e

3 h\\\\u1ed9i v\\\\u00e0 c\\\\u00e1ch th\\\\u1ee9c trao \\\\u0111\\\\u1ed5i\\",\\"description\\":\\"\\\\u1ee8ng d\\\\u1ee5ng nh\\\\u1eafn tin, qu\\\\u1ea3n l\\\\u00fd li\\\\u

00ean h\\\\u1ec7 v\\\\u00e0 m\\\\u1ea1ng x\\\\u00e3 h\\\\u1ed9i\\"},\\"zh-hans\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact man

agement and social media apps\\"},\\"zh-hant\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media

 apps\\"},\\"bn\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"br\\":{\\"name\\":\\"S

ocial & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"bs\\":{\\"name\\":\\"Social & communication\\",\\"des

cription\\":\\"Messaging, contact management and social media apps\\"},\\"ca\\":{\\"name\\":\\"Social i comunicacions\\",\\"description\\":\\"Aplicacions de m

issatgeria, gesti\\\\u00f3 de contactes i mitjans de comunicaci\\\\u00f3 social\\"},\\"cs\\":{\\"name\\":\\"Soci\\\\u00e1ln\\\\u00ed s\\\\u00edt\\\\u011b a komunika

ce\\",\\"description\\":\\"Aplikace pro zas\\\\u00edl\\\\u00e1n\\\\u00ed zpr\\\\u00e1v, spr\\\\u00e1vu kontakt\\\\u016f a soci\\\\u00e1ln\\\\u00ed s\\\\u00edt\\\\u011b\\"}

,\\"cy\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"da\\":{\\"name\\":\\"Socialt &

 kommunikation\\",\\"description\\":\\"Apps til beskeder, kontakter og sociale medier\\"},\\"de\\":{\\"name\\":\\"Kommunikation\\",\\"description\\":\\"Nachrich

ten-, Kontaktverwaltungs- und Social-Media-Apps\\"},\\"dsb\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management an

d social media apps\\"},\\"el\\":{\\"name\\":\\"\\\\u039a\\\\u03bf\\\\u03b9\\\\u03bd\\\\u03c9\\\\u03bd\\\\u03b9\\\\u03ba\\\\u03ac \\\\u03ba\\\\u03b1\\\\u03b9 \\\\u03b5\\\\u03c0\\\\u0

3b9\\\\u03ba\\\\u03bf\\\\u03b9\\\\u03bd\\\\u03c9\\\\u03bd\\\\u03af\\\\u03b1\\",\\"description\\":\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\

u03b5\\\\u03c0\\\\u03b9\\\\u03ba\\\\u03bf\\\\u03b9\\\\u03bd\\\\u03c9\\\\u03bd\\\\u03af\\\\u03b1\\\\u03c2, \\\\u03b4\\\\u03b9\\\\u03b1\\\\u03c7\\\\u03b5\\\\u03af\\\\u03c1\\\\u03b9\\\\u03c

3\\\\u03b7\\\\u03c2 \\\\u03b5\\\\u03c0\\\\u03b1\\\\u03c6\\\\u03ce\\\\u03bd \\\\u03ba\\\\u03b1\\\\u03b9 \\\\u03bc\\\\u03ad\\\\u03c3\\\\u03c9\\\\u03bd \\\\u03ba\\\\u03bf\\\\u03b9\\\\u03bd\\

\\u03c9\\\\u03bd\\\\u03b9\\\\u03ba\\\\u03ae\\\\u03c2 \\\\u03b4\\\\u03b9\\\\u03ba\\\\u03c4\\\\u03cd\\\\u03c9\\\\u03c3\\\\u03b7\\\\u03c2\\"},\\"eo\\":{\\"name\\":\\"Sociaj kaj komunik

aj iloj\\",\\"description\\":\\"Mesa\\\\u011dado, kontaktmastrumado kaj sociaj komunikiloj\\"},\\"es\\":{\\"name\\":\\"Social y comunicaci\\\\u00f3n\\",\\"descrip

tion\\":\\"Apps de mensajer\\\\u00eda, manejo de contactos y medios sociales\\"},\\"es-ar\\":{\\"name\\":\\"Social & comunicaci\\\\u00f3n\\",\\"description\\":\\"

Aplicaciones de mensajer\\\\u00eda, administraci\\\\u00f3n de contactos y medios sociales\\"},\\"es-co\\":{\\"name\\":\\"Social & comunicaci\\\\u00f3n\\",\\"des

cription\\":\\"Aplicaciones de mensajer\\\\u00eda, administraci\\\\u00f3n de contactos y medios sociales\\"},\\"es-mx\\":{\\"name\\":\\"Social & comunicaci\\\\u

00f3n\\",\\"description\\":\\"Aplicaciones de mensajer\\\\u00eda, administraci\\\\u00f3n de contactos y medios sociales\\"},\\"es-ni\\":{\\"name\\":\\"Social & 

comunicaci\\\\u00f3n\\",\\"description\\":\\"Aplicaciones de mensajer\\\\u00eda, administraci\\\\u00f3n de contactos y medios sociales\\"},\\"es-ve\\":{\\"name\\

":\\"Social y comunicaci\\\\u00f3n\\",\\"description\\":\\"Apps de mensajer\\\\u00eda, manejo de contactos y medios sociales\\"},\\"et\\":{\\"name\\":\\"Social &

 communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"eu\\":{\\"name\\":\\"Soziala eta komunikazioa\\",\\"descript

ion\\":\\"Mezularitza, kontaktuen kudeaketa eta sare sozialen app-ak\\"},\\"nl\\":{\\"name\\":\\"Sociaal & communicatie\\",\\"description\\":\\"Messaging, con

tactbeheer en social media apps\\"},\\"fa\\":{\\"name\\":\\"\\\\u0627\\\\u0631\\\\u062a\\\\u0628\\\\u0627\\\\u0637 \\\\u0627\\\\u062c\\\\u062a\\\\u0645\\\\u0627\\\\u0639\\\\u06cc

\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc \\\\u067e\\\\u06cc\\\\u0627\\\\u0645 \\\\u0631\\\\u0633\\\\u0627\\\\u0646\\\\u

06cc \\\\u060c \\\\u0645\\\\u062f\\\\u06cc\\\\u0631\\\\u06cc\\\\u062a \\\\u062a\\\\u0645\\\\u0627\\\\u0633 \\\\u0648 \\\\u0631\\\\u0633\\\\u0627\\\\u0646\\\\u0647 \\\\u0647\\\\u0627\\\\u

06cc \\\\u0627\\\\u062c\\\\u062a\\\\u0645\\\\u0627\\\\u0639\\\\u06cc\\"},\\"nn\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact managem

ent and social media apps\\"},\\"fi\\":{\\"name\\":\\"Sosiaaliset & kommunikaatio\\",\\"description\\":\\"Viestittely-, yhteystietojenhallinta- ja sosiaalis

en median sovellukset\\"},\\"os\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"pa

\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"pl\\":{\\"name\\":\\"Spo\\\\u0142eczn

o\\\\u015b\\\\u0107 i komunikacja\\",\\"description\\":\\"Aplikacje do komunikacji, zarz\\\\u0105dzania kontaktami i dla medi\\\\u00f3w spo\\\\u0142eczno\\\\u015b

ciowych\\"},\\"pt\\":{\\"name\\":\\"Social & comunica\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplica\\\\u00e7\\\\u00e3o para troca de mensagens, gest\\\\u00e3o de 

contactos e redes sociais\\"},\\"pt-br\\":{\\"name\\":\\"Social & comunica\\\\u00e7\\\\u00e3o\\",\\"description\\":\\"Aplicativos de mensagem, gerenciamento de 

contatos e m\\\\u00eddias sociais\\"},\\"ro\\":{\\"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media ap

ps\\"},\\"gl\\":{\\"name\\":\\"Social e comunicaci\\\\u00f3n\\",\\"description\\":\\"Aplicaci\\\\u00f3ns de mensaxer\\\\u00eda, xesti\\\\u00f3n de contactos e medio

s sociais\\"},\\"he\\":{\\"name\\":\\"\\\\u05d7\\\\u05d1\\\\u05e8\\\\u05ea\\\\u05d9 \\\\u05d5\\\\u05ea\\\\u05e7\\\\u05e9\\\\u05d5\\\\u05e8\\\\u05ea\\",\\"description\\":\\"\\\\u05d9\\

\\u05d9\\\\u05e9\\\\u05d5\\\\u05de\\\\u05d5\\\\u05e0\\\\u05d9 \\\\u05d4\\\\u05ea\\\\u05db\\\\u05ea\\\\u05d1\\\\u05d5\\\\u05ea, \\\\u05e0\\\\u05d9\\\\u05d4\\\\u05d5\\\\u05dc \\\\u05d0\\\\u

05e0\\\\u05e9\\\\u05d9 \\\\u05e7\\\\u05e9\\\\u05e8 \\\\u05d5\\\\u05e8\\\\u05e9\\\\u05ea\\\\u05d5\\\\u05ea \\\\u05d7\\\\u05d1\\\\u05e8\\\\u05ea\\\\u05d9\\\\u05d5\\\\u05ea\\"},\\"hi\\":{\\

"name\\":\\"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"hr\\":{\\"name\\":\\"Dru\\\\u0161tvene i k

omunikacijske aplikacije\\",\\"description\\":\\"Aplikacije za razmjenu poruka, upravljanje kontaktima i dru\\\\u0161tveni mediji\\"},\\"hsb\\":{\\"name\\":\\

"Social & communication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"sr\\":{\\"name\\":\\"\\\\u0414\\\\u0440\\\\u0443\\\\u0448

\\\\u0442\\\\u0432\\\\u0435\\\\u043d\\\\u0435 \\\\u043c\\\\u0440\\\\u0435\\\\u0436\\\\u0435 & \\\\u043a\\\\u043e\\\\u043c\\\\u0443\\\\u043d\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\

u0458\\\\u0430\\",\\"description\\":\\"\\\\u040b\\\\u0430\\\\u0441\\\\u043a\\\\u0430\\\\u045a\\\\u0435, \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u0459\\\\u0430\\\\u045a\\\\u043

5 \\\\u043a\\\\u043e\\\\u043d\\\\u0442\\\\u0430\\\\u043a\\\\u0442\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\

u0435 \\\\u0434\\\\u0440\\\\u0443\\\\u0448\\\\u0442\\\\u0432\\\\u0435\\\\u043d\\\\u0438\\\\u0445 \\\\u043c\\\\u0440\\\\u0435\\\\u0436\\\\u0430\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u041

4\\\\u0440\\\\u0443\\\\u0448\\\\u0442\\\\u0432\\\\u0435\\\\u043d\\\\u0435 \\\\u043c\\\\u0440\\\\u0435\\\\u0436\\\\u0435 & \\\\u043a\\\\u043e\\\\u043c\\\\u0443\\\\u043d\\\\u0438\\\\u043a\\

\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0430\\",\\"description\\":\\"\\\\u040b\\\\u0430\\\\u0441\\\\u043a\\\\u0430\\\\u045a\\\\u0435, \\\\u0443\\\\u043f\\\\u0440\\\\u0430\\\\u0432\\\\u04

59\\\\u0430\\\\u045a\\\\u0435 \\\\u043a\\\\u043e\\\\u043d\\\\u0442\\\\u0430\\\\u043a\\\\u0442\\\\u0438\\\\u043c\\\\u0430 \\\\u0438 \\\\u0430\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\

\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0434\\\\u0440\\\\u0443\\\\u0448\\\\u0442\\\\u0432\\\\u0435\\\\u043d\\\\u0438\\\\u0445 \\\\u043c\\\\u0440\\\\u0435\\\\u0436\\\\u0430\\"},\\"sv\\":{

\\"name\\":\\"Socialt & kommunikation\\",\\"description\\":\\"Meddelande, kontaktadministration och social media appar\\"},\\"sw\\":{\\"name\\":\\"Social & com

munication\\",\\"description\\":\\"Messaging, contact management and social media apps\\"},\\"ta\\":{\\"name\\":\\"Social & communication\\",\\"description\\":

\\"Messaging, contact management and social media apps\\"}}},{\\"id\\":\\"tools\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everyt

hing else\\"},\\"fr\\":{\\"name\\":\\"Outils\\",\\"description\\":\\"Tout le reste\\"},\\"fy\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ga\\"

:{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"gd\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ru\\":{\\"name\\":\\"\\\\u04

1f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f\\",\\"description\\":\\"\\\\u0427\\\\u0442\\\\u043e-\\\\u0442\\\\u043e \\\\u0435\\\\u0449\\\\u0435\\"

},\\"sk\\":{\\"name\\":\\"N\\\\u00e1stroje\\",\\"description\\":\\"V\\\\u0161etko ostatn\\\\u00e9\\"},\\"sl\\":{\\"name\\":\\"Orodja\\",\\"description\\":\\"Razli\\\\u010dna

 orodja za razli\\\\u010dne dejavnosti\\"},\\"sq\\":{\\"name\\":\\"Mjete\\",\\"description\\":\\"\\\\u00c7do gj\\\\u00eb tjet\\\\u00ebr\\"},\\"hu\\":{\\"name\\":\\"Eszk\\\\

u00f6z\\\\u00f6k\\",\\"description\\":\\"Minden m\\\\u00e1s\\"},\\"hy\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ia\\":{\\"name\\":\\"Tools\\",

\\"description\\":\\"Everything else\\"},\\"id\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"io\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"

Everything else\\"},\\"is\\":{\\"name\\":\\"Verkf\\\\u00e6ri\\",\\"description\\":\\"Allt anna\\\\u00f0\\"},\\"it\\":{\\"name\\":\\"Strumenti\\",\\"description\\":\\"Tutt

o il resto\\"},\\"ja\\":{\\"name\\":\\"\\\\u30c4\\\\u30fc\\\\u30eb\\",\\"description\\":\\"\\\\u305d\\\\u306e\\\\u4ed6\\\\u3059\\\\u3079\\\\u3066\\"},\\"ka\\":{\\"name\\":\\"\\\\u10e

e\\\\u10d4\\\\u10da\\\\u10e1\\\\u10d0\\\\u10ec\\\\u10e7\\\\u10dd\\\\u10d4\\\\u10d1\\\\u10d8\\",\\"description\\":\\"\\\\u10d3\\\\u10d0\\\\u10dc\\\\u10d0\\\\u10e0\\\\u10e9\\\\u10d4\\\\u10

dc\\\\u10d8 \\\\u10e1\\\\u10ee\\\\u10d5\\\\u10d0\\"},\\"kab\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"kk\\":{\\"name\\":\\"Tools\\",\\"descriptio

n\\":\\"Everything else\\"},\\"km\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"kn\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything e

lse\\"},\\"ko\\":{\\"name\\":\\"\\\\ub3c4\\\\uad6c\\",\\"description\\":\\"\\\\ub2e4\\\\ub978 \\\\ubaa8\\\\ub4e0 \\\\uac83\\"},\\"lb\\":{\\"name\\":\\"Tools\\",\\"description\\":\\

"Everything else\\"},\\"lt\\":{\\"name\\":\\"\\\\u012erankiai\\",\\"description\\":\\"Visa kita\\"},\\"lv\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything els

e\\"},\\"mk\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ml\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"mn\\":{\\"nam

e\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"mr\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"my\\":{\\"name\\":\\"Tools\\",\\"de

scription\\":\\"Everything else\\"},\\"nb\\":{\\"name\\":\\"Verkt\\\\u00f8y\\",\\"description\\":\\"Alt annet\\"},\\"ne\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Ev

erything else\\"},\\"te\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"th\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\

"tr\\":{\\"name\\":\\"Ara\\\\u00e7lar\\",\\"description\\":\\"Di\\\\u011fer uygulamalar\\"},\\"tt\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"u

dm\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"uk\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"af\\":{\\"name\\":\\"T

ools\\",\\"description\\":\\"Everything else\\"},\\"ar\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ast\\":{\\"name\\":\\"Tools\\",\\"descript

ion\\":\\"Everything else\\"},\\"az\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"bg\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything

 else\\"},\\"be\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ur\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"vi\\":{\\

"name\\":\\"C\\\\u00f4ng c\\\\u1ee5\\",\\"description\\":\\"M\\\\u1ecdi th\\\\u1ee9 kh\\\\u00e1c\\"},\\"zh-hans\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything e

lse\\"},\\"zh-hant\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"bn\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"br\\"

:{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"bs\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"ca\\":{\\"name\\":\\"Eines

\\",\\"description\\":\\"Tota la resta\\"},\\"cs\\":{\\"name\\":\\"N\\\\u00e1stroje\\",\\"description\\":\\"V\\\\u0161e ostatn\\\\u00ed\\"},\\"cy\\":{\\"name\\":\\"Tools\\",

\\"description\\":\\"Everything else\\"},\\"da\\":{\\"name\\":\\"V\\\\u00e6rkt\\\\u00f8jer\\",\\"description\\":\\"Alt andet\\"},\\"de\\":{\\"name\\":\\"Werkzeuge\\",\\"de

scription\\":\\"Alles Andere\\"},\\"dsb\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"el\\":{\\"name\\":\\"\\\\u0395\\\\u03c1\\\\u03b3\\\\u03b1\\\\u0

3bb\\\\u03b5\\\\u03af\\\\u03b1\\",\\"description\\":\\"\\\\u039f\\\\u03c4\\\\u03b9\\\\u03b4\\\\u03ae\\\\u03c0\\\\u03bf\\\\u03c4\\\\u03b5 \\\\u03ac\\\\u03bb\\\\u03bb\\\\u03bf\\"},\\"eo\\

":{\\"name\\":\\"Iloj\\",\\"description\\":\\"\\\\u0108io cetera\\"},\\"es\\":{\\"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u00e1s\\"},\\"es-ar\\":{\\

"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u00e1s\\"},\\"es-co\\":{\\"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u00e1s\\"},\\"

es-mx\\":{\\"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u00e1s\\"},\\"es-ni\\":{\\"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u0

0e1s\\"},\\"es-ve\\":{\\"name\\":\\"Herramientas\\",\\"description\\":\\"Todo lo dem\\\\u00e1s\\"},\\"et\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else

\\"},\\"eu\\":{\\"name\\":\\"Tresnak\\",\\"description\\":\\"Beste guztia\\"},\\"nl\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"De rest\\"},\\"fa\\":{\\"name\\":\\"\\\\u0

627\\\\u0628\\\\u0632\\\\u0627\\\\u0631\\\\u0647\\\\u0627\\",\\"description\\":\\"\\\\u0647\\\\u0645\\\\u0647 \\\\u0686\\\\u06cc\\\\u0632 \\\\u062f\\\\u06cc\\\\u06af\\\\u0631\\"},\\"nn

\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"fi\\":{\\"name\\":\\"Ty\\\\u00f6kalut\\",\\"description\\":\\"Kaikki muu\\"},\\"os\\":{\\"name\\":\\

"Tools\\",\\"description\\":\\"Everything else\\"},\\"pa\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"pl\\":{\\"name\\":\\"Narz\\\\u0119dzia\\"

,\\"description\\":\\"Wszystko inne\\"},\\"pt\\":{\\"name\\":\\"Ferramentas\\",\\"description\\":\\"Tudo o resto\\"},\\"pt-br\\":{\\"name\\":\\"Ferramentas\\",\\"descr

iption\\":\\"Tudo mais\\"},\\"ro\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"},\\"gl\\":{\\"name\\":\\"Ferramentas\\",\\"description\\":\\"Todo o 

demais\\"},\\"he\\":{\\"name\\":\\"\\\\u05db\\\\u05dc\\\\u05d9\\\\u05dd\\",\\"description\\":\\"\\\\u05db\\\\u05dc \\\\u05d4\\\\u05e9\\\\u05d0\\\\u05e8\\"},\\"hi\\":{\\"name\\":\\"To

ols\\",\\"description\\":\\"Everything else\\"},\\"hr\\":{\\"name\\":\\"Alati\\",\\"description\\":\\"Sve ostalo\\"},\\"hsb\\":{\\"name\\":\\"Tools\\",\\"description\\":

\\"Everything else\\"},\\"sr\\":{\\"name\\":\\"\\\\u0410\\\\u043b\\\\u0430\\\\u0442\\\\u0438\\",\\"description\\":\\"\\\\u0421\\\\u0432\\\\u0435 \\\\u043e\\\\u0441\\\\u0442\\\\u0430

\\\\u043b\\\\u043e\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0410\\\\u043b\\\\u0430\\\\u0442\\\\u0438\\",\\"description\\":\\"\\\\u0421\\\\u0432\\\\u0435 \\\\u043e\\\\u0441\\\\u0442\\\\u04

30\\\\u043b\\\\u043e\\"},\\"sv\\":{\\"name\\":\\"Verktyg\\",\\"description\\":\\"Allting annat\\"},\\"sw\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"

},\\"ta\\":{\\"name\\":\\"Tools\\",\\"description\\":\\"Everything else\\"}}},{\\"id\\":\\"workflow\\",\\"translations\\":{\\"en\\":{\\"name\\":\\"Flow\\",\\"description

\\":\\"Apps for Nextcloud Flow\\"},\\"fr\\":{\\"name\\":\\"Flux\\",\\"description\\":\\"Application pour le flux Nextcloud \\"},\\"fy\\":{\\"name\\":\\"Flow\\",\\"des

cription\\":\\"Apps for Nextcloud Flow\\"},\\"ga\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"gd\\":{\\"name\\":\\"Flow\\",\\"descrip

tion\\":\\"Apps for Nextcloud Flow\\"},\\"ru\\":{\\"name\\":\\"\\\\u041e\\\\u0431\\\\u0440\\\\u0430\\\\u0431\\\\u043e\\\\u0442\\\\u043a\\\\u0430 \\\\u0444\\\\u0430\\\\u0439\\\\u043

b\\\\u043e\\\\u0432\\",\\"description\\":\\"\\\\u041f\\\\u0440\\\\u0438\\\\u043b\\\\u043e\\\\u0436\\\\u0435\\\\u043d\\\\u0438\\\\u044f \\\\u0434\\\\u043b\\\\u044f Nextcloud Flow\\"}

,\\"sk\\":{\\"name\\":\\"Flow (tok)\\",\\"description\\":\\"Aplik\\\\u00e1cie pre Nextcloud Flow (tok)\\"},\\"sl\\":{\\"name\\":\\"Kora\\\\u010dnik (Flow)\\",\\"descri

ption\\":\\"Programi za Nextcloud Flow\\"},\\"sq\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"hu\\":{\\"name\\":\\"Flow\\",\\"descrip

tion\\":\\"Alkalmaz\\\\u00e1sok a Nextcloud Flowhoz\\"},\\"hy\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"ia\\":{\\"name\\":\\"Flow\\

",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"id\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"io\\":{\\"name\\":\\"Flow\\",\\"

description\\":\\"Apps for Nextcloud Flow\\"},\\"is\\":{\\"name\\":\\"Fl\\\\u00e6\\\\u00f0i\\",\\"description\\":\\"Forrit fyrir Nextcloud Flow fl\\\\u00e6\\\\u00f0i\\

"},\\"it\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Applicazioni per Nextcloud Flow\\"},\\"ja\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Nextcloud Flow\\\\u306

e\\\\u30a2\\\\u30d7\\\\u30ea\\"},\\"ka\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"kab\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps

 for Nextcloud Flow\\"},\\"kk\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"km\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for

 Nextcloud Flow\\"},\\"kn\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"ko\\":{\\"name\\":\\"\\\\ud750\\\\ub984\\",\\"description\\":\\"Ap

ps for Nextcloud Flow\\"},\\"lb\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"lt\\":{\\"name\\":\\"Eiga\\",\\"description\\":\\"Apps f

or Nextcloud Flow\\"},\\"lv\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"mk\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for N

extcloud Flow\\"},\\"ml\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"mn\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextc

loud Flow\\"},\\"mr\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"my\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud

 Flow\\"},\\"nb\\":{\\"name\\":\\"Flyt\\",\\"description\\":\\"Apper til Nextcloud Flow\\"},\\"ne\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Fl

ow\\"},\\"te\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"th\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"

},\\"tr\\":{\\"name\\":\\"Ak\\\\u0131\\\\u015f\\",\\"description\\":\\"Nextcloud Ak\\\\u0131\\\\u015f Uygulamalar\\\\u0131\\"},\\"tt\\":{\\"name\\":\\"Flow\\",\\"description

\\":\\"Apps for Nextcloud Flow\\"},\\"udm\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"uk\\":{\\"name\\":\\"Flow\\",\\"description\\":

\\"Apps for Nextcloud Flow\\"},\\"af\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"ar\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Ap

ps for Nextcloud Flow\\"},\\"ast\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"az\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps 

for Nextcloud Flow\\"},\\"bg\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"be\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for 

Nextcloud Flow\\"},\\"ur\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"vi\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"\\\\u1ee8ng d\\\\

u1ee5ng cho Flow\\"},\\"zh-hans\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"zh-hant\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"A

pps for Nextcloud Flow\\"},\\"bn\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"br\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps 

for Nextcloud Flow\\"},\\"bs\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"ca\\":{\\"name\\":\\"Flux\\",\\"description\\":\\"Aplicacio

ns per Nextcloud Flow\\"},\\"cs\\":{\\"name\\":\\"Flow (tok)\\",\\"description\\":\\"Aplikace pro Nextcloud Flow\\"},\\"cy\\":{\\"name\\":\\"Flow\\",\\"description\\

":\\"Apps for Nextcloud Flow\\"},\\"da\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"de\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"

Apps f\\\\u00fcr Nextcloud Flow\\"},\\"dsb\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"el\\":{\\"name\\":\\"\\\\u03a1\\\\u03bf\\\\u03ae\\

",\\"description\\":\\"\\\\u0395\\\\u03c6\\\\u03b1\\\\u03c1\\\\u03bc\\\\u03bf\\\\u03b3\\\\u03ad\\\\u03c2 \\\\u03b3\\\\u03b9\\\\u03b1 \\\\u03c4\\\\u03b7 \\\\u03a1\\\\u03bf\\\\u03ae \\\\u

03c4\\\\u03bf\\\\u03c5 Nextcloud\\"},\\"eo\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"es\\":{\\"name\\":\\"Flujo\\",\\"description\\":

\\"Apps para Nextcloud Flow\\"},\\"es-ar\\":{\\"name\\":\\"Flujo\\",\\"description\\":\\"Apps para Nextcloud Flow\\"},\\"es-co\\":{\\"name\\":\\"Flujo\\",\\"descript

ion\\":\\"Apps para Nextcloud Flow\\"},\\"es-mx\\":{\\"name\\":\\"Flujo\\",\\"description\\":\\"Apps para Nextcloud Flow\\"},\\"es-ni\\":{\\"name\\":\\"Flujo\\",\\"de

scription\\":\\"Apps para Nextcloud Flow\\"},\\"es-ve\\":{\\"name\\":\\"Flujo\\",\\"description\\":\\"Apps para Nextcloud Flow\\"},\\"et\\":{\\"name\\":\\"Flow\\",\\"

description\\":\\"Apps for Nextcloud Flow\\"},\\"eu\\":{\\"name\\":\\"Fluxua\\",\\"description\\":\\"Nextcloud Flow-rako aplikazioak\\"},\\"nl\\":{\\"name\\":\\"Flo

w\\",\\"description\\":\\"Apps voor Nextcloud Flow\\"},\\"fa\\":{\\"name\\":\\"\\\\u062c\\\\u0631\\\\u06cc\\\\u0627\\\\u0646\\",\\"description\\":\\"\\\\u0628\\\\u0631\\\\u0646

\\\\u0627\\\\u0645\\\\u0647 \\\\u0647\\\\u0627\\\\u06cc\\\\u06cc \\\\u0628\\\\u0631\\\\u0627\\\\u06cc \\\\u062c\\\\u0631\\\\u06cc\\\\u0627\\\\u0646 \\\\u0646\\\\u06a9\\\\u0633\\\\u062a \\

\\u06a9\\\\u0644\\\\u0648\\\\u062f\\"},\\"nn\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"fi\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"

Sovellukset Nextcloud Flow:lle\\"},\\"os\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"pa\\":{\\"name\\":\\"Flow\\",\\"description\\"

:\\"Apps for Nextcloud Flow\\"},\\"pl\\":{\\"name\\":\\"Przep\\\\u0142yw\\",\\"description\\":\\"Aplikacje dla Nextcloud Flow\\"},\\"pt\\":{\\"name\\":\\"Fluxo\\",\\"d

escription\\":\\"Apps for Nextcloud Flow\\"},\\"pt-br\\":{\\"name\\":\\"Fluxo\\",\\"description\\":\\"Aplicativos para Nextcloud Fluxo\\"},\\"ro\\":{\\"name\\":\\"F

low\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"gl\\":{\\"name\\":\\"Fluxo\\",\\"description\\":\\"Aplicaci\\\\u00f3ns para o Fluxo de Nextcloud\\"},\\"h

e\\":{\\"name\\":\\"\\\\u05e8\\\\u05e6\\\\u05e3\\",\\"description\\":\\"Apps for Nextcloud Flow\\"},\\"hi\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextclou

d Flow\\"},\\"hr\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Aplikacije za Nextcloud Flow\\"},\\"hsb\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcl

oud Flow\\"},\\"sr\\":{\\"name\\":\\"\\\\u0422\\\\u043e\\\\u043a\\",\\"description\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\

u0437\\\\u0430 \\\\u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043b\\\\u0430\\\\u0443\\\\u0434 Flow\\"},\\"sr-latn\\":{\\"name\\":\\"\\\\u0422\\\\u043e\\\\u043a\\",\\"desc

ription\\":\\"\\\\u0410\\\\u043f\\\\u043b\\\\u0438\\\\u043a\\\\u0430\\\\u0446\\\\u0438\\\\u0458\\\\u0435 \\\\u0437\\\\u0430 \\\\u041d\\\\u0435\\\\u043a\\\\u0441\\\\u0442\\\\u043a\\\\u043

b\\\\u0430\\\\u0443\\\\u0434 Flow\\"},\\"sv\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Appar f\\\\u00f6r Nextcloud Flow\\"},\\"sw\\":{\\"name\\":\\"Flow\\",\\"descripti

on\\":\\"Apps for Nextcloud Flow\\"},\\"ta\\":{\\"name\\":\\"Flow\\",\\"description\\":\\"Apps for Nextcloud Flow\\"}}}\]",

            "enabled": "no",

            "installed\_version": "2.4.0",

            "types": ""

        },

        "smb\_test": {

            "enabled": "no",

            "installed\_version": "0.3.4",

            "types": ""

        },

        "sms\_relentless": {

            "enabled": "no",

            "installed\_version": "1.0.5",

            "types": ""

        },

        "sociallogin": {

            "allow\_login\_connect": "1",

            "auto\_create\_groups": "",

            "create\_disabled\_users": "",

            "custom\_providers": "null",

            "disable\_notify\_admins": "",

            "disable\_registration": "",

            "enabled": "yes",

            "hide\_default\_login": "",

            "installed\_version": "4.15.3",

            "no\_prune\_user\_groups": "",

            "oauth\_providers": "{\\"google\\":{\\"appid\\":\\"[admin@cloud9.ctrlaltback.space](mailto:admin@cloud9.ctrlaltback.space)\\",\\"secret\\":\\"\[Mlp321Zaq\]\\",\\"defaultGroup\\":\\"Users\\",\\"au

th\_params\\":{\\"hd\\":\\"\\"}},\\"amazon\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"},\\"facebook\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaul

tGroup\\":\\"\\"},\\"twitter\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"},\\"GitHub\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"

,\\"orgs\\":\\"\\"},\\"discord\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\",\\"guilds\\":\\"\\"},\\"QQ\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaul

tGroup\\":\\"\\"},\\"slack\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"},\\"telegram\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"

},\\"mailru\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\"},\\"yandex\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\",\\"auth\_params

\\":{\\"hd\\":\\"\\"}},\\"BitBucket\\":{\\"appid\\":\\"\\",\\"secret\\":\\"\\",\\"defaultGroup\\":\\"\\",\\"workspace\\":\\"\\"}}",


            "prevent\_create\_email\_exists": "",

            "restrict\_users\_wo\_assigned\_groups": "",

            "restrict\_users\_wo\_mapped\_groups": "",

            "types": "",

            "update\_profile\_on\_login": ""

        },

        "socialsharing\_email": {

            "enabled": "yes",

            "installed\_version": "2.5.0",

            "types": ""

        },

        "socialsharing\_facebook": {

            "enabled": "yes",

            "installed\_version": "2.5.0",

            "types": ""

        },

        "socialsharing\_twitter": {

            "enabled": "yes",

            "installed\_version": "2.5.0",

            "types": ""

        },

        "spreed": {

            "enabled": "no",

            "has\_reference\_id": "yes",

            "installed\_version": "14.0.3",

            "project\_access\_invalidated": "1",

            "types": "dav,prevent\_group\_restriction"

        },

        "support": {

            "SwitchUpdaterServerHasRun": "yes",

            "enabled": "no",

            "installed\_version": "1.7.0",

            "types": "session"

        },

        "survey\_client": {

            "enabled": "no",

            "installed\_version": "1.12.0",

            "types": ""

        },

        "systemtags": {

            "enabled": "no",

            "installed\_version": "1.14.0",

            "types": "logging"

        },

        "tables": {

            "enabled": "no",

            "installed\_version": "0.1.2",

            "types": ""

        },

        "talked": {

            "enabled": "no",

            "installed\_version": "0.4.0",

            "types": ""

        },

        "terms\_of\_service": {

            "enabled": "no",

            "installed\_version": "1.10.2",

            "types": "filesystem,dav"

        },

        "text": {

            "enabled": "yes",

            "installed\_version": "3.5.1",

            "types": "dav"

        },

        "theming": {

            "cachebuster": "16",

            "color": "#02BCEB",

            "enabled": "yes",

            "faviconMime": "image\\/png",

            "installed\_version": "1.15.0",

            "logoMime": "image\\/png",

            "logoheaderMime": "image\\/png",

            "name": "CLOUD9",

            "slogan": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*",

            "types": "logging",

            "url": "\*\*\*REMOVED SENSITIVE VALUE\*\*\*"

        },

        "theming\_customcss": {

            "enabled": "no",

            "installed\_version": "1.11.0",

            "types": ""

        },

        "transfer": {

            "enabled": "yes",

            "installed\_version": "0.5.2",

            "types": ""

        },

        "twofactor\_backupcodes": {

            "enabled": "yes",

            "installed\_version": "1.13.0",

            "types": ""

        },

        "updatenotification": {

            "core": "24.0.2.1",

            "duplicatefinder": "0.0.15",

            "enabled": "yes",

            "installed\_version": "1.14.0",

            "mail": "1.13.6",

            "types": "",

            "update\_check\_errors": "0"

        },

        "uppush": {

            "enabled": "no",

            "installed\_version": "1.0.6",

            "types": ""

        },

        "user\_external": {

            "enabled": "yes",

            "installed\_version": "3.0.0",

            "types": "prelogin,authentication"

        },

        "user\_migration": {

            "enabled": "yes",

            "installed\_version": "1.0.4",

            "types": ""

        },

        "user\_status": {

            "enabled": "yes",

            "installed\_version": "1.4.0",

            "types": ""

        },

        "user\_usage\_report": {

            "enabled": "yes",

            "installed\_version": "1.8.0",

            "types": "filesystem"

        },

        "video\_converter": {

            "enabled": "no",

            "installed\_version": "1.0.5",

            "types": ""

        },

        "viewer": {

            "enabled": "yes",

            "installed\_version": "1.8.0",

            "types": ""

        },

        "weather\_status": {

            "enabled": "no",

            "installed\_version": "1.4.0",

            "types": ""

        },

        "webhooks": {

            "enabled": "yes",

            "installed\_version": "0.3.0",

            "types": ""

        },

        "whereami": {

            "enabled": "no",

            "installed\_version": "0.0.6",

            "types": ""

        },

        "workflow\_ocr": {

            "enabled": "no",

            "installed\_version": "1.24.3",

            "types": "filesystem"

        },

        "workflow\_script": {

            "enabled": "no",

            "installed\_version": "1.8.0",

            "types": "filesystem"

        },

        "workflowengine": {

            "enabled": "yes",

            "installed\_version": "2.6.0",

            "types": "filesystem"

        }

   }

}
```