[mustache.js](http://github.com/janl/mustache.js) is an implementation of the [mustache](http://mustache.github.com/) template system in JavaScript.


# This fork

This Fork has the following features have been added.


## Array

View:
```js
{
  "beatles": [
    { "firstName": "John", "lastName": "Lennon" },
    { "firstName": "Paul", "lastName": "McCartney" },
    { "firstName": "George", "lastName": "Harrison" },
    { "firstName": "Ringo", "lastName": "Star" }
  ]
}
```

Template:
```
{{#beatles}}
* {{firstName}} {{lastName}} ({{@i}}) ({{@first}})
{{/beatles}}
```

Output:
```
* John Lennon (0) (true)
* Paul McCartney (1) (false)
* George Harrison (2) (false)
* Ringo Star (3) (false)
```

## Object.@each

View:
```js
{
    "beatles": {
        "John": {"firstName": "John", "lastName": "Lennon"},
        "Paul": {"firstName": "Paul", "lastName": "McCartney"},
        "George": {"firstName": "George", "lastName": "Harrison"},
        "Ringo": {"firstName": "Ringo", "lastName": "Star"}
    }
}
```

Template:
```
{{#beatles}}
    {{#@each}}
    * {{@key}} : {{@value.firstName}} {{@value.lastName}}
    {{/@each}}
{{/beatles}}
```

Output:
```
* John : John Lennon
* Paul : Paul McCartney
* George : George Harrison
* Ringo : Ringo Star
```