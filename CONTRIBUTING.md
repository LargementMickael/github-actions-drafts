# Contributing to GitHub Actions Boilerplate

Thank you for your interest in contributing to the GitHub Actions Boilerplate! This document provides guidelines and information for contributors.

## 🚀 Getting Started

1. **Fork the repository**
2. **Clone your fork**:
   ```bash
   git clone https://github.com/your-username/github-actions-drafts.git
   cd github-actions-drafts
   ```
3. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

## 📋 Contribution Guidelines

### Types of Contributions

We welcome the following types of contributions:

- **New Workflows**: Add workflows for additional languages, frameworks, or use cases
- **Workflow Improvements**: Enhance existing workflows with better practices or new features
- **Configuration Files**: Add or improve configuration files for development tools
- **Documentation**: Improve README, add examples, or create tutorials
- **Bug Fixes**: Fix issues in existing workflows or configurations
- **Examples**: Add example projects that demonstrate workflow usage

### Workflow Standards

When contributing workflows, please ensure they follow these standards:

#### Security Best Practices
- Pin action versions to specific commits or tags (avoid `@main` or `@master`)
- Use minimal required permissions
- Handle secrets securely
- Include security scanning where appropriate

#### Code Quality
- Use descriptive job and step names
- Add comments for complex logic
- Follow YAML formatting conventions
- Include error handling where necessary

#### Compatibility
- Test across multiple OS environments when applicable
- Support common version ranges (e.g., Node.js 16.x, 18.x, 20.x)
- Ensure workflows work with common project structures

### Example Workflow Structure

```yaml
name: Descriptive Workflow Name

on:
  push:
    branches: [ main, develop ]
  pull_request:
    branches: [ main ]

jobs:
  job-name:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      # Add minimal required permissions

    steps:
    - name: Checkout code
      uses: actions/checkout@v4

    - name: Descriptive step name
      run: |
        # Your commands here
```

## 🧪 Testing Your Contributions

### Before Submitting

1. **Validate YAML syntax**:
   ```bash
   # Test YAML files
   python -c "import yaml; yaml.safe_load(open('.github/workflows/your-workflow.yml'))"
   ```

2. **Test example configurations**:
   ```bash
   # Test JSON configurations
   node -e "JSON.parse(require('fs').readFileSync('package.json.example', 'utf8'))"
   ```

3. **Run workflow validation**:
   - Push to a test repository to verify workflows execute correctly
   - Check for any syntax errors or failures

### Testing Workflows

If possible, test your workflows by:
1. Creating a test repository
2. Adding your workflow
3. Triggering the workflow with appropriate conditions
4. Verifying expected behavior

## 📝 Pull Request Process

1. **Ensure your code follows the project standards**
2. **Update documentation** if you're adding new features
3. **Add examples** for new workflows or configurations
4. **Write a clear PR description** explaining:
   - What the change does
   - Why it's needed
   - How to test it
   - Any breaking changes

### PR Title Format

Use conventional commit format:
- `feat: add workflow for Go projects`
- `fix: correct Node.js version matrix`
- `docs: update README with new examples`
- `refactor: improve Docker workflow efficiency`

## 🎯 Specific Contribution Areas

### High-Priority Contributions

- **Language Support**: Workflows for Go, Rust, PHP, Ruby, etc.
- **Platform Integration**: AWS, Azure, GCP deployment workflows
- **Advanced Features**: Multi-environment deployments, advanced testing strategies
- **Mobile Development**: React Native, Flutter, Ionic workflows
- **Infrastructure**: Terraform, Kubernetes, Helm workflows

### Configuration Files Needed

- More language-specific linting configurations
- IDE-specific settings (VS Code, IntelliJ)
- Additional Docker configurations
- Environment-specific examples

## 🐛 Reporting Issues

When reporting issues:

1. **Use the issue templates** provided
2. **Include specific details**:
   - Which workflow is affected
   - Error messages or logs
   - Steps to reproduce
   - Expected vs actual behavior
3. **Label appropriately** (bug, enhancement, documentation, etc.)

## 💡 Suggesting Enhancements

For feature requests:

1. **Check existing issues** first
2. **Use the feature request template**
3. **Explain the use case** and benefits
4. **Consider implementation complexity**
5. **Provide examples** if possible

## 🔍 Code Review Process

All contributions go through code review:

1. **Automated checks** must pass
2. **Manual review** by maintainers
3. **Testing verification** when possible
4. **Documentation review** for accuracy

### Review Criteria

- Security best practices
- Code quality and clarity
- Compatibility with existing workflows
- Documentation completeness
- Test coverage where applicable

## 📚 Resources

### GitHub Actions Documentation
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Workflow Syntax](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions)
- [Action Marketplace](https://github.com/marketplace?type=actions)

### Best Practices
- [Security hardening](https://docs.github.com/en/actions/security-guides/security-hardening-for-github-actions)
- [Workflow best practices](https://docs.github.com/en/actions/learn-github-actions/workflow-best-practices)

## 🏆 Recognition

Contributors will be:
- Added to the contributors list
- Mentioned in release notes for significant contributions
- Credited in documentation where appropriate

## 📞 Getting Help

If you need help:

1. **Check the documentation** first
2. **Search existing issues**
3. **Create a discussion** for questions
4. **Join community channels** if available

## 📄 License

By contributing, you agree that your contributions will be licensed under the MIT License.

---

Thank you for contributing to make GitHub Actions more accessible for everyone! 🎉