# Usage Guide

This guide provides detailed instructions on how to use this Terraform module.

## Prerequisites

- Terraform >= 1.0
- Appropriate provider credentials configured

## Basic Usage

```hcl
module "example" {
  source = "github.com/FransKoster/tf-template"

  # Configure your variables here
}
```

## Advanced Configuration

For advanced usage examples, please refer to the [examples directory](../examples/).

## Variable Reference

See [variables.tf](../variables.tf) for a complete list of available variables.

## Output Reference

See [outputs.tf](../outputs.tf) for a complete list of available outputs.

## Best Practices

1. Always pin module versions in production
2. Use variables for customization
3. Review terraform plan before applying
4. Keep sensitive data in secure variable stores
5. Use remote state for team collaboration

## Troubleshooting

### Common Issues

**Issue**: Terraform initialization fails
**Solution**: Ensure you have the correct provider credentials configured

**Issue**: Validation errors
**Solution**: Check that all required variables are provided and valid

For more help, please open an issue on GitHub.
