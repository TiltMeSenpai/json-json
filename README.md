# Specification for the implementation of JSON-JSON

For version `0.1`.


## Introduction

JSON-JSON is a format for storing JSON documents, with required keys which
clearly and concisely define the document. Optional, custom keys are stylized
separately (`PascalCase` instead of `snake_case`) so that the intent of the
document remains clear.


## File Extension

JSON-JSON officially uses `.jsonjson` as its filetype.


## Requirements

- All keys are to be either in `snake_case`, except non-required keys which are
  in `PascalCase`.
- Indentation must increment by one per nested key or value
- Besides the required keys, all other keys are allowed


## Struct

The struct is as follows:

- **author**: An array of author names (_array of strings_) (required)
- **description**: The description of the document (_string_) (required)
- **name**: The name of the JSON document (_string_) (required)
- **created_at**: A timestamp of when the document was created, with an epoch
  of `1992-11-12T21:41:23+00:00` (_integer_) (required)
- **updated_at**: A timestamp of when the document was last updated, with the
  same epoch of the above `created_at` key. If not updated, this can be null,
  but must always be present (_integer_)
- **document**: The JSON document (_object_) (required)


## Sample Document

```jsonjson
{ "author": 
  [ "My Name"
  , "Someone Else's Name"
  ]
, "description": "An in-depth sample document for the JSON-JSON spec"
, "name": "Sample Document"
, "created_at": 1751251
, "updated_at": null
, "document": {
  { "a_key":
    { "another_key": "a value" 
    }
  , "flexibility": "this defines JSON-JSON"
  }
, "aCustomKey": "and a value"
, "andAnother": "these must be PascalCase"
}
```
