---
bc-version: [all]
domain: style
keywords: [label, constant, error, message, localization, suffix, err, txt, hardcoded-string]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Use Label constants with Err or Txt suffix for all user-facing text

## Description

Every user-facing string must be declared as a `Label` constant rather than a hardcoded string literal. Hardcoded strings cannot be translated and are invisible to localization tooling. Within the Label convention, error messages must end with `Err` (e.g., `NoSubdomainErr`, `ParseFailedErr`) and all other UI text — messages, captions, prompts, status strings — must end with `Txt` (e.g., `SyncSuccessTxt`, `BoardsLoadingTxt`). The suffix distinguishes error labels from informational ones at a glance.

## Best Practice

Declare all user-visible strings as `Label` constants in the `var` section or at the top of the codeunit. Pass them to `Error()`, `Message()`, and `StrSubstNo()` by reference. Apply `Err` to anything passed to `Error()` and `Txt` to everything else.

## Anti Pattern

Writing `Error('Record not found')` or `Message('Sync complete')` with inline string literals skips localization and makes text updates fragile (each literal must be found and changed individually). Using no suffix — or mixing suffixes inconsistently — makes it hard to identify error labels when reviewing.
