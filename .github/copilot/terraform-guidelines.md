# GitHub Copilot Instructions for Terraform Development

## General Guidelines

You are an expert Terraform developer working on infrastructure as code. Follow these guidelines when generating or modifying Terraform code:

## Code Style and Formatting

- Use snake_case for all resource names, variable names, and output names
- Indent with 2 spaces
- Keep lines under 120 characters where possible
- Group related resources together
- Add blank lines between resource blocks for readability
- Use descriptive names that clearly indicate the purpose of the resource

## Best Practices

### Resource Naming
- Prefix resource names with the resource type (e.g., `aws_s3_bucket.example`)
- Use meaningful, descriptive names that indicate the resource's purpose
- Avoid abbreviations unless they are widely understood

### Variables
- Always include a description for each variable
- Specify the variable type explicitly
- Provide default values when appropriate
- Use validation blocks for input validation where necessary
- Group related variables together with comments

### Outputs
- Always include a description for each output
- Output values that might be useful for other modules or users
- Use descriptive output names

### Documentation
- Add comments for complex logic or non-obvious configurations
- Use inline comments sparingly, prefer descriptive resource names
- Keep README.md up to date with module usage examples

### Security
- Never hardcode sensitive values (passwords, API keys, etc.)
- Use variables for sensitive data and mark them as sensitive
- Follow the principle of least privilege for IAM policies
- Enable encryption where available (S3, RDS, EBS, etc.)
- Use secure defaults (e.g., private S3 buckets, encrypted storage)

### Versioning
- Always specify provider versions using version constraints
- Use semantic versioning for module versions
- Pin module sources to specific versions or tags
- Use `required_version` to specify the minimum Terraform version

### Modules
- Keep modules focused on a single responsibility
- Use outputs to expose only necessary values
- Document module inputs and outputs
- Include examples of module usage
- Avoid deeply nested module calls

### State Management
- Never commit .tfstate files
- Use remote state for team collaboration
- Enable state locking to prevent concurrent modifications
- Use workspaces for environment separation when appropriate

## Code Structure

### File Organization
```
.
├── main.tf           # Main resources
├── variables.tf      # Input variables
├── outputs.tf        # Output values
├── versions.tf       # Provider and Terraform version constraints
├── README.md         # Documentation
├── examples/         # Usage examples
│   └── basic/
│       ├── main.tf
│       └── variables.tf
└── docs/            # Additional documentation
```

### Resource Blocks
```hcl
resource "provider_resource_type" "name" {
  # Required arguments first
  required_arg = "value"

  # Optional arguments second
  optional_arg = "value"

  # Nested blocks last
  nested_block {
    key = "value"
  }

  # Tags last (if applicable)
  tags = {
    Name        = "resource-name"
    Environment = var.environment
    ManagedBy   = "Terraform"
  }
}
```

### Variable Blocks
```hcl
variable "example" {
  description = "A clear description of the variable's purpose"
  type        = string
  default     = "default-value"

  validation {
    condition     = length(var.example) > 0
    error_message = "The example variable must not be empty."
  }
}
```

### Output Blocks
```hcl
output "example" {
  description = "A clear description of the output's value"
  value       = resource.example.attribute
  sensitive   = false
}
```

## Common Patterns

### Data Sources
- Use data sources to reference existing resources
- Prefer data sources over hardcoded values
- Add error handling for data source lookups

### Conditional Resources
- Use `count` or `for_each` for conditional resource creation
- Prefer `for_each` for creating multiple similar resources
- Use `count = var.enabled ? 1 : 0` for conditional single resources

### Loops and Iterations
- Use `for_each` with maps for more readable code
- Use `for` expressions for transforming collections
- Use `dynamic` blocks for repeating nested blocks

### Local Values
- Use locals for computed values used multiple times
- Use locals to simplify complex expressions
- Keep locals close to where they're used

## Testing and Validation

- Run `terraform fmt` before committing
- Run `terraform validate` to check syntax
- Use `terraform plan` to preview changes
- Run TFLint to catch common mistakes
- Use pre-commit hooks for automated checks
- Write examples that can be used as integration tests

## Error Handling

- Use validation blocks in variables
- Add precondition and postcondition blocks where appropriate
- Provide helpful error messages
- Use lifecycle rules to prevent accidental deletions

## Performance

- Use `depends_on` only when necessary
- Avoid unnecessary data source lookups
- Use `-parallelism` flag for large deployments
- Consider using `-target` for specific resource updates during development

## Migration and Refactoring

- Use `terraform state mv` to rename resources
- Use `moved` blocks for Terraform 1.1+
- Document any manual state changes
- Test migrations in a non-production environment first

## Common Anti-Patterns to Avoid

- ❌ Hardcoding values that should be variables
- ❌ Using deprecated syntax or features
- ❌ Creating overly complex modules
- ❌ Ignoring provider version constraints
- ❌ Not using remote state for team projects
- ❌ Committing sensitive data
- ❌ Using `count` with lists that might change order
- ❌ Creating circular dependencies between resources

## Examples

When generating examples, include:
- A basic example showing minimal required configuration
- An advanced example showing all options
- README.md explaining the example
- Variable definitions with sensible defaults
- Comments explaining key decisions

Remember: Write clear, maintainable, and secure infrastructure as code!
