---
bc-version: [all]
domain: ui
keywords: [caption, field, redundant, table, property, display-name, default]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Omit Caption on table fields when it matches the field name

## Description

Business Central automatically uses the field name as the display caption when no `Caption` property is set. A `Caption` that exactly mirrors the field name adds no value — it duplicates text that the platform would produce anyway. Only set `Caption` when the intended display text must differ from the field name, for example when the AL identifier must be abbreviated or when a more user-friendly label is required.

## Best Practice

Omit the `Caption` property when the natural reading of the field name is the desired label. Add `Caption` only when the display label must differ — for example, field identifier `CustPostingGrp` with `Caption = 'Customer Posting Group';`.

## Anti Pattern

Writing `field(10; Status; Option) { Caption = 'Status'; }` where the `Caption` value is identical to the field name. The property is redundant and should be removed.
