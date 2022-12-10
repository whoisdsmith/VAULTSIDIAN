# Filters

To help users easily find their content you can suggest context aware filters like we have in Raindrop.io app

[![Filters right above search field](https://github.com/raindropio/developer-site/raw/master/.gitbook/assets/filters%20(1).png)](https://github.com/raindropio/developer-site/blob/master/.gitbook/assets/filters%20(1).png)

## [](https://github.com/raindropio/developer-site/blob/master/v1/filters.md#fields)Fields

| Field | Type | Description |
| --- | --- | --- |
| broken | `Object` |  |
| broken.count | `Integer` | Broken links count |
| duplicates | `Object` |  |
| duplicates.count | `Integer` | Duplicate links count |
| important | `Object` |  |
| important.count | `Integer` | Count of raindrops that marked as "favorite" |
| notag | `Object` |  |
| notag.count | `Integer` | Count of raindrops without any tag |
| tags | `Array<Object>` | List of tags in format `{"_id": "tag name", "count": 1}` |
| types | `Array<Object>` | List of types in format `{"_id": "type", "count": 1}` |

{% swagger baseUrl="[https://api.raindrop.io](https://api.raindrop.io)" path="/rest/v1/raindrops/{collectionId}/filters" method="get" summary="Get filters" %} {% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="path" name="collectionId" type="string" %} Collection ID.

`0`

for all {% endswagger-parameter %}

{% swagger-parameter in="query" name="tagsSort" type="string" %} Sort tags by:

\\

**`-count`**

by count, default

\\

**`_id`**

by name {% endswagger-parameter %}

{% swagger-parameter in="query" name="search" type="string" %} Check "raindrops" documentation for more details {% endswagger-parameter %}

{% swagger-response status="200" description="" %}

```js
{
  "result": true,
  "broken": {
    "count": 31
  },
  "duplicates": {
    "count": 7
  },
  "important": {
    "count": 59
  },
  "notag": {
    "count": 1366
  },
  "tags": [
    {
      "_id": "performanc",
      "count": 19
    },
    {
      "_id": "guides",
      "count": 9
    }
  ],
  "types": [
    {
      "_id": "article",
      "count": 313
    },
    {
      "_id": "image",
      "count": 143
    },
    {
      "_id": "video",
      "count": 26
    },
    {
      "_id": "document",
      "count": 7
    }
  ]
}
```

{% endswagger-response %} {% endswagger %}
