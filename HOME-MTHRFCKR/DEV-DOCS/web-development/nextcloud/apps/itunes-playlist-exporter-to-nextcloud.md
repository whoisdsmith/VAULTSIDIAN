---
tags:: apps
---
# iTunes Playlist exporter to Nextcloud / Owncloud Music app

The Music app for Nextcloud / Owncloud does not come with a playlist importation tool. This little XSLT transformation takes the 'iTunes Music Library' XML file and generates SQL queries for your MYSQL database.

## Getting Started


### Prerequisites
For importing playlist into the database you need to have admin privileges. 
#### SAXON
The XSLT processor to use is Saxon, as this transformation makes use of non compatible XSLT 1.0 functionalities.

#### XSLT file
Replace your username in the XSLT file and your library name if you wish to evict the native 'Library' playlist. Note that the library name must be set in your system language (e.g. for a system language set in French it would be 'Bibliothèque').

#### Music importation
The tracks needs to be imported into the database prior to importing the playlists. Do so and run
```
occ music:cleanup
occ music:scan USERNAME
```

## Importing the playlists 



### First

Do the XSLT transformation by running

```
saxon "iTunes Music Library.xml" xml_to_sql.xsl >> output.sql
```

### Then

Run the queries into the database

```
mysql -u MYSQLUSERNAME --pYOURPASSWORD YOURDATABASENAME -e "source output.sql;"
```
**Some errors will be prompted to the terminal if there are duplicates (tracks with same title, artist and album). These will not be added to your playlists.**
### Finally 
Enjoy your playlists in the Music app. This tool can of course be automated using cron or any automation tool.


