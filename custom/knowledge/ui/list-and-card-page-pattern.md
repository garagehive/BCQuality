---
bc-version: [all]
domain: ui
keywords: [list-page, card-page, cardpageid, editable, navigation, drill-down, naming, suffix]
technologies: [al]
countries: [w1]
application-area: [all]
---

# List pages must set CardPageId and Editable = false; names end in List or Card

## Description

When a table has both a list page and a card page, the list page must set `CardPageId` to the card page and `Editable = false`. These two properties together enforce the BC edit-on-card paradigm: a row click opens the card for editing rather than allowing inline changes. Without `CardPageId` the row drill-down is not wired up. Without `Editable = false` users can modify records directly in the list, bypassing the card page's validation logic. Name list pages with the "List" suffix and card pages with the "Card" suffix for consistent navigation.

## Best Practice

List page: name ends in "List", set `CardPageId = "GHV <Name> Card";` and `Editable = false;` in properties. Card page: name ends in "Card", `UsageCategory = None;`.

## Anti Pattern

A list page that omits `CardPageId` silently loses row drill-down — double-clicking a row does nothing. Omitting `Editable = false` permits inline edits that skip card-level field validation and triggers. Using inconsistent naming suffixes makes the list/card relationship unclear to future readers.
