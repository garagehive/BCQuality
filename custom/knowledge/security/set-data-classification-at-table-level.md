---
bc-version: [all]
domain: security
keywords: [dataclassification, table, field, privacy, customer-content, classification, inheritance]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Set DataClassification at the table level; override per field only when it differs

## Description

`DataClassification` must be set once in the table object definition (e.g., `DataClassification = CustomerContent;`). All fields in the table inherit the table-level classification automatically. Set `DataClassification` on an individual field only when that field requires a classification different from the table default — for example, a `SystemMetadata` timestamp in an otherwise `CustomerContent` table. Repeating the same classification on every field is redundant, increases file size, and creates a maintenance hazard when the table-level value changes.

## Best Practice

Set `DataClassification = CustomerContent;` (or the appropriate level) in the table `fields` block header. Only add a `DataClassification` property to a specific field when it must differ from the table default.

## Anti Pattern

Repeating `DataClassification = CustomerContent;` on every individual field when all fields share the same classification. If the table-level default changes later, all per-field copies must also be updated — a common source of stale or inconsistent classifications during refactoring.
