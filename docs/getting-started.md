# Getting Started with Claude Code Modular Framework

A comprehensive guide to set up and use the modular Claude Code framework for maximum productivity gains.

## Prerequisites

- **Claude Code** installed and configured
- **Git** repository for your project
- **Development environment** set up for your technology stack
- **Basic familiarity** with command-line interfaces

## Installation

### 1. Clone the Template Repository

```bash
git clone https://github.com/your-username/claude-modular.git
cd claude-modular
```

### 2. Copy Framework to Your Project

```bash
# Copy the .claude directory to your project
cp -r .claude /path/to/your/project/

# Copy the template files
cp templates/CLAUDE.md.template /path/to/your/project/CLAUDE.md
```

### 3. Customize Configuration

Navigate to your project and customize the configuration:

```bash
cd /path/to/your/project

# Edit the main configuration file
nano CLAUDE.md

# Customize environment settings
nano .claude/config/settings.json
nano .claude/config/development.json
nano .claude/config/staging.json
nano .claude/config/production.json
```

## Basic Usage

### First Steps

1. **Initialize your development environment:**
   ```bash
   /project:setup-environment
   ```

2. **Create your first feature:**
   ```bash
   /project:create-feature user-authentication
   ```

3. **Review your code:**
   ```bash
   /dev:code-review
   ```

### Command Categories

The framework organizes commands into logical categories:

- **Project** (`/project:*`) - Project management and scaffolding
- **Development** (`/dev:*`) - Development workflow and quality
- **Testing** (`/test:*`) - Test generation and validation
- **Deployment** (`/deploy:*`) - Deployment and operations
- **Documentation** (`/docs:*`) - Documentation generation

### Common Workflows

#### Feature Development Workflow
```bash
# 1. Create feature
/project:create-feature payment-processing

# 2. Generate tests
/test:generate-tests

# 3. Review code quality
/dev:code-review

# 4. Check test coverage
/test:coverage-analysis

# 5. Deploy to staging
/deploy:deploy-staging
```

#### Bug Fix Workflow
```bash
# 1. Debug the issue
/dev:debug-session

# 2. Generate tests for the fix
/test:generate-tests --focus=bug-fix

# 3. Review the fix
/dev:code-review --focus=security

# 4. Deploy the fix
/deploy:prepare-release --type=patch
```

## Configuration Guide

### Environment-Specific Settings

The framework supports layered configuration:

```json
// Base settings.json
{
  "defaults": {
    "max_tokens_per_session": 50000,
    "progressive_disclosure": true
  },
  "security": {
    "require_env_vars": true,
    "audit_logging": true
  }
}

// development.json (overrides base)
{
  "extends": "./settings.json",
  "overrides": {
    "defaults": {
      "max_tokens_per_session": 100000
    },
    "security": {
      "audit_logging": false
    }
  }
}
```

### Project-Specific Customization

Edit your `CLAUDE.md` file to include:

1. **Technology stack** and framework details
2. **Build commands** and development workflow
3. **Architecture notes** and key components
4. **Security considerations** and authentication
5. **Team conventions** and code standards

### Example CLAUDE.md Customization

```markdown
## Project-Specific Commands

### Build and Development
```bash
# Development server
npm run dev

# Build for production
npm run build

# Run tests
npm test

# Run linting
npm run lint
```

### Database Operations
```bash
# Run migrations
npm run migrate

# Seed database
npm run seed
```

## Architecture Notes

### Key Components
- **Authentication Service**: Handles user auth in `src/auth/`
- **API Gateway**: Routes requests in `src/gateway/`
- **Database Layer**: Data access in `src/data/`
```

## Token Optimization

### Progressive Disclosure

The framework automatically optimizes token usage:

- **Just-in-time loading** of command instructions
- **Context compression** for repeated patterns
- **Smart boundary detection** for context switching
- **Modular instruction loading** based on current task

### Best Practices

1. **Use specific commands** rather than generic requests
2. **Clear context** when switching between major tasks
3. **Leverage command categories** for focused work
4. **Monitor token usage** and adjust accordingly

## Security Best Practices

### Environment Variables

Always use environment variables for sensitive data:

```bash
# .env file
DATABASE_URL=postgresql://localhost/myapp
API_KEY=your-api-key-here
JWT_SECRET=your-jwt-secret
```

### Configuration Security

- **Never commit** `.env` files
- **Use templates** for configuration examples
- **Validate permissions** before executing commands
- **Enable audit logging** in production

## Troubleshooting

### Common Issues

**Issue**: Commands not found
**Solution**: Ensure `.claude/commands/` directory is properly copied

**Issue**: Configuration not loading
**Solution**: Check JSON syntax in configuration files

**Issue**: Token limit exceeded
**Solution**: Use `/clear` command and enable progressive disclosure

### Debug Commands

```bash
# Debug current session
/dev:debug-session

# Analyze system performance
/dev:refactor-analysis --focus=performance

# Check test coverage
/test:coverage-analysis
```

## Next Steps

1. **Explore command categories** - Try commands from each category
2. **Customize for your stack** - Adapt commands to your technology
3. **Create custom commands** - Add project-specific workflows
4. **Set up CI/CD integration** - Automate quality gates
5. **Train your team** - Share knowledge and best practices

## Resources

- **Command Reference**: [All available commands](./command-reference.md)
- **Configuration Guide**: [Detailed configuration options](./configuration-guide.md)
- **Security Guide**: [Security best practices](./security-best-practices.md)
- **Troubleshooting**: [Common issues and solutions](./troubleshooting.md)

## Support

- **Issues**: [GitHub Issues](https://github.com/your-username/claude-modular/issues)
- **Discussions**: [GitHub Discussions](https://github.com/your-username/claude-modular/discussions)
- **Documentation**: [Full documentation](https://github.com/your-username/claude-modular/wiki)

---

**Ready to boost your productivity with Claude Code's modular framework!**