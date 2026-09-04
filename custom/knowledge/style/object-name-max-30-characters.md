---
bc-version: [all]
domain: style
keywords: [object-name, length, 30-characters, platform-limit, compiler-error, abbreviation]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Object names must not exceed 30 characters

## Description

The Business Central platform enforces a hard 30-character limit on object names (tables, pages, codeunits, enums, reports, etc.). Names longer than 30 characters cause a compiler error. Because the mandatory "GHV" prefix consumes 3 characters, the descriptive part of any name is effectively limited to 27 characters.

## Best Practice

Keep names concise and count characters including the prefix before finalising. Use standard BC abbreviations when needed: "Mgt" for "Management", "Integ" for "Integration", "Jnl" for "Journal", "No." for "Number", "Def." for "Definition".

## Anti Pattern

Writing a fully descriptive name such as `GHV Application Build Management` (34 characters) produces a compiler error. The fix is to shorten the name — not to remove the prefix.
