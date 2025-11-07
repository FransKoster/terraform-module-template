# Contributing to This Terraform Module

Thank you for your interest in contributing to this Terraform module! This document provides guidelines and instructions for contributing.

## Code of Conduct

Please be respectful and constructive in all interactions.

## How to Contribute

### Reporting Issues

- Check if the issue already exists before creating a new one
- Provide a clear description of the issue
- Include steps to reproduce if applicable
- Add relevant logs or error messages

### Submitting Changes

1. **Fork the repository**
   ```bash
   # Click "Fork" on GitHub, then clone your fork
   git clone https://github.com/YOUR_USERNAME/tf-template.git
   cd tf-template
   ```

2. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Set up the development environment**
   ```bash
   # Install pre-commit
   pip install pre-commit
   pre-commit install

   # Install Terraform and TFLint
   # Follow installation instructions for your OS
   ```

4. **Make your changes**
   - Follow the [Terraform style guide](./.github/copilot/terraform-guidelines.md)
   - Write clear, descriptive commit messages
   - Keep changes focused and minimal
   - Update documentation as needed

5. **Test your changes**
   ```bash
   # Format code
   terraform fmt -recursive

   # Validate configuration
   terraform init -backend=false
   terraform validate

   # Run TFLint
   tflint --init
   tflint --recursive

   # Test examples
   cd examples/basic
   terraform init -backend=false
   terraform validate
   cd ../..
   ```

6. **Run pre-commit checks**
   ```bash
   pre-commit run --all-files
   ```

7. **Commit your changes**
   ```bash
   git add .
   git commit -m "feat: add new feature"
   ```

8. **Push to your fork**
   ```bash
   git push origin feature/your-feature-name
   ```

9. **Create a Pull Request**
   - Go to the original repository on GitHub
   - Click "New Pull Request"
   - Select your fork and branch
   - Provide a clear description of your changes
   - Reference any related issues

## Development Guidelines

### Terraform Code Style

- Use 2 spaces for indentation
- Use snake_case for all names
- Add descriptions to all variables and outputs
- Include examples for new features
- Follow the guidelines in [terraform-guidelines.md](./.github/copilot/terraform-guidelines.md)

### Documentation

- Update README.md for significant changes
- Add examples for new features
- Update docs/ directory as needed
- Keep documentation clear and concise

### Commit Message Format

Use conventional commit format:

- `feat:` - New features
- `fix:` - Bug fixes
- `docs:` - Documentation changes
- `style:` - Code style changes (formatting, etc.)
- `refactor:` - Code refactoring
- `test:` - Test additions or changes
- `chore:` - Build process or tooling changes

Examples:
```
feat: add support for custom tags
fix: correct variable validation logic
docs: update usage examples
```

### Testing

- Test all changes locally before submitting
- Ensure examples work correctly
- Run all validation checks
- Add new examples if introducing new features

### Pull Request Guidelines

- Keep PRs focused on a single change
- Provide a clear description of what and why
- Reference related issues
- Ensure all checks pass
- Respond to review feedback promptly

## Getting Help

- Check the [documentation](./docs/)
- Review [existing issues](../../issues)
- Ask questions in new issues with the "question" label

## Review Process

1. Automated checks must pass (terraform fmt, validate, tflint)
2. At least one maintainer review required
3. Address all review comments
4. Maintainer will merge when approved

## License

By contributing, you agree that your contributions will be licensed under the same license as the project.

Thank you for contributing! 🎉
