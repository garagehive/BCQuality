---
bc-version: [all]
domain: security
keywords: [permission-set, ghsuper, rimd, table, access, administrator, rbac]
technologies: [al]
countries: [w1]
application-area: [all]
---

# Add every new table to the GH Super permission set with RIMD permissions

## Description

Every new table must be added to the `GHSuper` permission set (`GHSuper.permissionset.al`) with `Read, Insert, Modify, Delete` (RIMD) permissions before the code is merged. This ensures administrators have full access to all extension tables through BC's role-based access control system from day one. A table missing from the permission set is invisible to RBAC tooling, blocking delegated-access setup, support queries, and data-migration tasks.

## Best Practice

After creating a new table, open `GHSuper.permissionset.al` and add an RIMD entry for the new table object. Treat this as a mandatory final step of table creation, not a post-release cleanup task.

## Anti Pattern

Creating a table without updating `GHSuper.permissionset.al`. The table may be usable by code running in an elevated context, but administrators cannot grant or inspect access through standard BC permission tooling. The gap is often only discovered when support needs to query the table or when setting up delegated permissions.
