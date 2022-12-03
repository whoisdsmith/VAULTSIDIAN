# Make API documentation

### Fundamentals

The Make REST API allows using HTTP requests to access Make data and control the Make platform without opening its graphical interface. This allows you to embed Make features into your software, add features on top of the platform, and automate your tasks that you perform in Make. To use the Make API, you need an Make account. Once logged in, you can [generate an authentication token](https://www.make.com/en/api-documentation/authentication-token#authentication-token) and [start making calls to the API](https://www.make.com/en/api-documentation/getting-started#getting-started).

The API allows you to interact with multiple [Make resources](https://www.make.com/en/api-documentation/api-resources#api-resources). This documentation covers the following API resources:

-   [Connections](https://www.make.com/en/api-documentation/connections#connections)
-   [Data stores](https://www.make.com/en/api-documentation/data-stores#data-stores)
-   [Data structures](https://www.make.com/en/api-documentation/data-structures#data-structures)
-   [Hooks](https://www.make.com/en/api-documentation/hooks#hooks)
-   [Notifications](https://www.make.com/en/api-documentation/notifications#notifications)
-   [Scenarios](https://www.make.com/en/api-documentation/scenarios#scenarios)
-   [Scenarios folders](https://www.make.com/en/api-documentation/scenarios-folders#scenarios-folders)
-   [Templates](https://www.make.com/en/api-documentation/templates#templates)
-   [Users](https://www.make.com/en/api-documentation/users#users)

The following API resources are fully functional, but are not covered in this documentation yet:

-   Custom apps
-   Devices
-   Keys
-   Organizations
-   Teams

#### Make API structure

The root URL of the Make API consists of three parts and looks as follows:  
`{environment_url}/api/v2/{api_endpoint}`

**Environment URL**  
The environment of Make you work in. This can be the link to your private instance of Make, for example, `https://development.make.cloud`, or the link to Make (with or without the zone, depending on a specific endpoint), for example, `https://eu1.make.com`.

Always use HTTPS in your API requests.

**API version**  
The version of the API preceded by `/api/`

**Endpoint** **(with or without parameters)**  
Each endpoint represents a resource that you can work with. Endpoints contain required and/or optional parameters. The resources are described in detail in [Make resources](https://www.make.com/en/api-documentation/api-resources#api-resources).

#### HTTP methods

Make API uses standard HTTP methods to interact with endpoints. The following table lists the available HTTP methods and shows examples of endpoints these methods can be used with.

| **HTTP method** | **Description** |
| --- | --- |
| 
```
GET
```

 | 

Retrieves a resource representation without modifying it.

_Example:_  
[`/scenarios`](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-get)  
_returns all available Make scenarios_ |
| 

```
POST
```

 | 

Creates a resource.

_Example:_  
[`/scenarios`](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-post)  
_creates a scenario_ |
| 

```
PUT
```

 | 

Updates a resource. If the resource does not exist yet, this method creates it.

_Example:_  
[`/scenarios/{scenarioId}/data`](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-data-put)  
_sets module data for a scenario with a given ID_ |
| 

```
PATCH
```

 | 

Makes a partial update on a resource. Does not replace the entire resource.

_Example:_  
[`/scenarios/{scenarioId}`](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-patch)  
_updates properties (for example, scheduling or blueprint) of the scenario with a given ID_ |
| 

```
DELETE
```

 | 

Removes a resource.

_Example:_  
[`/scenarios/{scenarioId}`](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-delete)  
_deletes the scenario with a given ID_ |

### Getting started

This start guide will take you through making your first request to the Make API.

_Example:_  
_Let's imagine that you would like to list all data stores available in your team. Your team ID is 35. Returned data should be ordered in descending order._

To make your first API call, you need to perform the following actions:

How to:

1.  **Create an authentication token**. The token gives you access to Make API resources depending on your [Make role and assigned scopes](https://www.make.com/en/api-documentation/users-password-reset-post#authentication-scopes). You must include the token in the **Authorization** header of all requests. Add the word **Token** and a space before the token itself:  
    `'Authorization: Token {Your authentication token}'`
    
2.  **Choose the** [endpoint](https://www.make.com/en/api-documentation/users-password-reset-post#api-resources) **that corresponds to the resource you want to interact with.** For this example, you need the `/data-stores` endpoint. The endpoint requires the **teamId** query parameter. Place the parameter after the question mark in the endpoint URL. To filter results, you also need the [parameter for ordering data](https://www.make.com/en/api-documentation/users-password-reset-post#pagination-sorting-filtering)—**pg\[sortDir\]**:  
    `{environment_url}/api/v2/data-stores?teamId={teamId}&pg%5BsortDir%5D=asc`
    
    The environment URL refers to the Make platform you interact with.
    
3.  **Prepare the full request and send it.** In this case, use cURL to making the request. You want to retrieve data without modifying it—use the **GET** method. Let’s put elements from the previous steps together.
    
    The following request example contains a sample authentication token. Don't use it in your requests. [Generate your own token](https://www.make.com/en/api-documentation/users-password-reset-post#authentication-token).
    
    Always include a request body in POST, PUT, or PATCH requests.
    
4.  **Evaluate the response.** The API returns `200 OK` and a list of all data stores for the specified team. If your request failed, you receive an error code. Refer to [Troubleshooting and error handling](https://www.make.com/en/api-documentation/users-password-reset-post#troubleshooting) to troubleshoot the issue.
    

Request

```
curl --location \
--request GET 'https://eu1.make.com/api/v2/data-stores?teamId=35&pg%5BsortDir%5D=asc' \
--header 'Content-Type: application/json' \
--header 'Authorization: Token 93dc8837-2911-4711-a766-59c1167a974d'
```

Response

```
{
  "dataStores": [
    {
      "id": 15043,
      "name": "Old data store",
      "records": 10,
      "size": "620",
      "maxSize": "1048576",
      "teamId": 35
    },
    {
      "id": 13433,
      "name": "New data store",
      "records": 1,
      "size": "48",
      "maxSize": "1048576",
      "teamId": 35
    }
  ],
  "pg": {
    "sortBy": "name",
    "limit": 10000,
    "sortDir": "asc",
    "offset": 0
  }
}
```

### Resources

API resources are grouped into sections corresponding with Make features and components.

Each endpoint resource contains the following details:

#### Methods and endpoints

[Methods](https://www.make.com/en/api-documentation/fundamentals#fundamentals) define the allowed interaction and endpoints define how to access the resource — what URI should be used to interact with a resource.  
_Example:_ `GET /data-stores`

#### Required scopes

Defines what resources you are allowed to interact with based on scopes you selected when generating your [API access token](https://www.make.com/en/api-documentation/authentication-token#authentication-token).  
_Example:_ `datastores:write`

#### Resource description

Describes the expected outcome when using an endpoint, and what Make features the resource relates to.

#### Parameters

These are options you can include with a request to modify the response. Each parameter specifies whether it is required or not. Parameters are divided into two main groups:

-   **Path parameters** — path parameters are always required. They are used to identify or specify the resource (usually by indicating its ID) and they should be placed inside the endpoint URI. Example: `/data-stores/54`
    
-   **Query parameters** — query parameters are often optional. They can be used to specify the resource but they are usually used as [parameters to sort or filter resources](https://www.make.com/en/api-documentation/pagination-sorting-filtering#pagination-sorting-filtering). They are placed at the end of the endpoint URI, after a question mark. Separate multiple parameters with an ampersand symbol. If a parameter contains square brackets, encode them. Example: `/data-stores?teamId=123&pg%5Boffset%5D=10`
    
-   **Request body** — for some endpoints (mainly connected with the POST, PUT, or PATCH HTTP methods), you can also see the Request body section in the endpoint details. This section contains the description of the payload properties that are needed to modify the resource.
    
    Example:
    
    ```
    {
      "name": "Customers",
      "teamId": 123,
      "datastructureId": 178,
      "maxSizeMB": 1
    }
    ```
    

#### Request examples

These are request samples that show how to make a request to the endpoint. They consist of the request URL and authentication token (if needed) and other elements required to make a request in the selected language. Example of request for creating a data store:

#### Response examples

These are response samples you would receive when calling the request in real life. The outcome strictly depends on the request sample. The response schema contains all possible elements available in the response. Each response has its [status code](https://www.make.com/en/api-documentation/http-status-codes#http-status-codes). Example of created data store:

Request

```
curl -X POST https://eu1.make.dev/api/v2/data-stores \
--header 'Content-Type: application/json' \
--header 'Authorization: Token 93dc8837-2911-4711-a766-59c1167a974d' \
-d '{"name":"Customers","teamId":123,"datastructureId":1234,"maxSizeMB":1}'
```

Response

```
{
  "dataStore": {
    "id": 20024,
    "name": "Customers",
    "teamId": "123",
    "datastructureId": 1234,
    "records": 0,
    "size": "0",
    "maxSize": "1048576"
  }
}
```

#### Create scenario folder

##### POST/scenarios-foldersscenarios:write

Creates a new scenario folder with data passed in the request body. As the response, it returns all details of the created scenario folder.

Request body

`name`

`string` REQUIRED

The name of the scenario folder. The name must be at most 100 characters long and does not need to be unique.

Example: ZULU

`teamId`

`integer` REQUIRED

The unique ID of the team in which the scenario folder will be created.

Example: 123

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X POST \
  https://eu1.make.com/api/v2/scenarios-folders \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566' \
  -d '{"name":"ZULU","teamId":123}'
```

Response

-   Value
-   Schema

```
{
  "scenarioFolder": {
    "id": 1576,
    "name": "ALPHA",
    "scenariosTotal": 10
  }
}
```

```
{
  "type": "object",
  "properties": {
    "scenarioFolder": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer"
        },
        "name": {
          "type": "string"
        },
        "scenariosTotal": {
          "type": "integer"
        }
      }
    }
  }
}
```

___

### Public

The following endpoints focus on the public (approved) templates that are available to every user regardless of the organization and team.

### Public

The following endpoints focus on the public (approved) templates that are available to every user regardless of the organization and team.

#### List public (approved) templates

##### GET/templates/publictemplates:read

Retrieves a collection of all public (approved) templates that are available for anyone. Returned templates are sorted by usage in descending order.

Query parameters

`includeEn`

`boolean`

If this parameter is set to `true`, it means English templates should be included in the response. This is relevant only if the user's language is not English.

Example: true

`name`

`string`

The name of the template. This parameter allows limiting returned results to the template(s) with the given name.

Example: my first template

`usedApps[]`

`array [string]`

The array with the text IDs of the apps used in the templates. This parameter allows you to get only the templates containing specific apps.

Example: \[ "http" \]

`cols[]`

`array[Enum<values>]`

Specifies the group of values to return. For example, you may want to retrieve only the names and IDs of the public templates.

`pg[sortBy]`

`string`

The value that will be used to sort returned entities by.

Default: usage

`pg[offset]`

`integer`

The value of entities you want to skip before getting entities you need.

Default: 0

`pg[sortDir]`

Enum<values>

The sorting order. It accepts the ascending and descending direction specifiers.

Default: desc

`pg[limit]`

`integer`

The maximum entities to return.

Default: 100

Maximum: 10000

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/templates/public?includeEn=true&name=my%20first%20template&usedApps%5B%5D=http' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "templatesPublic": [
    {
      "id": 13,
      "name": "Http template example",
      "description": null,
      "url": "13-http-template-example",
      "usedApps": [
        "http"
      ],
      "usage": 321
    },
    {
      "id": 17,
      "name": "Multiple apps template example",
      "description": null,
      "url": "16-multiple-apps-template-example",
      "usedApps": [
        "discord",
        "http",
        "tools",
        "util",
        "gmail"
      ],
      "usage": 52
    }
  ],
  "pg": {
    "sortBy": "usage",
    "limit": 100,
    "sortDir": "desc",
    "offset": 0
  }
}
```

```
{
  "type": "object",
  "properties": {
    "templatesPublic": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer"
          },
          "name": {
            "type": "string"
          },
          "description": {
            "type": "string"
          },
          "url": {
            "type": "string"
          },
          "usedApps": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "usage": {
            "type": "integer"
          }
        }
      }
    },
    "pg": {
      "type": "object",
      "properties": {
        "last": {
          "type": "string"
        },
        "showLast": {
          "type": "boolean"
        },
        "sortBy": {
          "type": "string"
        },
        "sortDir": {
          "type": "string"
        },
        "limit": {
          "type": "integer"
        },
        "offset": {
          "type": "integer"
        }
      }
    }
  }
}
```

___

#### List public (approved) templates

##### GET/templates/publictemplates:read

Retrieves a collection of all public (approved) templates that are available for anyone. Returned templates are sorted by usage in descending order.

Query parameters

`includeEn`

`boolean`

If this parameter is set to `true`, it means English templates should be included in the response. This is relevant only if the user's language is not English.

Example: true

`name`

`string`

The name of the template. This parameter allows limiting returned results to the template(s) with the given name.

Example: my first template

`usedApps[]`

`array [string]`

The array with the text IDs of the apps used in the templates. This parameter allows you to get only the templates containing specific apps.

Example: \[ "http" \]

`cols[]`

`array[Enum<values>]`

Specifies the group of values to return. For example, you may want to retrieve only the names and IDs of the public templates.

`pg[sortBy]`

`string`

The value that will be used to sort returned entities by.

Default: usage

`pg[offset]`

`integer`

The value of entities you want to skip before getting entities you need.

Default: 0

`pg[sortDir]`

Enum<values>

The sorting order. It accepts the ascending and descending direction specifiers.

Default: desc

`pg[limit]`

`integer`

The maximum entities to return.

Default: 100

Maximum: 10000

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/templates/public?includeEn=true&name=my%20first%20template&usedApps%5B%5D=http' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "templatesPublic": [
    {
      "id": 13,
      "name": "Http template example",
      "description": null,
      "url": "13-http-template-example",
      "usedApps": [
        "http"
      ],
      "usage": 321
    },
    {
      "id": 17,
      "name": "Multiple apps template example",
      "description": null,
      "url": "16-multiple-apps-template-example",
      "usedApps": [
        "discord",
        "http",
        "tools",
        "util",
        "gmail"
      ],
      "usage": 52
    }
  ],
  "pg": {
    "sortBy": "usage",
    "limit": 100,
    "sortDir": "desc",
    "offset": 0
  }
}
```

```
{
  "type": "object",
  "properties": {
    "templatesPublic": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer"
          },
          "name": {
            "type": "string"
          },
          "description": {
            "type": "string"
          },
          "url": {
            "type": "string"
          },
          "usedApps": {
            "type": "array",
            "items": {
              "type": "string"
            }
          },
          "usage": {
            "type": "integer"
          }
        }
      }
    },
    "pg": {
      "type": "object",
      "properties": {
        "last": {
          "type": "string"
        },
        "showLast": {
          "type": "boolean"
        },
        "sortBy": {
          "type": "string"
        },
        "sortDir": {
          "type": "string"
        },
        "limit": {
          "type": "integer"
        },
        "offset": {
          "type": "integer"
        }
      }
    }
  }
}
```

___

#### Get public (approved) template details

##### GET/templates/public/{templateUrl}templates:read

Retrieves details of a public (approved) template with a given `publicUrl`.

Path parameters

`templateUrl`

`string` REQUIRED

The unique URL of the public (approved) template consisting of the template ID and name. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint.

Example: 16-multiple-apps-template-example

Query parameters

`templatePublicId`

`integer`

The unique ID of the public version of the approved template. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint as one of the following IDs: `publishedId` for all published templates that are waiting for approval or not, or `approvedId` for approved templates.

Example: 18

`cols[]`

`array[Enum<values>]`

Specifies the group of values to return. For example, you may want to retrieve only information about the apps used in the template.

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/templates/public/16-multiple-apps-template-example?templatePublicId=18' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "templatePublic": {
    "id": 18,
    "name": "Multiple apps template example",
    "description": null,
    "url": "16-multiple-apps-template-example",
    "usedApps": [
      "discord",
      "http",
      "tools",
      "util",
      "gmail"
    ],
    "usage": 52
  }
}
```

```
{
  "type": "object",
  "properties": {
    "templatePublic": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer"
        },
        "name": {
          "type": "string"
        },
        "description": {
          "type": "string"
        },
        "url": {
          "type": "string"
        },
        "usedApps": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "usage": {
          "type": "integer"
        }
      }
    }
  }
}
```

___

#### Get public (approved) template details

##### GET/templates/public/{templateUrl}templates:read

Retrieves details of a public (approved) template with a given `publicUrl`.

Path parameters

`templateUrl`

`string` REQUIRED

The unique URL of the public (approved) template consisting of the template ID and name. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint.

Example: 16-multiple-apps-template-example

Query parameters

`templatePublicId`

`integer`

The unique ID of the public version of the approved template. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint as one of the following IDs: `publishedId` for all published templates that are waiting for approval or not, or `approvedId` for approved templates.

Example: 18

`cols[]`

`array[Enum<values>]`

Specifies the group of values to return. For example, you may want to retrieve only information about the apps used in the template.

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/templates/public/16-multiple-apps-template-example?templatePublicId=18' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "templatePublic": {
    "id": 18,
    "name": "Multiple apps template example",
    "description": null,
    "url": "16-multiple-apps-template-example",
    "usedApps": [
      "discord",
      "http",
      "tools",
      "util",
      "gmail"
    ],
    "usage": 52
  }
}
```

```
{
  "type": "object",
  "properties": {
    "templatePublic": {
      "type": "object",
      "properties": {
        "id": {
          "type": "integer"
        },
        "name": {
          "type": "string"
        },
        "description": {
          "type": "string"
        },
        "url": {
          "type": "string"
        },
        "usedApps": {
          "type": "array",
          "items": {
            "type": "string"
          }
        },
        "usage": {
          "type": "integer"
        }
      }
    }
  }
}
```

___

#### Get public (approved) template blueprint

##### GET/templates/public/{templateUrl}/blueprinttemplates:read

Retrieves a blueprint of a public (approved) template with a given `publicUrl`.

Path parameters

`templateUrl`

`string` REQUIRED

The unique URL of the public (approved) template consisting of the template ID and name. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint.

Example: 16-multiple-apps-template-example

Query parameters

`templatePublicId`

`integer`

The unique ID of the public version of the approved template. It can be retrieved from the [List templates](https://www.make.com/en/api-documentation/templates-get#templates-get) endpoint as one of the following IDs: `publishedId` for all published templates that are waiting for approval or not, or `approvedId` for approved templates.

Example: 18

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/templates/public/16-multiple-apps-template-example/blueprint?templatePublicId=18' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "blueprint": {
    "flow": [
      {
        "id": 1,
        "mapper": {
          "url": "https://google.com",
          "method": "get",
          "shareCookies": false
        },
        "module": "http:ActionGetFile",
        "version": 3,
        "metadata": {
          "expect": [
            {
              "name": "url",
              "type": "url",
              "label": "URL",
              "required": true
            },
            {
              "name": "method",
              "type": "hidden",
              "label": "Method"
            },
            {
              "name": "shareCookies",
              "type": "boolean",
              "label": "Share cookies with other HTTP modules",
              "required": true
            }
          ],
          "designer": {
            "x": 0,
            "y": 0
          },
          "parameters": [
            {
              "name": "handleErrors",
              "type": "boolean",
              "label": "Evaluate all states as errors (except for 2xx and 3xx )",
              "required": true
            }
          ]
        },
        "parameters": {
          "handleErrors": false
        }
      }
    ],
    "metadata": {
      "version": 1,
      "designer": {
        "orphans": []
      },
      "scenario": {
        "dlq": false,
        "dataloss": false,
        "maxErrors": 3,
        "autoCommit": true,
        "roundtrips": 1,
        "sequential": false,
        "confidential": false,
        "autoCommitTriggerLast": true
      }
    }
  },
  "controller": {
    "name": "New template",
    "modules": {},
    "idSequence": 2
  },
  "scheduling": {
    "type": "indefinitely",
    "interval": 900
  },
  "language": "en"
}
```

```
{
  "type": "object",
  "properties": {
    "blueprint": {
      "type": "object",
      "properties": {
        "flow": {
          "type": "array",
          "items": {
            "type": "object",
            "properties": {
              "id": {
                "type": "integer"
              },
              "mapper": {
                "type": "object",
                "properties": {
                  "ca": {
                    "type": "string"
                  },
                  "qs": {
                    "type": "array"
                  },
                  "url": {
                    "type": "string",
                    "format": "uri"
                  },
                  "gzip": {
                    "type": "boolean"
                  },
                  "method": {
                    "type": "string"
                  },
                  "headers": {
                    "type": "array"
                  },
                  "timeout": {
                    "type": "string"
                  },
                  "authPass": {
                    "type": "string"
                  },
                  "authUser": {
                    "type": "string"
                  },
                  "bodyType": {
                    "type": "string"
                  },
                  "shareCookies": {
                    "type": "boolean"
                  },
                  "parseResponse": {
                    "type": "boolean"
                  },
                  "followRedirect": {
                    "type": "boolean"
                  },
                  "useQuerystring": {
                    "type": "boolean"
                  },
                  "rejectUnauthorized": {
                    "type": "boolean"
                  }
                }
              },
              "module": {
                "type": "string",
                "format": "uri"
              },
              "onerror": {
                "type": "array",
                "items": {
                  "type": "object",
                  "properties": {
                    "id": {
                      "type": "integer"
                    },
                    "mapper": {
                      "type": "object",
                      "properties": {
                        "count": {
                          "type": "string",
                          "format": "utc-millisec"
                        },
                        "retry": {
                          "type": "boolean"
                        },
                        "interval": {
                          "type": "string",
                          "format": "utc-millisec"
                        }
                      }
                    },
                    "module": {
                      "type": "string",
                      "format": "uri"
                    },
                    "version": {
                      "type": "integer"
                    },
                    "metadata": {
                      "type": "object",
                      "properties": {
                        "expect": {
                          "type": "array",
                          "items": {
                            "type": "object",
                            "properties": {
                              "name": {
                                "type": "string"
                              },
                              "type": {
                                "type": "string"
                              },
                              "label": {
                                "type": "string"
                              },
                              "required": {
                                "type": "boolean"
                              }
                            }
                          }
                        },
                        "restore": {
                          "type": "object",
                          "properties": {
                            "retry": {
                              "type": "object",
                              "properties": {
                                "mode": {
                                  "type": "string"
                                }
                              }
                            }
                          }
                        },
                        "designer": {
                          "type": "object",
                          "properties": {
                            "x": {
                              "type": "integer"
                            },
                            "y": {
                              "type": "integer"
                            }
                          }
                        }
                      }
                    },
                    "parameters": {
                      "type": "object"
                    }
                  }
                }
              },
              "version": {
                "type": "integer"
              },
              "metadata": {
                "type": "object",
                "properties": {
                  "expect": {
                    "type": "array",
                    "items": {
                      "type": "object"
                    }
                  },
                  "restore": {
                    "type": "object",
                    "properties": {
                      "qs": {
                        "type": "object",
                        "properties": {
                          "mode": {
                            "type": "string"
                          },
                          "items": {
                            "type": "array"
                          }
                        }
                      },
                      "method": {
                        "type": "object",
                        "properties": {
                          "mode": {
                            "type": "string"
                          },
                          "label": {
                            "type": "string"
                          }
                        }
                      },
                      "headers": {
                        "type": "object",
                        "properties": {
                          "mode": {
                            "type": "string"
                          },
                          "items": {
                            "type": "array"
                          }
                        }
                      },
                      "bodyType": {
                        "type": "object",
                        "properties": {
                          "label": {
                            "type": "string"
                          }
                        }
                      }
                    }
                  },
                  "designer": {
                    "type": "object",
                    "properties": {
                      "x": {
                        "type": "integer"
                      },
                      "y": {
                        "type": "integer"
                      }
                    }
                  },
                  "parameters": {
                    "type": "array",
                    "items": {
                      "type": "object",
                      "properties": {
                        "name": {
                          "type": "string"
                        },
                        "type": {
                          "type": "string"
                        },
                        "label": {
                          "type": "string"
                        },
                        "required": {
                          "type": "boolean"
                        }
                      }
                    }
                  }
                }
              },
              "parameters": {
                "type": "object",
                "properties": {
                  "handleErrors": {
                    "type": "boolean"
                  }
                }
              }
            }
          }
        },
        "name": {
          "type": "string"
        },
        "metadata": {
          "type": "object",
          "properties": {
            "version": {
              "type": "integer"
            },
            "scenario": {
              "type": "object",
              "properties": {
                "maxErrors": {
                  "type": "integer"
                },
                "autoCommit": {
                  "type": "boolean"
                },
                "roundtrips": {
                  "type": "integer"
                }
              }
            }
          }
        }
      }
    },
    "controller": {
      "type": "object",
      "properties": {
        "name": {
          "type": "string"
        },
        "modules": {
          "type": "object"
        },
        "idSequence": {
          "type": "integer"
        }
      }
    },
    "scheduling": {
      "type": "object",
      "properties": {
        "type": {
          "type": "string"
        },
        "interval": {
          "type": "integer"
        }
      }
    },
    "language": {
      "type": "string"
    }
  }
}
```

___

### Users

The following main user endpoints allow you to get a list of existing users and manage their basic details such as password change.

#### List users

##### GET/usersuser:read

Retrieves a collection of all users for a team or an organization with a given ID. Returned users are sorted by name in ascending order.

Query parameters

`organizationId`

`integer`

The unique ID of the organization whose users will be retrieved. If this parameter is set, the `teamId` parameter must be skipped. For each request either `teamId` or `organizationId` must be defined.

`teamId`

`integer`

The unique ID of the team whose users will be retrieved. If this parameter is set, the `organizationId` parameter must be skipped. For each request either `teamId` or `organizationId` must be defined.

Example: 1

`cols[]`

`array[Enum<values>]`

An array of columns that should be returned from the API. Can be used to save bandwidth when not all properties are needed.

Default: \[ "id", "name", "email", "language", "timezoneId", "localeId", "countryId", "features", "avatar" \]

`pg[sortBy]`

Enum<values>

The value that will be used to sort returned entities by. Users can be currently sorted only by name.

Default: name

`pg[sortDir]`

Enum<values>

The sorting order. It accepts the ascending and descending direction specifiers.

Default: asc

`pg[offset]`

`integer`

The value of entities you want to skip before getting entities you need.

Default: 0

`pg[limit]`

`integer`

The value of maximum entities to return.

Default: 10

Maximum: 10000

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/users?teamId=1' \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566'
```

Response

-   Value
-   Schema

```
{
  "users": [
    {
      "id": 1,
      "name": "Administrator",
      "email": "admin@make.cloud",
      "language": "en",
      "timezoneId": 113,
      "localeId": 18,
      "countryId": 202,
      "features": {},
      "avatar": "https://secure.gravatar.com/avatar/6b1a74d20d925c12a73af32bf0dd7164.jpg?d=mm"
    }
  ],
  "pg": {
    "sortBy": "name",
    "sortDir": "desc",
    "offset": 0,
    "limit": 10
  },
  "membershipPromises": [
    {
      "id": 1,
      "legacyUserId": 238,
      "organizationRoleId": 11,
      "teamRoleId": 1,
      "organizationId": 666,
      "createdAt": "2022-01-01T12:00:00.000Z",
      "legacyEmail": "user@example.com",
      "legacyName": "User Example",
      "avatar": "https://secure.gravatar.com/avatar/6b1a74d20d925c12a73af32bf0dd7164.jpg?d=mm"
    }
  ]
}
```

```
{
  "type": "object",
  "properties": {
    "users": {
      "type": "array",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "integer"
          },
          "name": {
            "type": "string"
          },
          "email": {
            "type": "string",
            "format": "email"
          },
          "language": {
            "type": "string"
          },
          "timezoneId": {
            "type": "integer"
          },
          "localeId": {
            "type": "integer"
          },
          "countryId": {
            "type": "integer"
          },
          "features": {
            "type": "object",
            "properties": {
              "allow_apps": {
                "type": "boolean"
              }
            }
          },
          "avatar": {
            "type": "string",
            "format": "uri"
          },
          "timezone": {
            "type": "string"
          },
          "locale": {
            "type": "string"
          },
          "emailNotifications": {
            "type": "null"
          },
          "usersAdminsRoleId": {
            "type": "integer"
          },
          "hasPassword": {
            "type": "boolean"
          },
          "tfaEnabled": {
            "type": "boolean"
          },
          "forceSetPassword": {
            "type": "boolean"
          },
          "userOrganizationRoles": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "usersRoleId": {
                  "type": "integer"
                },
                "userId": {
                  "type": "integer"
                },
                "organizationId": {
                  "type": "integer"
                },
                "invitation": {
                  "type": "null"
                }
              }
            }
          },
          "userTeamRoles": {
            "type": "array",
            "items": {
              "type": "object",
              "properties": {
                "usersRoleId": {
                  "type": "integer"
                },
                "userId": {
                  "type": "integer"
                },
                "teamId": {
                  "type": "integer"
                },
                "changeable": {
                  "type": "boolean"
                }
              }
            }
          }
        }
      }
    },
    "pg": {
      "type": "object",
      "properties": {
        "last": {
          "type": "string",
          "description": "Shown only when using the `last` based pagination."
        },
        "showLast": {
          "type": "boolean",
          "description": "Shown only when using the `last` based pagination."
        },
        "sortBy": {
          "type": "string"
        },
        "sortDir": {
          "type": "string"
        },
        "limit": {
          "type": "integer"
        },
        "offset": {
          "type": "integer",
          "description": "Shown only when using the `offset` based pagination."
        }
      }
    },
    "membershipPromises": {
      "type": "array",
      "description": "Works only on Cloud Instances",
      "items": {
        "type": "object",
        "properties": {
          "id": {
            "type": "number"
          },
          "legacyUserId": {
            "type": "number"
          },
          "organizationRoleId": {
            "type": "number"
          },
          "teamRoleId": {
            "type": "number"
          },
          "organizationId": {
            "type": "number"
          },
          "createdAt": {
            "type": "string",
            "format": "date-time"
          },
          "legacyEmail": {
            "type": "string"
          },
          "legacyName": {
            "type": "string"
          },
          "avatar": {
            "type": "string"
          }
        }
      }
    }
  }
}
```

___

#### Update user password

##### PUT/users/{userId}/attributes/passworduser:write

Updates a password for a user with a given ID by passing new data in the request body. It replaces the entire resource with the new values. In the response, it returns the confirmation if the password was changed. This endpoint corresponds to changing a password in the user profile when the user is logged in to the Make interface.

Path parameters

`userId`

`string` REQUIRED

The unique ID of the user. It can be retrieved from the [List users](https://www.make.com/en/api-documentation/users-get#users-get) endpoint.

Example: 1

Request body

`currentPassword`

`string` REQUIRED

The current user password.

Example: 123456Ab.

`newPassword1`

`string` REQUIRED

The new user password. The password must be at least 9 characters long and must contain at least one uppercase letter, at least one number, and at least one special character.

Example: 123456Ab-

`newPassword2`

`string` REQUIRED

The new user password for confirmation. This password must be the same as the password in the `newPassword1` property.

Example: 123456Ab-

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X PUT \
  https://eu1.make.com/api/v2/users/1/attributes/password \
  -H 'Authorization: Token abcdefab-1234-5678-abcd-112233445566' \
  -d '{"currentPassword":"123456Ab.","newPassword1":"123456Ab-","newPassword2":"123456Ab-"}'
```

Response

-   Value
-   Schema

```
{
  "changed": true
}
```

```
{
  "type": "object",
  "properties": {
    "changed": {
      "type": "boolean"
    }
  }
}
```

___

#### Send password reset demand

##### POST/users/password-reset-demand

Sends password reset demand for a user with an email passed in the request body. This endpoint corresponds to the **Lost password** function on the login page in the Make interface. In the response, it returns the confirmation if the demand was sent successfully.

Request body

`email`

`string` REQUIRED

The email of the user for who the password should be reset.

Example: ee@eee.com

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X POST \
  https://eu1.make.com/api/v2/users/password-reset-demand \
  -d '{"email":"ee@eee.com"}'
```

Response

-   Value
-   Schema

```
{
  "ok": 1
}
```

```
{
  "type": "object",
  "properties": {
    "ok": {
      "type": "integer"
    }
  }
}
```

___

#### Set session for resetting lost password

##### GET/users/password-reset

Checks a hash and sets a session for the [Reset lost password](https://www.make.com/en/api-documentation/users-password-reset-post#users-password-reset-post) endpoint. This endpoint corresponds to clicking the **Reset password** link in the **Password reset** email.

Query parameters

`hash`

`string`

The unique hash of the password reset session.

Example: fab680b60044adb766128e713e44e15b

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X GET \
  'https://eu1.make.com/api/v2/users/password-reset?hash=fab680b60044adb766128e713e44e15b'
```

Response

-   Value
-   Schema

```
{
  "ok": 1
}
```

```
{
  "type": "object",
  "properties": {
    "ok": {
      "type": "integer"
    }
  }
}
```

___

#### Reset lost password

##### POST/users/password-reset

Updates a password for a user based on the session created when calling the [Prepare session for password reset](https://www.make.com/en/api-documentation/users-password-reset-get#users-password-reset-get) endpoint. This endpoint corresponds to setting a new password on the **Lost password** page in the Make interface.

Request body

`newPassword1`

`string` REQUIRED

The new user password.

Example: Aa123456.

`newPassword2`

`string` REQUIRED

This password must be the same as the password in the `newPassword1` property.

Example: Aa123456.

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X POST \
  https://eu1.make.com/api/v2/users/password-reset \
  -d '{"newPassword1":"Aa123456.","newPassword2":"Aa123456."}'
```

Response

-   Value
-   Schema

```
{
  "ok": 1
}
```

```
{
  "type": "object",
  "properties": {
    "ok": {
      "type": "integer"
    }
  }
}
```

___

#### Reset lost password

##### POST/users/password-reset

Updates a password for a user based on the session created when calling the [Prepare session for password reset](https://www.make.com/en/api-documentation/users-password-reset-get#users-password-reset-get) endpoint. This endpoint corresponds to setting a new password on the **Lost password** page in the Make interface.

Request body

`newPassword1`

`string` REQUIRED

The new user password.

Example: Aa123456.

`newPassword2`

`string` REQUIRED

This password must be the same as the password in the `newPassword1` property.

Example: Aa123456.

###### Example

Request

cURL

-   cURL
-   HTTP
-   Node.js (https)
-   Java (nethttp)
-   PHP (http1)
-   Python (http.client)
-   C# (httpclient)
-   Go
-   Ruby

```
curl -X POST \
  https://eu1.make.com/api/v2/users/password-reset \
  -d '{"newPassword1":"Aa123456.","newPassword2":"Aa123456."}'
```

Response

-   Value
-   Schema

```
{
  "ok": 1
}
```

```
{
  "type": "object",
  "properties": {
    "ok": {
      "type": "integer"
    }
  }
}
```

___

[](https://www.make.com)

Make API documentation

-   Introduction
-   [Fundamentals](https://www.make.com/en/api-documentation/users-password-reset-post#fundamentals)
-   [Getting started](https://www.make.com/en/api-documentation/users-password-reset-post#getting-started)
-   [Authentication](https://www.make.com/en/api-documentation/users-password-reset-post#authentication)
    -   [Make roles and API scopes](https://www.make.com/en/api-documentation/users-password-reset-post#authentication-scopes)
    -   [Generating authentication token](https://www.make.com/en/api-documentation/users-password-reset-post#authentication-token)
    -   [Managing authentication token](https://www.make.com/en/api-documentation/users-password-reset-post#authentication-managing)
-   [Pagination, sorting and filtering](https://www.make.com/en/api-documentation/users-password-reset-post#pagination-sorting-filtering)
-   [Troubleshooting and error handling](https://www.make.com/en/api-documentation/users-password-reset-post#troubleshooting)
    -   [HTTP status codes of errors](https://www.make.com/en/api-documentation/users-password-reset-post#http-status-codes)
    -   [Troubleshooting](https://www.make.com/en/api-documentation/users-password-reset-post#common-issues)
-   [Resources](https://www.make.com/en/api-documentation/users-password-reset-post#api-resources)

-   Resources
-   [Connections](https://www.make.com/en/api-documentation/users-password-reset-post#connections)
    -   [List connections](https://www.make.com/en/api-documentation/users-password-reset-post#connections-get)
    -   [Create connection](https://www.make.com/en/api-documentation/users-password-reset-post#connections-post)
    -   [Get connection details](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-get)
    -   [Update connection](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-patch)
    -   [Delete connection](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-delete)
    -   [Verify connection](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-test-post)
    -   [Verify if connection is scoped](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-scoped-post)
    -   [Set connection data](https://www.make.com/en/api-documentation/users-password-reset-post#connections-connectionId-set-data-post)
-   [Data stores](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores)
    -   [List data stores](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-get)
    -   [Create data store](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-post)
    -   [Delete data stores](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-delete)
    -   [Get data store details](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-get)
    -   [Update data store](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-patch)
    -   [Data](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-data)
        -   [List data store records](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-data-get)
        -   [Create data store record](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-data-post)
        -   [Delete data store records](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-data-delete)
        -   [Update entire data store record](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-data-dataStoreKeyRecord-put)
        -   [Update data store record details](https://www.make.com/en/api-documentation/users-password-reset-post#data-stores-dataStoreId-data-dataStoreKeyRecord-patch)
-   [Data structures](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures)
    -   [List data structures](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures-get)
    -   [Create data structure](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures-post)
    -   [Update data structure](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures-dataStructureId-patch)
    -   [Delete data structure](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures-dataStructureId-delete)
    -   [Clone data structure](https://www.make.com/en/api-documentation/users-password-reset-post#data-structures-dataStructureId-clone-post)
-   [Hooks](https://www.make.com/en/api-documentation/users-password-reset-post#hooks)
    -   [List hooks](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-get)
    -   [Create hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-post)
    -   [Get hook details](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-get)
    -   [Delete hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-delete)
    -   [Update hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-patch)
    -   [Ping hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-ping-get)
    -   [Learn start](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-learn-start-post)
    -   [Learn stop](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-learn-stop-post)
    -   [Enable hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-enable-post)
    -   [Disable hook](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-disable-post)
    -   [Set hook details](https://www.make.com/en/api-documentation/users-password-reset-post#hooks-hookId-set-data-post)
-   [Notifications](https://www.make.com/en/api-documentation/users-password-reset-post#notifications)
    -   [List notifications](https://www.make.com/en/api-documentation/users-password-reset-post#notifications-get)
    -   [Delete notifications](https://www.make.com/en/api-documentation/users-password-reset-post#notifications-delete)
    -   [Get notification detail](https://www.make.com/en/api-documentation/users-password-reset-post#notifications-notificationId-get)
    -   [Mark all notifications as read](https://www.make.com/en/api-documentation/users-password-reset-post#notifications-mark-as-read-post)
-   [Scenarios](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios)
    -   [List scenarios](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-get)
    -   [Create scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-post)
    -   [Get scenario details](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-get)
    -   [Update scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-patch)
    -   [Delete scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-delete)
    -   [Get scenario blueprint](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-blueprint-get)
    -   [Get trigger details](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-triggers-get)
    -   [Clone scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-clone-post)
    -   [Set module data](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-data-put)
    -   [Check module data](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-data-moduleId-get)
    -   [Start scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-start-post)
    -   [Stop scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-stop-post)
    -   [Publish scenario](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-publish-post)
    -   [Logs](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-logs)
        -   [List scenario logs](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-logs-get)
        -   [Get execution log](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-logs-executionId-get)
    -   [Blueprints](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-blueprints)
        -   [Get blueprint versions](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-scenarioId-blueprints-get)
-   [Scenarios folders](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-folders)
    -   [List scenario folders](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-folders-get)
    -   [Create scenario folder](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-folders-post)
    -   [Update scenario folder](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-folders-folderId-patch)
    -   [Delete scenario folder](https://www.make.com/en/api-documentation/users-password-reset-post#scenarios-folders-folderId-delete)
-   [Templates](https://www.make.com/en/api-documentation/users-password-reset-post#templates)
    -   [List templates](https://www.make.com/en/api-documentation/users-password-reset-post#templates-get)
    -   [Create template](https://www.make.com/en/api-documentation/users-password-reset-post#templates-post)
    -   [Get template details](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-get)
    -   [Update template](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-patch)
    -   [Delete template](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-delete)
    -   [Get template blueprint](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-blueprint-get)
    -   [Publish template](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-publish-post)
    -   [Request approval](https://www.make.com/en/api-documentation/users-password-reset-post#templates-templateId-request-approval-post)
    -   [Public](https://www.make.com/en/api-documentation/users-password-reset-post#templates-public)
        -   [List public (approved) templates](https://www.make.com/en/api-documentation/users-password-reset-post#templates-public-get)
        -   [Get public (approved) template details](https://www.make.com/en/api-documentation/users-password-reset-post#templates-public-templateUrl-get)
        -   [Get public (approved) template blueprint](https://www.make.com/en/api-documentation/users-password-reset-post#templates-public-templateUrl-blueprint-get)
-   [Users](https://www.make.com/en/api-documentation/users-password-reset-post#users)
    -   [List users](https://www.make.com/en/api-documentation/users-password-reset-post#users-get)
    -   [Update user](https://www.make.com/en/api-documentation/users-password-reset-post#users-userId-patch)
    -   [Update user email](https://www.make.com/en/api-documentation/users-password-reset-post#users-userId-attributes-email-put)
    -   [Update user password](https://www.make.com/en/api-documentation/users-password-reset-post#users-userId-attributes-password-put)
    -   [Send password reset demand](https://www.make.com/en/api-documentation/users-password-reset-post#users-password-reset-demand-post)
    -   [Set session for resetting lost password](https://www.make.com/en/api-documentation/users-password-reset-post#users-password-reset-get)
    -   [Reset lost password](https://www.make.com/en/api-documentation/users-password-reset-post#users-password-reset-post)