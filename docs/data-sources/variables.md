---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_variables Data Source - terraform-provider-tfe"
subcategory: ""
description: |-
  
---

# tfe_variables





<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- `variable_set_id` (String)
- `workspace_id` (String)

### Read-Only

- `env` (List of Object) (see [below for nested schema](#nestedatt--env))
- `id` (String) The ID of this resource.
- `terraform` (List of Object) (see [below for nested schema](#nestedatt--terraform))
- `variables` (List of Object) (see [below for nested schema](#nestedatt--variables))

<a id="nestedatt--env"></a>
### Nested Schema for `env`

Read-Only:

- `category` (String)
- `hcl` (Boolean)
- `id` (String)
- `name` (String)
- `sensitive` (Boolean)
- `value` (String)


<a id="nestedatt--terraform"></a>
### Nested Schema for `terraform`

Read-Only:

- `category` (String)
- `hcl` (Boolean)
- `id` (String)
- `name` (String)
- `sensitive` (Boolean)
- `value` (String)


<a id="nestedatt--variables"></a>
### Nested Schema for `variables`

Read-Only:

- `category` (String)
- `hcl` (Boolean)
- `id` (String)
- `name` (String)
- `sensitive` (Boolean)
- `value` (String)
