# Lab 3: Research JSON:API
## 1. What is JSON:API and why was it created?
JSON:API is a specification for creating more consistent and efficient APIs with JSON. It specifies how clients should request messages and how the server should respond. It was created in order to streamline the process of formatting JSON responses within a development team and to optimize the responses.
## 2. Are there any alternatives to JSON:API? If so, please specify.
OData, developed by Microsoft since 2007, is similar to JSON:API in that it is also a specification for how RESTful APIs should communicate. Facebook's GraphQL is also a specification, it is not REST, but rather an alternative to REST.
## 3. What are the pros and cons of JSON:API?
JSON:API responses can pass links like _self_, _next_, and _last_ which can make pagination easily, and also allows for sparse field sets, which allows for a response to only contain requested information. Both of these things work to optimize API responses. JSON:API seems very highly praised online, and the only real complaints I could find were that GraphQL has better interactivity and auto-generated documentation capabilities.
## 4. Make up an endpoint and its data and model it as JSON:API.
#### Your example should be different from the one on the JSON:API site. Your example should have at least 2 attributes and 1 relationship. Write your example JSON in a code block.
```json
{
  "data": [{
    "type": "videos",
    "id": "1",
    "attributes": {
      "title": "Man watches paint dry for 10 hours",
      "likes": 789124,
      "dislikes": 1285,
      "length": 36000
    },
    "relationships": {
      "channel": {
        "links": {
          "self": "http://example.com/videos/1/relationships/channel",
          "related": "http://example.com/videos/1/channel"
        },
        "data": { "type": "channels", "id": "4" }
      },
    },
    "links": {
      "self": "http://example.com/videos/1"
    }
  }],
  "included": [{
    "type": "channel",
    "id": "9",
    "attributes": {
     "title": "10 hour bad videos",
     "subscribers": 10149523
    },
    "links": {
      "self": "http://example.com/channels/4"
    }
  }]
}
```
