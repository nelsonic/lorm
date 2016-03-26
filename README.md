# Lightweight Object Relational Mapper

A simple JOI model of the form:
```js
var Joi = require('joi');
var person = {
  email    : Joi.string().email().required().max(254), // Required
  password : Joi.string().required().min(6).max(100),  // minimum length 6 characters]
  name     : Joi.string().optional().max(100),
  id       : Joi.any().forbidden()
};
console.log(JSON.stringify(person, null, 2));
```

Has the following Object structure:

```js
{
  "email": {
    "isJoi": true,
    "_type": "string",
    "_settings": null,
    "_valids": {
      "_set": []
    },
    "_invalids": {
      "_set": [
        ""
      ]
    },
    "_tests": [
      {
        "name": "email"
      },
      {
        "name": "max",
        "arg": 254
      }
    ],
    "_refs": [],
    "_flags": {
      "presence": "required"
    },
    "_description": null,
    "_unit": null,
    "_notes": [],
    "_tags": [],
    "_examples": [],
    "_meta": [],
    "_inner": {}
  },
  "password": {
    "isJoi": true,
    "_type": "string",
    "_settings": null,
    "_valids": {
      "_set": []
    },
    "_invalids": {
      "_set": [
        ""
      ]
    },
    "_tests": [
      {
        "name": "min",
        "arg": 6
      },
      {
        "name": "max",
        "arg": 100
      }
    ],
    "_refs": [],
    "_flags": {
      "presence": "required"
    },
    "_description": null,
    "_unit": null,
    "_notes": [],
    "_tags": [],
    "_examples": [],
    "_meta": [],
    "_inner": {}
  },
  "name": {
    "isJoi": true,
    "_type": "string",
    "_settings": null,
    "_valids": {
      "_set": []
    },
    "_invalids": {
      "_set": [
        ""
      ]
    },
    "_tests": [
      {
        "name": "max",
        "arg": 100
      }
    ],
    "_refs": [],
    "_flags": {
      "presence": "optional"
    },
    "_description": null,
    "_unit": null,
    "_notes": [],
    "_tags": [],
    "_examples": [],
    "_meta": [],
    "_inner": {}
  },
  "id": {
    "isJoi": true,
    "_type": "any",
    "_settings": null,
    "_valids": {
      "_set": []
    },
    "_invalids": {
      "_set": []
    },
    "_tests": [],
    "_refs": [],
    "_flags": {
      "presence": "forbidden"
    },
    "_description": null,
    "_unit": null,
    "_notes": [],
    "_tags": [],
    "_examples": [],
    "_meta": [],
    "_inner": {}
  }
}
```

```js
"_flags": {
  "presence": "forbidden"
}
```
