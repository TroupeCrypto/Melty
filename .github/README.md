# Troupe Inc. Universe - GitHub Configuration

This directory contains GitHub-specific configuration files for the Troupe Inc. universe repository.

## Contents

- `workflows/` - GitHub Actions workflows for CI/CD

## Workflows

### CI Workflow (`ci.yml`)
- Runs on push and pull requests to main/develop branches
- Lints code for common issues
- Builds projects across all categories
- Runs tests for all projects

### Documentation Workflow (`docs.yml`)
- Runs on changes to markdown and documentation files
- Validates documentation structure
- Checks for broken links

## Adding New Workflows

When adding new workflows:

1. Create a new `.yml` file in the `workflows/` directory
2. Follow GitHub Actions best practices
3. Use appropriate triggers (push, pull_request, schedule, etc.)
4. Include clear job and step names
5. Document the workflow purpose in this README

## Security

- Use GitHub Secrets for sensitive data
- Use `secrets.GITHUB_TOKEN` for repository access
- Review workflow permissions carefully
- Keep actions up to date

## References

- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Workflow Syntax](https://docs.github.com/en/actions/reference/workflow-syntax-for-github-actions)
