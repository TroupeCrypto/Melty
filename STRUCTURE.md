# Repository Structure

This document describes the organization and architecture of the Troupe Inc. universe repository.

## Directory Structure

```
Melty/
├── apps/               # Standalone applications
├── libs/               # Shared libraries and utilities
├── services/           # Backend services and APIs
├── tools/              # Development and deployment tools
├── docs/               # Documentation and resources
├── scripts/            # Build and deployment scripts
└── .github/            # GitHub workflows and configurations
```

## Organization Principles

### 1. Modular Architecture

Each project maintains its own directory with clear boundaries, enabling:
- Independent development and deployment
- Clear ownership and responsibility
- Easier testing and maintenance

### 2. Shared Resources

Common code and utilities are placed in `libs/` to:
- Reduce duplication
- Ensure consistency across projects
- Simplify updates and bug fixes

### 3. Git History Preservation

When merging repositories:
- Use git subtree merge to preserve history
- Maintain original commit messages and authorship
- Document the merge in PROJECTS.md

## Project Layout

Each project directory should contain:
- `README.md` - Project-specific documentation
- `package.json` / `requirements.txt` / etc. - Dependencies
- `src/` or `lib/` - Source code
- `tests/` - Test files
- `.gitignore` - Project-specific ignore rules

## Build System

The repository supports multiple build systems:
- Individual projects can use their preferred tools
- Root-level scripts coordinate multi-project builds
- CI/CD workflows handle automated testing and deployment

## Dependencies

### Workspace Management

Consider using workspace features for dependency management:
- npm workspaces for Node.js projects
- Python virtual environments
- Go modules

### Versioning

- Each project maintains its own version
- Shared libraries use semantic versioning
- Lock files are committed for reproducible builds

## Development Workflow

1. Clone the repository
2. Install dependencies for needed projects
3. Make changes in appropriate project directories
4. Test affected projects
5. Submit pull requests with clear descriptions

## Migration Guide

### Merging an Existing Repository

To merge an existing repository into Melty:

```bash
# Add the repository as a remote
git remote add -f <project-name> <repository-url>

# Merge the repository into a subdirectory
git merge -s ours --no-commit --allow-unrelated-histories <project-name>/main
git read-tree --prefix=<category>/<project-name>/ -u <project-name>/main
git commit -m "Merge <project-name> into Troupe Inc. universe"

# Remove the remote
git remote remove <project-name>
```

### Post-Merge Tasks

1. Update PROJECTS.md with the new project
2. Adjust paths in configuration files
3. Update import statements if needed
4. Verify builds and tests pass
5. Update documentation

## Best Practices

- Keep projects loosely coupled
- Use clear, consistent naming conventions
- Document dependencies between projects
- Maintain comprehensive READMEs
- Write tests for all code
- Use CI/CD for automated validation
