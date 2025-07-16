# Basic Setup Example

This example demonstrates how to set up the Claude Code modular framework for a simple web application project.

## Project Structure

```
my-web-app/
├── .claude/                    # Framework configuration
│   ├── config/
│   │   ├── settings.json
│   │   ├── development.json
│   │   └── production.json
│   └── commands/              # Command library
├── src/                       # Application source code
├── tests/                     # Test files
├── docs/                      # Documentation
├── .env.example              # Environment template
├── CLAUDE.md                 # Project configuration
└── package.json              # Dependencies
```

## Setup Steps

### 1. Copy Framework Files

```bash
# Copy the framework to your project
cp -r /path/to/claude-modular/.claude ./
cp /path/to/claude-modular/templates/CLAUDE.md.template ./CLAUDE.md
```

### 2. Customize CLAUDE.md

Edit the `CLAUDE.md` file for your project:

```markdown
# CLAUDE.md

## Project Overview

**Project Name:** My Web App
**Technology Stack:** React, Node.js, PostgreSQL
**Architecture:** Full-stack web application

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
- **Frontend**: React components in `src/components/`
- **Backend**: Express API in `src/api/`
- **Database**: PostgreSQL with Prisma ORM

### Security Considerations
- JWT authentication
- Input validation with Joi
- CORS configuration
- Environment variable management
```

### 3. Configure Environment

Create environment files:

```bash
# .env.example
DATABASE_URL=postgresql://localhost/myapp
JWT_SECRET=your-jwt-secret-here
PORT=3000
NODE_ENV=development
```

```bash
# Copy example to actual .env
cp .env.example .env
# Edit .env with your actual values
```

### 4. Update Configuration

Edit `.claude/config/settings.json`:

```json
{
  "framework": {
    "name": "my-web-app",
    "version": "1.0.0",
    "description": "Simple web application with React and Node.js"
  },
  "defaults": {
    "max_tokens_per_session": 50000,
    "progressive_disclosure": true
  },
  "quality_gates": {
    "require_tests": true,
    "require_documentation": true,
    "require_type_checking": true
  }
}
```

## Usage Examples

### Feature Development

```bash
# Create a new feature
/project:create-feature user-profile

# This creates:
# - src/components/UserProfile/
# - src/api/routes/user-profile.js
# - tests/user-profile.test.js
# - docs/user-profile.md
```

### Code Review

```bash
# Review current changes
/dev:code-review

# Output:
# ✅ Code Quality: Follows React best practices
# ✅ Security: No security issues found
# ⚠️  Performance: Consider lazy loading for large components
# ✅ Tests: Coverage at 85%
```

### Testing

```bash
# Generate comprehensive tests
/test:generate-tests

# Analyze test coverage
/test:coverage-analysis

# Run integration tests
/test:integration-tests
```

### Deployment

```bash
# Prepare for release
/deploy:prepare-release --type=minor

# Deploy to staging
/deploy:deploy-staging

# If everything looks good, deploy to production
/deploy:deploy-production
```

## Team Workflow

### Daily Development

1. **Start with environment check:**
   ```bash
   /project:setup-environment
   ```

2. **Create feature branch:**
   ```bash
   git checkout -b feature/new-feature
   ```

3. **Develop feature:**
   ```bash
   /project:create-feature new-feature
   ```

4. **Review before commit:**
   ```bash
   /dev:code-review
   ```

5. **Commit and push:**
   ```bash
   git add .
   git commit -m "feat: add new feature"
   git push origin feature/new-feature
   ```

### Weekly Tasks

1. **Update documentation:**
   ```bash
   /docs:update-readme
   /docs:api-docs
   ```

2. **Architecture review:**
   ```bash
   /docs:architecture-review
   ```

3. **Security scan:**
   ```bash
   /dev:code-review --focus=security
   ```

## Customization Tips

### Adding Custom Commands

1. Create command file:
   ```bash
   touch .claude/commands/project/custom-command.md
   ```

2. Follow the XML structure:
   ```xml
   <instructions>
     <context>Your custom command description</context>
     <requirements>Prerequisites</requirements>
     <execution>Implementation steps</execution>
     <validation>Success criteria</validation>
     <examples>Usage examples</examples>
   </instructions>
   ```

### Environment-Specific Settings

Customize for your deployment environments:

```json
// .claude/config/development.json
{
  "extends": "./settings.json",
  "overrides": {
    "defaults": {
      "max_tokens_per_session": 75000
    },
    "debug": {
      "verbose_logging": true
    }
  }
}
```

## Troubleshooting

### Common Issues

**Issue**: Commands not found
**Solution**: Check `.claude/commands/` directory exists

**Issue**: Configuration not loading
**Solution**: Validate JSON syntax in config files

**Issue**: Environment variables not found
**Solution**: Ensure `.env` file exists and has correct values

### Debug Commands

```bash
# Debug current session
/dev:debug-session

# Check configuration
/config:validate

# Test environment
/project:setup-environment --test
```

## Next Steps

1. **Explore advanced features** - Try integration with MCP servers
2. **Set up CI/CD** - Integrate with GitHub Actions
3. **Team training** - Share this setup with your team
4. **Monitoring** - Add application monitoring and logging
5. **Documentation** - Keep your docs updated as the project grows

---

**This basic setup provides a solid foundation for productive development with Claude Code.**