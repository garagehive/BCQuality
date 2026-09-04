---
bc-version: [all]
domain: ui
keywords: [applicationarea, page, property, field, control, redundancy, inheritance]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Set ApplicationArea once in page properties; override per control only when needed

## Description

`ApplicationArea` set in the page `properties` block is inherited by all fields, actions, and parts on that page. Repeating the same `ApplicationArea` on individual controls is redundant and creates a maintenance hazard: if the page-level value is updated, all the per-control copies must be found and updated individually. Only set `ApplicationArea` on a specific control when that control genuinely requires a different application area than the page default.

## Best Practice

Set `ApplicationArea = All;` (or the appropriate area) in the page `properties` block. Leave individual fields and actions without an `ApplicationArea` property unless they require a different value.

## Anti Pattern

Copying `ApplicationArea = All;` onto every field and action inside the page. If the page-level value ever changes, every per-control copy becomes stale — a common source of inconsistency in large pages.
