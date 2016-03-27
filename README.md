# Lightweight Object Relational Mapper

The basic idea is to have a *single* [Joi](https://github.com/hapijs/joi)
*model* which can be used to create input forms, validate http requests
*and* database queries.

A simple JOI model for a "Person" could take the form:
```js
var Joi = require('joi');
var person = {
  email    : Joi.string().email().required().max(254), // Required
  password : Joi.string().required().min(6).max(100),  // minimum length 6 chars
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
Each sub-object has the folowing
```js
"_flags": {
  "presence": "forbidden"
}
```

## Research & Background Reading


### Existing Node Modules

+ pg - https://github.com/brianc/node-postgres (the most popular node Postgres module)
+ node-sql - https://github.com/brianc/node-sql sql string builder for node
+ sequelize - https://github.com/sequelize/sequelize
+ js-data - https://github.com/js-data/js-data
+ knex - https://github.com/tgriesser/knex

### Data Types

+ Postgres data types: https://en.wikipedia.org/wiki/PostgreSQL#Data_types

## Motivation

+ Read the comments in this post: http://www.sitepoint.com/3-javascript-orms-you-might-not-know/
