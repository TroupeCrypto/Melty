# Contributing to Troupe Inc. Universe

Thank you for your interest in contributing to the Troupe Inc. universe! This document provides guidelines for contributing to this consolidated repository.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [Repository Structure](#repository-structure)
- [Merging Repositories](#merging-repositories)
- [Development Workflow](#development-workflow)
- [Pull Request Process](#pull-request-process)
- [Coding Standards](#coding-standards)

## Code of Conduct

- Be respectful and inclusive
- Focus on constructive feedback
- Help maintain a welcoming environment
- Follow professional communication standards

## Getting Started

1. **Clone the repository**
   ```bash
   git clone https://github.com/TroupeCrypto/Melty.git
   cd Melty
   ```

2. **Set up your development environment**
   - Install dependencies for the projects you're working on
   - Follow project-specific setup instructions in individual README files

3. **Create a feature branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

## Repository Structure

See [STRUCTURE.md](STRUCTURE.md) for detailed information about how the repository is organized.

Key directories:
- `apps/` - Standalone applications
- `libs/` - Shared libraries and utilities
- `services/` - Backend services and APIs
- `tools/` - Development and deployment tools
- `docs/` - Documentation and resources

## Merging Repositories

When merging an existing repository into the Troupe Inc. universe:

### Pre-Merge Checklist

- [ ] Review the repository for sensitive data or credentials
- [ ] Clean up unnecessary files (build artifacts, dependencies)
- [ ] Ensure all tests pass in the original repository
- [ ] Document any breaking changes or migration requirements
- [ ] Choose the appropriate category directory (apps, libs, services, tools)

### Merge Process

1. **Add the repository as a remote**
   ```bash
   git remote add -f <project-name> <repository-url>
   ```

2. **Merge preserving history**
   ```bash
   git merge -s ours --no-commit --allow-unrelated-histories <project-name>/main
   git read-tree --prefix=<category>/<project-name>/ -u <project-name>/main
   git commit -m "Merge <project-name> into Troupe Inc. universe"
   ```

3. **Clean up**
   ```bash
   git remote remove <project-name>
   ```

4. **Post-merge tasks**
   - Update [PROJECTS.md](PROJECTS.md) with the new project
   - Adjust configuration files and paths
   - Update import statements if needed
   - Verify builds and tests pass
   - Update documentation

## Development Workflow

1. **Branch naming conventions**
   - `feature/` - New features
   - `fix/` - Bug fixes
   - `docs/` - Documentation changes
   - `refactor/` - Code refactoring
   - `test/` - Test additions or modifications

2. **Commit messages**
   - Use clear, descriptive commit messages
   - Start with a verb in present tense (Add, Fix, Update, Remove)
   - Reference issue numbers when applicable
   - Example: `Add authentication service to libs/auth`

3. **Testing**
   - Write tests for new features
   - Ensure existing tests pass
   - Run tests locally before pushing
   - Follow project-specific testing conventions

## Pull Request Process

1. **Before submitting**
   - Ensure your code follows the project's coding standards
   - Update documentation as needed
   - Add or update tests
   - Verify all tests pass
   - Rebase on the latest main branch if needed

2. **PR Description**
   - Clearly describe what changes were made and why
   - Reference any related issues
   - Include screenshots for UI changes
   - List any breaking changes
   - Note any new dependencies

3. **Review process**
   - Address reviewer feedback promptly
   - Keep discussions focused and professional
   - Make requested changes in new commits
   - Update the PR description if the scope changes

4. **Merging**
   - PRs require approval before merging
   - Ensure CI/CD checks pass
   - Use squash merge for feature branches
   - Delete the branch after merging

## Coding Standards

### General Guidelines

- Write clean, readable, and maintainable code
- Follow the principle of least surprise
- Keep functions small and focused
- Use meaningful variable and function names
- Comment complex logic, not obvious code
- Remove commented-out code before committing

### Project-Specific Standards

Each project may have its own coding standards. Check the project's README or CONTRIBUTING file for specific guidelines.

### Documentation

- Keep README files up to date
- Document public APIs and interfaces
- Include usage examples
- Explain non-obvious design decisions
- Update PROJECTS.md when adding new projects

### Security

- Never commit secrets, API keys, or credentials
- Use environment variables for sensitive configuration
- Follow security best practices for your language/framework
- Report security vulnerabilities privately to maintainers

## Questions?

If you have questions about contributing:
- Check existing documentation (README, STRUCTURE, PROJECTS)
- Review closed issues and PRs for similar topics
- Open a discussion or issue for clarification

## License

By contributing to this repository, you agree that your contributions will be licensed under the same license as the project.
