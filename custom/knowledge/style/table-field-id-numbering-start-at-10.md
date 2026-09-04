---
bc-version: [all]
domain: style
keywords: [field-id, field-number, table, numbering, primary-key, breaking-change]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Table field IDs start at 10 and increment by 10

## Description

Custom table field IDs must start at 10 and increment by 10 (10, 20, 30, 40, …). The gap between IDs allows new fields to be inserted between existing ones in the future without renumbering, which would be a breaking change for any dependent extension or data migration. Field ID 1 is reserved exclusively for single-field integer primary keys; do not use it for ordinary fields.

## Best Practice

Number new table fields 10, 20, 30, … When inserting a field between two existing IDs, use the midpoint (e.g., 15 between 10 and 20). Reserve ID 1 only for the primary key of tables that follow the single-integer-key pattern.

## Anti Pattern

Starting at 1 and incrementing by 1 (1, 2, 3, …) exhausts the gaps between IDs immediately, making future field insertions a breaking renumbering operation. Starting at 1 for a non-primary-key field also conflicts with the reserved-ID convention.
