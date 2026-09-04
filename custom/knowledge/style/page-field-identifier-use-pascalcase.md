---
bc-version: [all]
domain: style
keywords: [page, field, identifier, pascalcase, quoted-string, control-name, naming]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Page field control identifiers must use PascalCase, not quoted strings

## Description

Page field control identifiers must be written in unquoted PascalCase (e.g., `WorkItemNo`, `PlannedDeploymentDate`) rather than quoted strings containing spaces (e.g., `"Work Item No."`, `"Planned Deployment Date"`). While the AL compiler accepts quoted identifiers, they complicate refactoring, reduce readability, and diverge from Microsoft's own page authoring convention for extension fields.

## Best Practice

Derive the control identifier from the field name by removing spaces and capitalising each word: field `"Planned Deployment Date"` → control identifier `PlannedDeploymentDate`. The source expression still uses the quoted field name: `field(PlannedDeploymentDate; Rec."Planned Deployment Date")`.

## Anti Pattern

Writing `field("Work Item No."; Rec."Work Item No.")` where the control name is a quoted string. Prefer `field(WorkItemNo; Rec."Work Item No.")`.
