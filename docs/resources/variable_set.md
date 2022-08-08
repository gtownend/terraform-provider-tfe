---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_variable_set Resource - terraform-provider-tfe"
subcategory: ""
description: |-
  Creates, updates and destroys variable sets.
---

# tfe_variable_set

Creates, updates and destroys variable sets.

## Example Usage 

Basic usage:

```terraform
resource "tfe_organization" "test" {
  name  = "my-org-name"
  email = "admin@company.com"
}

resource "tfe_workspace" "test" {
  name         = "my-workspace-name"
  organization = tfe_organization.test.name
}

resource "tfe_variable_set" "test" {
  name          = "Test Varset"
  description   = "Some description."
  organization  = tfe_organization.test.name
}

resource "tfe_workspace_variable_set" "test" {
  workspace_id    = tfe_workspace.test.id
  variable_set_id = tfe_variable_set.test.id
}

resource "tfe_variable" "test-a" {
  key             = "seperate_variable"
  value           = "my_value_name"
  category        = "terraform"
  description     = "a useful description"
  variable_set_id = tfe_variable_set.test.id
}

resource "tfe_variable" "test-b" {
  key             = "another_variable"
  value           = "my_value_name"
  category        = "env"
  description     = "an environment variable"
  variable_set_id = tfe_variable_set.test.id
}
```

Creating a global variable set:

```terraform
resource "tfe_organization" "test" {
  name  = "my-org-name"
  email = "admin@company.com"
}

resource "tfe_variable_set" "test" {
  name         = "Global Varset"
  description  = "Variable set applied to all workspaces."
  global       = true
  organization = tfe_organization.test.name
}

resource "tfe_variable" "test-a" {
  key             = "seperate_variable"
  value           = "my_value_name"
  category        = "terraform"
  description     = "a useful description"
  variable_set_id = tfe_variable_set.test.id
}

resource "tfe_variable" "test-b" {
  key             = "another_variable"
  value           = "my_value_name"
  category        = "env"
  description     = "an environment variable"
  variable_set_id = tfe_variable_set.test.id
}
```

Creating a variable set that is applied based on workspace tags:

```terraform
resource "tfe_organization" "test" {
  name  = "my-org-name"
  email = "admin@company.com"
}

data "tfe_workspace_ids" "prod-apps" {
  tag_names    = ["prod", "app", "aws"]
  organization = tfe_organization.test.name
}

resource "tfe_variable_set" "test" {
  name          = "Tag Based Varset"
  description   = "Variable set applied to workspaces based on tag."
  organization  = tfe_organization.test.name
}

resource "tfe_workspace_variable_set" "test" {
  for_each        = toset(values(data.tfe_workspace_ids.prod-apps.ids))
  workspace_id    = each.key
  variable_set_id = tfe_variable_set.test.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String)
- `organization` (String)

### Optional

- `description` (String)
- `global` (Boolean)
- `workspace_ids` (Set of String)

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
# Use `<VARIABLE SET ID>` as the import ID. For example:

terraform import tfe_variable_set.test varset-5rTwnSaRPogw6apb
```
