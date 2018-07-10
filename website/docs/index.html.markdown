---
layout: "terraform-enterprise"
page_title: "Provider: Atlas"
sidebar_current: "docs-terraform-enterprise-index"
description: |-
  The Atlas provider was used to interact with configuration,
  artifacts, and metadata managed by the discontinued Atlas service.
---

# Atlas Provider

~> **This provider is deprecated,** and the service it interacts with has been discontinued.

The Atlas provider was used to interact with objects in Atlas's artifact registry, which were usually machine images built with Packer. In 2018, the Atlas suite was discontinued. It is replaced by [Terraform Enterprise](https://www.terraform.io/docs/enterprise/index.html), which focuses on the core Terraform workflow and does not include an artifact registry. For more information, see [Differences Between Current and Legacy Terraform Enterprise](https://www.terraform.io/docs/enterprise/upgrade/differences.html).

The provider needs to be configured with the proper credentials before it can
be used.

Use the navigation to the left to read about the available resources.

## Example Usage

```hcl
# Configure the Atlas provider
provider "atlas" {
  token = "${var.atlas_token}"
}

# Fetch an artifact configuration
data "atlas_artifact" "web" {
  # ...
}
```

## Argument Reference

The following arguments are supported:

* `address` - (Optional) Atlas server endpoint. Defaults to
  public Atlas. This is only required when using an on-premise
  deployment of Atlas. This can also be specified with the
  `ATLAS_ADDRESS` shell environment variable.

* `token` - (Required) API token. This can also be specified with the
  `ATLAS_TOKEN` shell environment variable.
