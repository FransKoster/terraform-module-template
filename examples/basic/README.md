# Basic Example

This example demonstrates the basic usage of this Terraform module.

## Usage

```hcl
module "example" {
  source = "../.."

  # Add your variables here
  # example_variable = "example-value"
}
```

## Running this Example

```bash
# Initialize Terraform
terraform init

# Review the plan
terraform plan

# Apply the configuration
terraform apply

# Destroy the resources when done
terraform destroy
```

## Requirements

| Name | Version |
|------|---------|
| terraform | >= 1.0 |

## Providers

No providers.

## Inputs

No inputs.

## Outputs

No outputs.
