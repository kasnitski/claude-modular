# Configuration Guide

Comprehensive guide to configuring the Claude Code modular framework for your specific needs, environment, and team requirements.

## Configuration Architecture

### Layered Configuration System

The framework uses a hierarchical configuration system:

```
Base Configuration (settings.json)
├── Environment Overrides (development.json, staging.json, production.json)
└── Local Customizations (local.json) - gitignored
```

### Configuration Files

| File | Purpose | Version Control |
|------|---------|----------------|
| `settings.json` | Base configuration | ✅ Committed |
| `development.json` | Development overrides | ✅ Committed |
| `staging.json` | Staging overrides | ✅ Committed |
| `production.json` | Production overrides | ✅ Committed |
| `local.json` | User-specific settings | ❌ Gitignored |

## Base Configuration (`settings.json`)

### Core Settings

```json
{
  "framework": {
    "name": "claude-modular",
    "version": "1.0.0",
    "description": "Modular Claude Code Framework Template"
  },
  "defaults": {
    "max_tokens_per_session": 50000,
    "context_window_warning": 40000,
    "auto_clear_threshold": 45000,
    "progressive_disclosure": true,
    "xml_structured_commands": true
  }
}
```

### Token Management

```json
{
  "token_optimization": {
    "lazy_loading": true,
    "context_compression": true,
    "modular_instructions": true,
    "smart_context_switching": true
  }
}
```

### Security Settings

```json
{
  "security": {
    "require_env_vars": true,
    "audit_logging": true,
    "permission_validation": true,
    "secret_scanning": true
  }
}
```

### Quality Gates

```json
{
  "quality_gates": {
    "require_tests": true,
    "require_documentation": true,
    "require_type_checking": true,
    "require_security_scan": true
  }
}
```

## Environment-Specific Configuration

### Development Environment (`development.json`)

```json
{
  "extends": "./settings.json",
  "overrides": {
    "defaults": {
      "max_tokens_per_session": 100000,
      "context_window_warning": 80000,
      "auto_clear_threshold": 90000
    },
    "security": {
      "audit_logging": false,
      "permission_validation": false
    },
    "quality_gates": {
      "require_tests": false,
      "require_documentation": false,
      "require_type_checking": false,
      "require_security_scan": false
    },
    "workflows": {
      "auto_commit_formatting": true,
      "auto_generate_docs": false,
      "auto_run_tests": false,
      "quality_check_on_save": false
    },
    "debug": {
      "verbose_logging": true,
      "show_token_usage": true,
      "show_context_boundaries": true,
      "enable_experimental_features": true
    }
  }
}
```

### Staging Environment (`staging.json`)

```json
{
  "extends": "./settings.json",
  "overrides": {
    "security": {
      "audit_logging": true,
      "permission_validation": true,
      "secret_scanning": true,
      "require_approval": ["deployment", "external_api"]
    },
    "quality_gates": {
      "require_tests": true,
      "require_documentation": true,
      "require_type_checking": true,
      "require_security_scan": true,
      "require_performance_tests": true
    },
    "workflows": {
      "auto_commit_formatting": false,
      "auto_generate_docs": true,
      "auto_run_tests": true,
      "quality_check_on_save": true,
      "require_review": true
    },
    "staging": {
      "deployment_checks": true,
      "rollback_enabled": true,
      "monitoring_enabled": true
    }
  }
}
```

### Production Environment (`production.json`)

```json
{
  "extends": "./settings.json",
  "overrides": {
    "security": {
      "audit_logging": true,
      "permission_validation": true,
      "secret_scanning": true,
      "require_approval": ["deployment", "external_api", "database", "infrastructure"],
      "multi_factor_required": true
    },
    "quality_gates": {
      "require_tests": true,
      "require_documentation": true,
      "require_type_checking": true,
      "require_security_scan": true,
      "require_performance_tests": true,
      "require_load_tests": true,
      "require_code_review": true
    },
    "production": {
      "deployment_window": "business_hours",
      "rollback_enabled": true,
      "monitoring_enabled": true,
      "alerting_enabled": true,
      "backup_required": true,
      "canary_deployment": true
    },
    "restrictions": {
      "no_direct_commits": true,
      "require_pr": true,
      "require_approvals": 2,
      "block_force_push": true
    }
  }
}
```

## MCP Server Integration

### Memory Server Configuration

```json
{
  "integrations": {
    "mcp_servers": {
      "memory": {
        "enabled": true,
        "auto_context_save": true,
        "session_persistence": true,
        "entity_tracking": true,
        "relationship_mapping": true
      }
    }
  }
}
```

### Git Server Configuration

```json
{
  "integrations": {
    "mcp_servers": {
      "git": {
        "enabled": true,
        "auto_commit_templates": true,
        "semantic_commits": true,
        "pre_commit_hooks": true,
        "branch_protection": true
      }
    }
  }
}
```

### External Tools Configuration

```json
{
  "integrations": {
    "external_tools": {
      "linear": {
        "enabled": false,
        "auto_link_issues": true,
        "project_id": "${LINEAR_PROJECT_ID}",
        "api_key": "${LINEAR_API_KEY}"
      },
      "notion": {
        "enabled": false,
        "auto_doc_sync": true,
        "database_id": "${NOTION_DATABASE_ID}",
        "api_key": "${NOTION_API_KEY}"
      }
    }
  }
}
```

## Command Configuration

### Command Categories

```json
{
  "commands": {
    "categories": {
      "project": {
        "enabled": true,
        "auto_scaffolding": true,
        "template_validation": true
      },
      "development": {
        "enabled": true,
        "auto_code_review": true,
        "refactor_suggestions": true
      },
      "testing": {
        "enabled": true,
        "auto_test_generation": true,
        "coverage_enforcement": true
      },
      "deployment": {
        "enabled": true,
        "auto_quality_gates": true,
        "rollback_protection": true
      },
      "documentation": {
        "enabled": true,
        "auto_api_docs": true,
        "version_tracking": true
      }
    }
  }
}
```

### Command Permissions

```json
{
  "permissions": {
    "project": {
      "create-feature": ["developer", "lead"],
      "scaffold-component": ["developer", "lead"],
      "setup-environment": ["developer", "lead", "admin"]
    },
    "deployment": {
      "deploy-staging": ["lead", "admin"],
      "deploy-production": ["admin"],
      "rollback-procedure": ["lead", "admin"]
    }
  }
}
```

## Workflow Configuration

### Automated Workflows

```json
{
  "workflows": {
    "feature_development": {
      "auto_branch_creation": true,
      "auto_test_generation": true,
      "auto_documentation": true,
      "quality_gates": ["lint", "test", "security"]
    },
    "code_review": {
      "auto_analysis": true,
      "security_scanning": true,
      "performance_checking": true,
      "coverage_validation": true
    },
    "deployment": {
      "auto_quality_check": true,
      "staging_validation": true,
      "production_approval": true,
      "rollback_preparation": true
    }
  }
}
```

### Notification Configuration

```json
{
  "notifications": {
    "channels": {
      "email": {
        "enabled": true,
        "smtp_host": "${SMTP_HOST}",
        "smtp_port": "${SMTP_PORT}",
        "smtp_user": "${SMTP_USER}",
        "smtp_pass": "${SMTP_PASS}"
      },
      "slack": {
        "enabled": false,
        "webhook_url": "${SLACK_WEBHOOK_URL}",
        "channel": "#development"
      },
      "teams": {
        "enabled": false,
        "webhook_url": "${TEAMS_WEBHOOK_URL}"
      }
    }
  }
}
```

## Local Customization

### User-Specific Settings (`local.json`)

```json
{
  "user": {
    "name": "Your Name",
    "email": "your.email@example.com",
    "preferences": {
      "theme": "dark",
      "verbose_output": true,
      "auto_save": true
    }
  },
  "overrides": {
    "defaults": {
      "max_tokens_per_session": 75000
    },
    "debug": {
      "verbose_logging": false,
      "show_token_usage": false
    }
  }
}
```

## Environment Variables

### Required Variables

```bash
# Database
DATABASE_URL=postgresql://localhost/myapp

# API Keys
API_KEY=your-api-key-here
JWT_SECRET=your-jwt-secret

# External Services
LINEAR_API_KEY=your-linear-key
NOTION_API_KEY=your-notion-key

# Email Configuration
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your-email@gmail.com
SMTP_PASS=your-app-password
```

### Optional Variables

```bash
# Monitoring
SENTRY_DSN=your-sentry-dsn
NEW_RELIC_LICENSE_KEY=your-newrelic-key

# CI/CD
GITHUB_TOKEN=your-github-token
DOCKER_REGISTRY=your-registry-url

# Feature Flags
FEATURE_FLAG_API_KEY=your-feature-flag-key
```

## Validation and Testing

### Configuration Validation

```bash
# Validate configuration syntax
/config:validate

# Test configuration loading
/config:test

# Check environment variables
/config:check-env
```

### Environment Testing

```bash
# Test development environment
NODE_ENV=development /config:test

# Test staging environment
NODE_ENV=staging /config:test

# Test production environment
NODE_ENV=production /config:test
```

## Migration and Upgrades

### Version Migration

```bash
# Check for configuration updates
/config:check-updates

# Migrate to new version
/config:migrate --version=1.1.0

# Backup current configuration
/config:backup
```

### Breaking Changes

When upgrading, check for breaking changes:

1. **Review changelog** for configuration changes
2. **Backup current configuration** before upgrading
3. **Test in development** environment first
4. **Validate all commands** work correctly
5. **Update team documentation** if needed

## Best Practices

### Configuration Management

1. **Use environment variables** for sensitive data
2. **Version control** all configuration files except `local.json`
3. **Document custom settings** in team documentation
4. **Validate configurations** before deployment
5. **Test across environments** regularly

### Security

1. **Never commit secrets** to version control
2. **Use different secrets** for each environment
3. **Rotate secrets** regularly
4. **Audit configuration changes** in production
5. **Implement least privilege** access

### Performance

1. **Monitor token usage** and adjust limits
2. **Use progressive disclosure** for large projects
3. **Optimize command loading** for frequently used commands
4. **Cache configuration** for faster startup
5. **Profile performance** regularly

## Troubleshooting

### Common Configuration Issues

**Issue**: Configuration not loading
**Solution**: Check JSON syntax and file permissions

**Issue**: Environment variables not found
**Solution**: Verify .env file location and syntax

**Issue**: Commands not working
**Solution**: Check command permissions and category enablement

**Issue**: Token limits exceeded
**Solution**: Adjust token limits in configuration

### Debug Commands

```bash
# Show current configuration
/config:show

# Debug configuration loading
/config:debug

# Validate all settings
/config:validate --verbose
```

---

**Proper configuration is key to maximizing the benefits of the Claude Code modular framework.**