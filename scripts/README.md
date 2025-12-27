# Scripts

This directory contains build and deployment scripts for the Troupe Inc. universe.

## Structure

Scripts are organized by purpose:
- Build scripts
- Deployment scripts
- Testing scripts
- Maintenance scripts
- Utility scripts

## Adding Scripts

When adding a script:

1. Use clear, descriptive names
2. Include usage comments at the top
3. Handle errors appropriately
4. Make scripts idempotent when possible
5. Document prerequisites and dependencies
6. Test scripts before committing

## Guidelines

- Use shell scripts or language-specific build tools
- Make scripts cross-platform when possible
- Include help text (`--help` flag)
- Log important actions
- Fail fast on errors
- Use environment variables for configuration
