# Terraform Module Template

A comprehensive template repository for creating Terraform modules with best practices, automated validation, and complete documentation structure.

## Features

- ✅ **Automated Validation**: GitHub Actions workflows for terraform fmt, validate, and tflint
- ✅ **Pre-commit Hooks**: Automated code quality checks before commits
- ✅ **TFLint Configuration**: Linting rules for Terraform best practices
- ✅ **Dependabot**: Automated dependency updates for Terraform and GitHub Actions
- ✅ **Examples**: Sample configurations demonstrating module usage
- ✅ **Documentation**: Comprehensive docs for users and contributors
- ✅ **GitHub Copilot**: AI-assisted development with Terraform-specific guidelines

## Quick Start

### Using This Template

1. Click "Use this template" to create a new repository
2. Clone your new repository
3. Customize the module files (`main.tf`, `variables.tf`, `outputs.tf`)
4. Update this README with your module's specific documentation
5. Add your resources and logic

### Using This Module

```hcl
module "example" {
  source = "github.com/FransKoster/tf-template"

  # Add your variables here
}
```

## Prerequisites

- [Terraform](https://www.terraform.io/downloads.html) >= 1.0
- [TFLint](https://github.com/terraform-linters/tflint) (for local development)
- [Pre-commit](https://pre-commit.com/) (for local development)

## Development Setup

### Install Pre-commit Hooks

```bash
# Install pre-commit
pip install pre-commit

# Install the git hooks
pre-commit install

# (Optional) Run against all files
pre-commit run --all-files
```

### Local Validation

```bash
# Format code
terraform fmt -recursive

# Initialize
terraform init

# Validate
terraform validate

# Run TFLint
tflint --init
tflint --recursive
```

## Repository Structure

```
.
├── .github/
│   ├── copilot/
│   │   └── terraform-guidelines.md  # GitHub Copilot instructions
│   ├── workflows/
│   │   └── terraform-validation.yml # CI/CD validation workflows
│   └── dependabot.yml               # Dependency update configuration
├── docs/
│   ├── README.md                    # Documentation index
│   ├── usage.md                     # Usage guide
│   ├── examples.md                  # Example configurations
│   └── faq.md                       # Frequently asked questions
├── examples/
│   └── basic/                       # Basic usage example
│       ├── README.md
│       ├── main.tf
│       └── variables.tf
├── .pre-commit-config.yaml          # Pre-commit hook configuration
├── .tflint.hcl                      # TFLint configuration
├── main.tf                          # Main module resources
├── variables.tf                     # Input variables
├── outputs.tf                       # Output values
├── versions.tf                      # Version constraints
└── README.md                        # This file
```

## Validation Workflows

This repository includes automated validation workflows that run on pull requests and pushes:

- **Terraform Format**: Checks code formatting with `terraform fmt`
- **Terraform Validate**: Validates Terraform configuration syntax
- **TFLint**: Lints Terraform code for best practices and potential issues

## Pre-commit Hooks

Pre-commit hooks automatically run the following checks:

- Terraform formatting (`terraform fmt`)
- Terraform validation (`terraform validate`)
- Terraform documentation generation (`terraform-docs`)
- TFLint validation
- Checkov security scanning
- General file checks (trailing whitespace, YAML syntax, etc.)

## Dependabot

Dependabot is configured to automatically update:

- GitHub Actions versions (weekly)
- Terraform provider versions (weekly)
- Example dependencies (weekly)

## Examples

See the [examples directory](./examples/) for working examples of how to use this module.

- [Basic Example](./examples/basic/) - Minimal configuration

## Documentation

Additional documentation is available in the [docs directory](./docs/):

- [Usage Guide](./docs/usage.md) - Detailed usage instructions
- [Examples](./docs/examples.md) - Common usage patterns
- [FAQ](./docs/faq.md) - Frequently asked questions

## GitHub Copilot

This repository includes [GitHub Copilot guidelines](./.github/copilot/terraform-guidelines.md) to help with AI-assisted Terraform development. These guidelines include:

- Code style and formatting standards
- Security best practices
- Common patterns and anti-patterns
- Testing and validation approaches

## Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Run validation checks locally
5. Submit a pull request

See [CONTRIBUTING.md](./CONTRIBUTING.md) for detailed contribution guidelines.

## License

MIT License - see [LICENSE](./LICENSE) file for details.

## Authors

[Specify authors/maintainers here]

## Support

For issues, questions, or contributions, please open an issue or pull request on GitHub.
<!-- BEGINNING OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0 |

## Providers

No providers.

## Modules

No modules.

## Resources

No resources.

## Inputs

No inputs.

## Outputs

No outputs.
<!-- END OF PRE-COMMIT-TERRAFORM DOCS HOOK -->
