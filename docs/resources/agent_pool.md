---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe_agent_pool Resource - terraform-provider-tfe"
subcategory: ""
description: |-
  An agent pool represents a group of agents, often related to one another by sharing a common network segment or purpose. A workspace may be configured to use one of the organization's agent pools to run remote operations with isolated, private, or on-premises infrastructure.
  ~> NOTE: This resource requires using the provider with Terraform Cloud and a Terraform Cloud for Business account. Learn more about Terraform Cloud pricing here https://www.hashicorp.com/products/terraform/pricing?_ga=2.56441195.1392855715.1658762101-1323299352.1652184430.
---

# tfe_agent_pool

An agent pool represents a group of agents, often related to one another by sharing a common network segment or purpose. A workspace may be configured to use one of the organization's agent pools to run remote operations with isolated, private, or on-premises infrastructure.

 ~> **NOTE:** This resource requires using the provider with Terraform Cloud and a Terraform Cloud for Business account. [Learn more about Terraform Cloud pricing here](https://www.hashicorp.com/products/terraform/pricing?_ga=2.56441195.1392855715.1658762101-1323299352.1652184430).

## Example Usage 

```terraform
resource "tfe_organization" "test-organization" {
  name  = "my-org-name"
  email = "admin@company.com"
}

resource "tfe_agent_pool" "test-agent-pool" {
  name         = "my-agent-pool-name"
  organization = tfe_organization.test-organization.name
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- `name` (String) Name of the agent pool.
- `organization` (String) Name of the organization.

### Read-Only

- `id` (String) The ID of this resource.

## Import

Import is supported using the following syntax:

```shell
# Use <AGENT POOL ID> as the import ID. For example:

terraform import tfe_agent_pool.test apool-rW0KoLSlnuNb5adB
```