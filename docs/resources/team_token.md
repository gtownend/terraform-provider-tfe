---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_team_token Resource - terraform-provider-tfe"
subcategory: ""
description: |-
  Generates a new team token and overrides existing token if one exists.
---

# tfe_team_token

Generates a new team token and overrides existing token if one exists.

## Example Usage 

```terraform
resource "tfe_team" "test" {
  name         = "my-team-name"
  organization = "my-org-name"
}

resource "tfe_team_token" "test" {
  team_id = tfe_team.test.id
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `team_id` (String) ID of the team.

### Optional

- `force_regenerate` (Boolean) If set to `true`, a new token will be generated even if a token already exists. This will invalidate the existing token!

### Read-Only

- `id` (String) The ID of this resource.
- `token` (String, Sensitive) The generated token.

## Import

Import is supported using the following syntax:

```shell
# Use <TEAM ID> as the import ID. For example:

terraform import tfe_team_token.test team-47qC3LmA47piVan7
```