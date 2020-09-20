# JSONQL
This project is meant to be a simple database management system—based on JSON format—from scratch.
It will start by parsing a json to know if it's valid or not, till it will be a valid DBMS that can load and save the database to the disk, with the ability to manage it during runtime.

## Stage 1

In this stage, the project should only be able to parse a text, and knows it's valid or not. Using the [JSON specifications](https://www.json.org/json-en.html)

<details>
  <summary>Valid test Data</summary>

Valid:
```
{
  "id": 1,
  "admin":true,
  "name" : "Leanne Graham"
}
```

Valid:
```
{
  "id"    :   1    ,
  "admin":false,
  "name" :   "Leanne Graham"
}
```

Valid:
```
{
  "id": 1,
  "address": {
    "street": "Kulas Light"
  },
  "company": {
    "name": "Romaguera-Crona"
  }
}
```

Valid:
```
{
  "id": 1,
  "admin": true,
  "email": "Sincere@april.biz",
  "address": {
    "zipcode": "92998-3874",
    "geo": {
      "lat": "-37.3159",
      "lng": "81.1496"
    }
  },
  "phone": null,
  "company": {
    "name": "Romaguera-Crona",
    "catchPhrase": "Multi-layered client-server neural-net",
    "bs": "harness real-time e-markets"
  }
}
```

Valid (Array):
```
[
  "a",
  "b",
  1,
  true,
  false,
  null,
  {"id": 1}
]
```

Valid (Array):
```
[
  {
    "id": 1,
    "admin": true,
    "email": "Sincere@april.biz",
    "address": {
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": null,
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  }
]
```

</details>

<details>
  <summary>Inalid test Data</summary>

Invalid (Extra bracket):
```
{
  "id": 1,
  "admin": true,
  "name": "Leanne Graham"
}}
```

Invalid (Trailing comma):
```
{
  "id": 1,
  "admin": true,
  "name": "Leanne Graham",
}
```

Invalid (Missing comma):
```
{
  "id": 1,
  "admin": true
  "name": "Leanne Graham"
}
```

Invalid (Single quotes):
```
{
  "id": 1,
  'admin': false,
  "name": "Leanne Graham"
}
```

Invalid (Semi-colon):
```
{
  "id"; 1
}
```


Invalid (Trailing comma):
```
{
  "id": 1,
  "address": {
    "street"
  },
  "company": {
    "name": "Romaguera-Crona",
  }
}
```

Invalid (Undefined value):
```
{
  "id": 1,
  "admin": true,
  "email": "Sincere@april.biz",
  "address": {
    "zipcode": "92998-3874",
    "geo": {
      "lat": "-37.3159",
      "lng": "81.1496"
    }
  },
  "phone": undefined,
  "company": {
    "name": "Romaguera-Crona",
    "catchPhrase": "Multi-layered client-server neural-net",
    "bs": "harness real-time e-markets"
  }
}
```

Invalid (Array; Trailing comma):
```
[
  "a",
  "b",
  1,
  true,
  false,
  null,
  {"id": 1},
]
```

Invalid (Array; Single quotes):
```
[
  "a",
  "b",
  1,
  true,
  false,
  null,
  {'id': 1}
]
```


Invalid (Array; Trailing comma):
```
[
  {
    "id": 1,
    "admin": true,
    "email": "Sincere@april.biz",
    "address": {
      "zipcode": "92998-3874",
      "geo": {
        "lat": "-37.3159",
        "lng": "81.1496"
      }
    },
    "phone": null,
    "company": {
      "name": "Romaguera-Crona",
      "catchPhrase": "Multi-layered client-server neural-net",
      "bs": "harness real-time e-markets"
    }
  },
]
```

</details>
