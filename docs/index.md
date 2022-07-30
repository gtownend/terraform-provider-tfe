---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "tfe Provider"
subcategory: ""
description: |-
  
---

# tfe Provider





<!-- schema generated by tfplugindocs -->
## Schema

### Optional

- `hostname` (String) The Terraform Enterprise hostname to connect to. Defaults to app.terraform.io.
- `ssl_skip_verify` (Boolean) Whether or not to skip certificate verifications.
- `token` (String) The token used to authenticate with Terraform Enterprise. We recommend omitting
the token which can be set as credentials in the CLI config file.