---
bc-version: [all]
domain: style
keywords: [object-name, prefix, ghv, appsource, naming-conflict, appsourcecop]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Use GHV prefix on all object names

## Description

All AL objects (tables, pages, codeunits, enums, reports, queries, etc.) must be prefixed with "GHV" as mandated by `AppSourceCop.json` (`mandatoryPrefix: "GHV"`). This avoids naming collisions with base application objects, other extensions, and future BC platform objects. AppSourceCop rule AS0011 enforces this at build time and will fail the build for any non-prefixed object.

## Best Practice

Prefix every object name with "GHV" — for example, `GHV App Build List`, `GHV Deployment Mgt`, `GHV Work Item`. The prefix applies to the object name, not the file name. When a prefix is already present, do not add it twice.

## Anti Pattern

Creating an object without the "GHV" prefix (e.g., `App Build List`, `Deployment Management`) causes an AppSourceCop AS0011 violation and risks name collisions with base application objects or other installed extensions.
