# Search for Item

[

OAuth 2.0



](https://developer.spotify.com/documentation/web-api/reference/#/operations/search#/?security=oauth_2_0)

Get Spotify catalog information about albums, artists, playlists, tracks, shows or episodes that match a keyword string.

Request

get /search

Query

q

string

required

Your search query.

You can narrow down your search using field filters. The available filters are `album`, `artist`, `track`, `year`, `upc`, `tag:hipster`, `tag:new`, `isrc`, and `genre`. Each field filter only applies to certain result types.

The `artist` filter can be used while searching albums, artists or tracks.  
The `album` and `year` filters can be used while searching albums or tracks. You can filter on a single `year` or a range (e.g. 1955-1960).  
The `genre` filter can be use while searching tracks and artists.  
The `isrc` and `track` filters can be used while searching tracks.  
The `upc`, `tag:new` and `tag:hipster` filters can only be used while searching albums. The `tag:new` filter will return albums released in the past two weeks and `tag:hipster` can be used to return only albums with the lowest 10% popularity.  

You can also use the `NOT` operator to exclude keywords from your search.

Example value:"remaster%20track:Doxy+artist:Miles%20Davis"

type

array

required

A comma-separated list of item types to search across. Search results include hits from all the specified item types. For example: `q=name:abacab&type=album,track` returns both albums and tracks with "abacab" included in their name.

Allowed values:"album""artist""playlist""track""show""episode"

Example value:"track,artist"

include\_external

string

If `include_external=audio` is specified it signals that the client can play externally hosted audio content, and marks the content as playable in the response. By default externally hosted audio content is marked as unplayable in the response.

Allowed value:"audio"

limit

integer

The maximum number of results to return in each item type.

\>= 0<= 50

Default value:20

Example value:10

market

string

An [ISO 3166-1 alpha-2 country code](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2). If a country code is specified, only content that is available in that market will be returned.  
If a valid user access token is specified in the request header, the country associated with the user account will take priority over this parameter.  
_**Note**: If neither market or user country are provided, the content is considered unavailable for the client._  
Users can view the country that is associated with their account in the [account settings](https://www.spotify.com/se/account/overview/).

Example value:"ES"

offset

integer

The index of the first result to return. Use with limit to get the next page of search results.

\>= 0<= 1000

Default value:0

Example value:5

Responses

200

401

403

429

Search response

Body

application/json

application/json

tracks

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.

artists

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.

albums

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.

playlists

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.

shows

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.

episodes

object

href

string

required

A link to the Web API endpoint returning the full result of the request

items

array of objects

required

The requested content

limit

integer

required

The maximum number of items in the response (as set in the query or by default).

next

string

required

URL to the next page of items. ( `null` if none)

offset

integer

required

The offset of the items returned (as set in the query or by default)

previous

string

required

URL to the previous page of items. ( `null` if none)

total

integer

required

The total number of items available to return.