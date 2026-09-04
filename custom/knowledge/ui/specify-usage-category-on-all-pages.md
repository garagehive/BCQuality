---
bc-version: [all]
domain: ui
keywords: [usagecategory, page, search, tell-me, discoverability, list, card, none, navigation]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Always specify UsageCategory; use None for pages that must not appear in search

## Description

Every page must declare an explicit `UsageCategory` property. Pages without it are excluded from Tell Me search in a way that is non-obvious — an omitted property looks identical to `None` in the source but may behave differently across BC versions. List and document pages that users should find via Tell Me must use a meaningful category (`Lists`, `Documents`, `Tasks`, `Reports`, `Administration`). Card pages, subpages, FactBox pages, and dialog pages that should not be directly navigable must explicitly set `UsageCategory = None;`.

## Best Practice

For list pages users should discover via Tell Me: `UsageCategory = Lists;`. For card pages, subpages, or any page not meant for direct navigation: `UsageCategory = None;`.

## Anti Pattern

Omitting `UsageCategory` entirely. A list page without it may silently disappear from Tell Me search. A card page without it may unexpectedly appear in search, confusing users who land on it without context.
