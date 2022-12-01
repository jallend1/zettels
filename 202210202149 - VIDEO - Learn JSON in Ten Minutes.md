# Learn JSON in Ten Minutes

Javascript Object Notation

  

## Basics

- Data representation format

- Lightweight, and easy to read/write

  

## Supported Data Types

- Strings

- Numbers

- Booleans

- Null

- Arrays

- Objects (Most Common)

  

## Examples

  

{

    "key": "value",

    "name": "Jason",

    "sampleNumber": 3,

    "isBoolean": true,

    "anArray": ["First item", "Second item"],

    "anEmbeddedArrayOfObjects": [{

        "key": "value",

        "name": "Jason",

        "sampleNumber": 3,

        "isBoolean": true,

        "anArray": ["First item", "Second item"],

    }]

}

  

Converts JSON file (otherwise received as a string) into a meaningful object:

JSON.parse(filename)

  

# JSON Tutorial for Beginners

## Basics

- Key/Name value pairs {"key": "value"}

- Objects are comma separated {"name1": "value", "name2": "value"}

- Arrays with square brackets separated by commas {"key": [{"name": value}], [{"name": value}]}

  

## Differences b/n JSON and JavaScript

- All keys must be quoted

- JSON uses double quotes

- No functions in JSON

  

fetch(url).then((res) => res.json()) -- Automatiaclly returns it within a json format