---
subcategory: "VPC Lattice"
layout: "aws"
page_title: "AWS: aws_vpclattice_service_network_service_association"
description: |-
  Terraform resource for managing an AWS VPC Lattice Service Network Service Association.
---

# Resource: aws_vpclattice_service_network_service_association

Terraform resource for managing an AWS VPC Lattice Service Network Service Association.

## Example Usage

### Basic Usage

```terraform
resource "aws_vpclattice_vpclattice_servicenetwork_service_association" "example" {
  service_identifier         = aws_vpclattice_service.example.id
  service_network_identifier = aws_vpclattice_service_network.example.id
}
```

## Argument Reference

The following arguments are required:

* `service_identifier` - (Required) The ID or Amazon Resource Identifier (ARN) of the service.
* `service_network_identifier` - (Required) The ID or Amazon Resource Identifier (ARN) of the service network. You must use the ARN if the resources specified in the operation are in different accounts.
The following arguments are optional:

* `tags` - (Optional) Key-value mapping of resource tags. If configured with a provider [`default_tags` configuration block](/docs/providers/aws/index.html#default_tags-configuration-block) present, tags with matching keys will overwrite those defined at the provider-level.

## Attributes Reference

In addition to all arguments above, the following attributes are exported:

* `arn` - The ARN of the Association.
* `created_by` - The account that created the association.
* `custom_domain_name` - The custom domain name of the service.
* `dns_entry` - The DNS name of the service.
    * `domain_name` - The domain name of the service.
    * `hosted_zone_id` - The ID of the hosted zone.
* `id` - The ID of the association.
* `status` - The operations status. Valid Values are CREATE_IN_PROGRESS | ACTIVE | DELETE_IN_PROGRESS | CREATE_FAILED | DELETE_FAILED
* `tags_all` - Map of tags assigned to the resource, including those inherited from the provider [`default_tags` configuration block](/docs/providers/aws/index.html#default_tags-configuration-block).

## Timeouts

[Configuration options](https://developer.hashicorp.com/terraform/language/resources/syntax#operation-timeouts):

* `create` - (Default `5m`)
* `delete` - (Default `5m`)

## Import

VPC Lattice Service Network Service Association can be imported using the `id`, e.g.,

```
$ terraform import aws_vpclattice_service_network_service_association.example snsa-05e2474658a88f6ba
```
