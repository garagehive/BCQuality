---
bc-version: [all]
domain: ui
keywords: [tooltip, table, field, page, property, consistency, dead-code]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Define ToolTip on the table field; omit it for fields never shown on a page

## Description

`ToolTip` must be set on the **table field** definition, not on the page field control. A tooltip defined in the table is automatically shown by every page that displays the field, ensuring consistency without duplication. Conversely, a table field that is never displayed on any page should carry no `ToolTip` — adding one is dead weight that inflates the table and will never be seen by a user.

## Best Practice

Add `ToolTip` to a table field at the point when you add that field to its first page. Write it once in the table. All subsequent pages that include the field inherit the same text automatically. For internal-only fields used exclusively in code, omit `ToolTip`.

## Anti Pattern

Defining `ToolTip` on the page field control instead of the table field. When the same field appears on multiple pages, each carrying its own tooltip text, the texts diverge over time and require separate maintenance. Adding `ToolTip` to a table field that is never rendered on any page is equally wasteful.
