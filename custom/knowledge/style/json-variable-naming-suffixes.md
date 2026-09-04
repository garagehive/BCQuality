---
bc-version: [all]
domain: style
keywords: [json, variable, naming, jobj, jarr, jtok, jval, jsonobject, jsonarray, jsontoken, jsonvalue]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Use type-indicating suffixes for JSON variables

## Description

AL variables that hold JSON structures must carry a suffix identifying the AL JSON type: `JObj` for `JsonObject`, `JArr` for `JsonArray`, `JTok` for `JsonToken`, and `JVal` for `JsonValue`. The suffix is appended to a descriptive name, e.g. `ResponseJObj`, `TasksJArr`, `DataJTok`, `NameJVal`. This makes the type of every JSON variable visible at the call site without consulting the `var` block, reducing the risk of calling a method on the wrong JSON type.

## Best Practice

Name every JSON variable as `<Purpose><TypeSuffix>`: `ResponseJObj`, `BoardsJArr`, `DataJTok`, `IdJVal`. Apply the convention consistently across all procedures and codeunits that deal with HTTP responses or JSON payloads.

## Anti Pattern

Using generic names like `Json`, `JsonData`, `Response`, or `Token` without a type suffix. A reader cannot tell whether `Response` is a `JsonObject` or `JsonToken` without scrolling to the declaration — and mistakenly calling `.AsObject()` on a token that holds an array is a silent runtime error.
