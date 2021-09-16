---
# generated by https://github.com/hashicorp/terraform-plugin-docs
page_title: "astra_access_list Resource - terraform-provider-astra"
subcategory: ""
description: |-
  astra_access_list resource represents a database access list, used to limit the ip's / CIDR groups that have access to a database.
---

# astra_access_list (Resource)

`astra_access_list` resource represents a database access list, used to limit the ip's / CIDR groups that have access to a database.

## Example Usage

```terraform
resource "astra_access_list" "example" {
  database_id = "a6bc9c26-e7ce-424f-84c7-0a00afb12588"
  addresses {
    request {
      address = "0.0.0.0/0"
      enabled = true
    }
  }
}
```

<!-- schema generated by tfplugindocs -->
## Schema

### Required

- **addresses** (Block List, Min: 1) List of address requests that should have access to database endpoints. (see [below for nested schema](#nestedblock--addresses))
- **database_id** (String) The ID of the Astra database.

### Optional

- **id** (String) The ID of this resource.

<a id="nestedblock--addresses"></a>
### Nested Schema for `addresses`

Required:

- **request** (Block Set, Min: 1) (see [below for nested schema](#nestedblock--addresses--request))

<a id="nestedblock--addresses--request"></a>
### Nested Schema for `addresses.request`

Required:

- **address** (String) Address
- **enabled** (Boolean) Description

Optional:

- **description** (String) Description

## Import

Import is supported using the following syntax:

```shell
# the import id includes the database_id and the keyspace name.
terraform import astra_access_list.example 48bfc13b-c1a5-48db-b70f-b6ef9709872b/keyspace/example
```