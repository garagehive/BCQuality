---
bc-version: [all]
domain: style
keywords: [file-name, object-name, rename, prefix, al-file, pascalcase]
technologies: [al]
countries: [w1]
application-area: [all]
---

# AL file name must match the object name without the GHV prefix

## Description

AL source files must be named after the object they contain, with the "GHV" prefix removed and spaces omitted. The file suffix follows BC convention: `<ObjectNameWithoutPrefix>.<ObjectType>.al`. For example, object `GHV App Build List` belongs in `AppBuildList.Page.al`. When an object is renamed, the file must be renamed to match. Mismatched names make objects hard to locate and break tooling and scripts that assume the naming convention.

## Best Practice

When naming or renaming an object, derive the file name by stripping the "GHV" prefix, removing spaces, and applying PascalCase: `GHV App Build Mgt` → `AppBuildMgt.Codeunit.al`. Rename both the file and update any workspace references as needed.

## Anti Pattern

Leaving a file named after an old object name after a rename, or using a generic name like `Codeunit1.al`. A file `AppBuildMgt.Codeunit.al` that contains `codeunit "GHV Deployment Management"` violates the convention and makes the object hard to find.
