# GitHub Actions Boilerplate

A comprehensive collection of GitHub Actions workflows and configuration files to jumpstart your CI/CD pipeline. This repository provides ready-to-use workflows for common development scenarios including Node.js, Python, Docker, security scanning, and automated releases.

## 🚀 Features

### Workflows Included

- **Node.js CI** (`nodejs-ci.yml`) - Automated testing across multiple Node.js versions with linting, testing, and coverage reporting
- **Python CI** (`python-ci.yml`) - Python testing pipeline with flake8 linting and pytest coverage
- **Docker Build** (`docker-build.yml`) - Multi-platform Docker image building and publishing to GitHub Container Registry
- **Pull Request Validation** (`pr-validation.yml`) - Automated PR checks including semantic PR titles and merge conflict detection
- **CodeQL Security Scan** (`codeql.yml`) - Automated security vulnerability scanning
- **Release Automation** (`release.yml`) - Automated release creation with changelog generation
- **Auto Format** (`auto-format.yml`) - Automatic code formatting for JavaScript/TypeScript and Python
- **Stale Issues Management** (`stale-issues.yml`) - Automatic management of stale issues and PRs

### Configuration Files

- **Dependabot** (`dependabot.yml`) - Automated dependency updates
- **Issue Templates** - Bug reports and feature requests
- **Pull Request Template** - Standardized PR descriptions
- **Code Quality Tools**:
  - ESLint configuration (`.eslintrc.json`)
  - Prettier configuration (`.prettierrc`)
  - Commitlint configuration (`.commitlintrc.json`)
- **Docker Configuration**:
  - Multi-stage Dockerfile
  - Optimized `.dockerignore`
- **Git Configuration**:
  - Comprehensive `.gitignore`

## 📋 Quick Start

1. **Copy workflows to your repository**:
   ```bash
   # Create the GitHub workflows directory
   mkdir -p .github/workflows
   
   # Copy the workflow files you need
   cp .github/workflows/* your-repo/.github/workflows/
   ```

2. **Customize for your project**:
   - Update workflow triggers (branches, paths)
   - Modify Node.js/Python versions in matrix builds
   - Adjust Docker registry settings
   - Configure secrets if needed

3. **Set up repository secrets** (if required):
   - `GITHUB_TOKEN` (automatically provided)
   - `CODECOV_TOKEN` (for code coverage)
   - Custom secrets for your specific workflows

## 🔧 Workflow Configuration

### Node.js CI Workflow

```yaml
# Triggers on push/PR to main and develop branches
# Tests against Node.js 16.x, 18.x, 20.x
# Runs: lint, test, build, coverage upload
```

**Prerequisites**:
- `package.json` with scripts: `lint`, `test`, `build`
- Jest or similar test framework configured

### Python CI Workflow

```yaml
# Triggers on push/PR to main and develop branches  
# Tests against Python 3.9, 3.10, 3.11, 3.12
# Runs: flake8 linting, pytest with coverage
```

**Prerequisites**:
- `requirements.txt` and/or `requirements-dev.txt`
- pytest configured for testing

### Docker Workflow

```yaml
# Builds multi-platform images (linux/amd64, linux/arm64)
# Pushes to GitHub Container Registry
# Tags based on branch/tag patterns
```

**Prerequisites**:
- `Dockerfile` in repository root
- Package write permissions enabled

### Security Workflows

- **CodeQL**: Scans for security vulnerabilities
- **Dependabot**: Keeps dependencies updated
- **PR Validation**: Ensures quality standards

## 🛠️ Customization Guide

### Modifying Workflow Triggers

```yaml
on:
  push:
    branches: [ main, develop, staging ]  # Add your branches
    paths: [ 'src/**' ]                   # Only trigger on specific paths
  pull_request:
    branches: [ main ]
```

### Adding New Languages

For additional language support, extend the CodeQL workflow:

```yaml
matrix:
  language: [ 'javascript', 'python', 'go', 'java' ]  # Add languages
```

### Environment-Specific Configurations

Create environment-specific workflow files:
- `.github/workflows/deploy-staging.yml`
- `.github/workflows/deploy-production.yml`

## 📊 Monitoring and Badges

Add status badges to your README:

```markdown
![CI](https://github.com/username/repo/workflows/CI/badge.svg)
![Security](https://github.com/username/repo/workflows/CodeQL/badge.svg)
![Docker](https://github.com/username/repo/workflows/Docker/badge.svg)
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Add tests if applicable
5. Submit a pull request

## 📚 Workflow Examples

### Basic Node.js Project Setup

```json
{
  "scripts": {
    "lint": "eslint src/",
    "test": "jest",
    "build": "webpack --mode production",
    "start": "node dist/index.js"
  }
}
```

### Python Project Structure

```
project/
├── requirements.txt
├── requirements-dev.txt
├── src/
│   └── main.py
├── tests/
│   └── test_main.py
└── setup.py
```

## 🔒 Security Considerations

- All workflows use pinned action versions (e.g., `@v4`)
- Minimal permissions granted to jobs
- Secrets handled securely
- Container images built from trusted base images
- Regular dependency updates via Dependabot

## 📝 License

This boilerplate is provided as-is under the MIT License. Feel free to use, modify, and distribute.

## 🆘 Troubleshooting

### Common Issues

1. **Workflow not triggering**: Check branch names and path filters
2. **Permission denied**: Ensure proper repository permissions
3. **Missing secrets**: Configure required secrets in repository settings
4. **Test failures**: Verify test commands and dependencies

### Getting Help

- Check GitHub Actions documentation
- Review workflow run logs
- Open an issue for specific problems

---

**Happy automating! 🎉**