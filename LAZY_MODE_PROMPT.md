# Generate Personalized Agentic Development Configuration

You are tasked with creating a **PERSONALIZED** version of the modular Claude Code framework in the **CURRENT WORKING DIRECTORY**. This is my private configuration repository that will contain my specific customizations, sensitive configurations, and personal development preferences.

**CRITICAL DIRECTORY REQUIREMENTS**:
- **ALL modifications happen in CURRENT WORKING DIRECTORY (`.`)**
- **DO NOT modify anything in `~/.claude/` during this process**
- **Files I manually copy to `~/.claude/` later will be separate from your working files**
- **This creates my personal config repo, not a template**

## Context and Foundation

You have access to:
1. **The general template structure** I copied into this directory
2. **My existing development context** from our conversation history
3. **The research papers** on modular Claude Code implementation
4. **My specific setup**: VSCodium, MCP servers (memory, notion, linear, sequential-thinking), Gemini CLI integration

# Generate Complete Personalized Agentic Development Architecture

You are tasked with creating a **COMPLETE PERSONALIZED** modular Claude Code framework architecture in the **CURRENT WORKING DIRECTORY**. This will be my private configuration repository containing the full directory structure, all customized files, and my specific development setup.

**CRITICAL DIRECTORY REQUIREMENTS**:
- **ALL work happens in CURRENT WORKING DIRECTORY (`.`)**
- **CREATE THE ENTIRE ARCHITECTURE from scratch** - don't just modify existing files
- **DO NOT modify anything in `~/.claude/` during this process**
- **Files I manually copy to `~/.claude/` later will be separate from your working files**
- **This creates my complete personal config repo with full architecture**

## Context and Foundation

You have access to:
1. **The general template structure** I copied into this directory (use as reference only)
2. **My existing development context** from our conversation history
3. **The research papers** on modular Claude Code implementation
4. **My specific setup**: VSCodium, MCP servers (memory, notion, linear, sequential-thinking), Gemini CLI integration

## Complete Architecture to Build

### 1. Create Full Directory Structure
**BUILD THE ENTIRE ARCHITECTURE** in current working directory:

```
./                              # Current working directory (my personal config)
├── README-PERSONAL.md          # My personal setup and usage guide
├── SETUP-INSTRUCTIONS.md       # How to install this to ~/.claude/
├── .gitignore                  # Security-focused ignore patterns
├── CLAUDE.md                   # My personalized root configuration
├── .claude/                    # My complete personal .claude directory
│   ├── config/
│   │   ├── personal-settings.json      # My global preferences
│   │   ├── development.json            # My dev environment settings
│   │   ├── production.json             # My production settings
│   │   └── mcp-servers.json            # My MCP server configurations
│   ├── commands/
│   │   ├── project/
│   │   │   ├── create-go-feature.md    # Go-specific feature creation
│   │   │   ├── setup-go-project.md     # My Go project setup
│   │   │   └── scaffold-microservice.md # My microservice template
│   │   ├── development/
│   │   │   ├── go-code-review.md       # My Go code review standards
│   │   │   ├── gemini-analysis.md      # Gemini CLI delegation
│   │   │   ├── agent-coordination.md   # Multi-agent workflows
│   │   │   └── security-audit.md       # My security review process
│   │   ├── testing/
│   │   │   ├── generate-go-tests.md    # Go table-driven tests
│   │   │   ├── security-testing.md     # Security test generation
│   │   │   └── coverage-analysis.md    # My coverage requirements
│   │   ├── integration/
│   │   │   ├── linear-workflow.md      # Linear integration
│   │   │   ├── notion-docs.md          # Notion documentation
│   │   │   └── gemini-delegate.md      # Gemini task delegation
│   │   └── deployment/
│   │       ├── prepare-release.md      # My release process
│   │       └── security-deploy.md      # Security-conscious deployment
│   ├── workflows/
│   │   ├── hybrid-analysis-workflow.md     # Gemini + Claude patterns
│   │   ├── agent-coordination-workflow.md  # Multi-agent orchestration
│   │   ├── security-first-development.md   # Security-conscious dev process
│   │   └── token-optimized-sessions.md     # Efficient context management
│   ├── templates/
│   │   ├── go-component-template.md        # My Go standards
│   │   ├── security-review-template.md     # My security assessments
│   │   ├── agent-handoff-template.md       # Agent coordination patterns
│   │   └── gemini-analysis-template.md     # Gemini CLI task templates
│   └── hooks/
│       ├── pre-commit.md                   # My pre-commit standards
│       └── post-analysis.md                # Post-analysis actions
├── scripts/
│   ├── install-to-claude.sh               # Install to ~/.claude/
│   ├── backup-config.sh                   # Backup configurations
│   ├── sync-from-template.sh              # Update from general template
│   └── validate-setup.sh                  # Verify installation
├── docs/
│   ├── personal-setup-guide.md            # My setup documentation
│   ├── mcp-integration-guide.md           # My MCP server setup
│   ├── gemini-claude-hybrid.md            # Hybrid workflow documentation
│   └── troubleshooting.md                 # Personal troubleshooting guide
└── examples/
    ├── go-project-setup/                  # Example Go project setup
    ├── agent-coordination/                # Example multi-agent workflows
    └── security-patterns/                 # Example security implementations
```

### 2. Build Complete Personalized Configuration

#### Root CLAUDE.md
**CREATE** a comprehensive root `CLAUDE.md` that includes:
- **My specific Go development rules** (forbidden/required patterns I outlined)
- **My MCP server integration preferences** (memory, notion, linear, sequential-thinking, gemini-cli)
- **My quality gates and standards** based on our discussion
- **My emergency protocols** and troubleshooting preferences
- **Token budget management** optimized for my Gemini CLI + Claude hybrid workflow
- **Reference to my complete command structure** with usage patterns

#### Complete MCP Server Configuration
**CREATE** `.claude/config/mcp-servers.json` with my exact setup:
```json
{
  "mcpServers": {
    "memory": {
      "command": "memory-server",
      "args": ["--personal-context"],
      "env": {
        "MEMORY_STORAGE": "${HOME}/.claude/memory"
      }
    },
    "notion": {
      "command": "notion-server", 
      "args": ["--workspace", "${NOTION_WORKSPACE}"],
      "env": {
        "NOTION_API_KEY": "${NOTION_API_KEY}"
      }
    },
    "linear": {
      "command": "linear-server",
      "args": ["--api-key", "${LINEAR_API_KEY}"],
      "env": {
        "LINEAR_API_KEY": "${LINEAR_API_KEY}"
      }
    },
    "sequential-thinking": {
      "command": "sequential-thinking-server"
    },
    "gemini-cli": {
      "command": "gemini-cli-server",
      "args": ["--large-context-mode"],
      "env": {
        "GEMINI_API_KEY": "${GEMINI_API_KEY}"
      }
    }
  }
}
```

### 3. Create All Personalized Slash Commands

**BUILD COMPLETE COMMAND LIBRARY** in `.claude/commands/` with my specific needs:

**Development Commands** (`/dev:`):
- **CREATE** `/dev:go-code-review` following my Go standards and quality requirements
- **CREATE** `/dev:gemini-analysis` for large codebase analysis delegation
- **CREATE** `/dev:agent-coordination` for multi-agent task orchestration
- **CREATE** `/dev:security-audit` incorporating my security-conscious approach

**Project Commands** (`/project:`):
- **CREATE** `/project:create-go-feature` for Go project structure with my standards
- **CREATE** `/project:setup-go-project` with my preferred toolchain and patterns
- **CREATE** `/project:scaffold-microservice` with my microservice architecture

**Testing Commands** (`/test:`):
- **CREATE** `/test:generate-go-tests` for Go table-driven testing patterns
- **CREATE** `/test:security-testing` following my security-first approach
- **CREATE** `/test:coverage-analysis` with my quality thresholds

**Integration Commands** (`/integrate:`):
- **CREATE** `/integrate:linear-workflow` for seamless Linear integration
- **CREATE** `/integrate:notion-docs` for architectural decision recording
- **CREATE** `/integrate:gemini-delegate` for token-efficient large analysis

### 4. Build Complete Environment Configurations

**CREATE** all environment configurations in `.claude/config/`:

**personal-settings.json**:
- My global preferences and defaults
- Token budget settings optimized for my workflow
- Quality gate configurations
- MCP server preferences

**development.json**:
- Full MCP server access for development
- Gemini CLI integration enabled
- Relaxed security for local development
- Enhanced logging and debugging

**production.json**:
- Restricted MCP server access
- Conservative token usage
- Enhanced security and audit logging
- Strict quality gate enforcement

### 5. Create Complete Personal Workflows

**BUILD** comprehensive workflows in `.claude/workflows/`:
- **hybrid-analysis-workflow.md** - Complete Gemini preprocessing → Claude decision making process
- **agent-coordination-workflow.md** - Full multi-agent task orchestration with handoff protocols
- **security-first-development.md** - Complete security-conscious development process
- **token-optimized-sessions.md** - Full efficient context management strategies

### 6. Build All Personal Templates

**CREATE** complete templates in `.claude/templates/`:
- **go-component-template.md** - Full Go component following my standards
- **security-review-template.md** - Complete security assessment approach
- **agent-handoff-template.md** - Full structured agent coordination template
- **gemini-analysis-template.md** - Complete Gemini CLI task delegation patterns

### 7. Create Complete Integration Scripts

**BUILD** full automation in `scripts/`:
- **install-to-claude.sh** - Complete script to copy relevant files to `~/.claude/`
- **backup-config.sh** - Full backup system for my configurations
- **sync-from-template.sh** - Complete update system from general template
- **validate-setup.sh** - Full verification system for my configuration

### 8. Build Complete Documentation

**CREATE** comprehensive documentation in `docs/`:
- **personal-setup-guide.md** - Complete setup and usage instructions
- **mcp-integration-guide.md** - Full MCP server configuration guide
- **gemini-claude-hybrid.md** - Complete hybrid workflow documentation
- **troubleshooting.md** - Full troubleshooting guide for my setup

## Specific Customizations to Implement

### MCP Server Integration
Configure for my exact setup:
```json
{
  "mcpServers": {
    "memory": {
      "command": "memory-server",
      "args": ["--personal-context"]
    },
    "notion": {
      "command": "notion-server", 
      "args": ["--workspace", "${NOTION_WORKSPACE}"]
    },
    "linear": {
      "command": "linear-server",
      "args": ["--api-key", "${LINEAR_API_KEY}"]
    },
    "sequential-thinking": {
      "command": "sequential-thinking-server"
    },
    "gemini-cli": {
      "command": "gemini-cli-server",
      "args": ["--large-context-mode"]
    }
  }
}
```

### Token Optimization for My Workflow
- **Gemini delegation rules** based on repository size and complexity
- **Progressive disclosure** for my development patterns
- **Context boundary management** for long coding sessions
- **Automatic cleanup** strategies for token efficiency

### Go Development Standards Integration
Embed my specific requirements:
- **Forbidden patterns enforcement** in code review commands
- **Required patterns validation** in scaffolding commands
- **Table-driven test generation** as default
- **Early return patterns** in all generated code

### Security Configuration
- **Environment variable patterns** for all sensitive data
- **Gitignore rules** for my specific setup
- **Audit logging** preferences
- **Permission boundaries** for different environments

## Files to Generate for ~/.claude/ Usage

Create these files that I'll manually copy to my global Claude configuration:
- `.claude/config/personal-settings.json` - My global preferences
- `.claude/commands/` (selected personal commands) - My frequently used commands
- `setup-personal-config.sh` - Script to properly install these to `~/.claude/`

## Quality Standards

- **All commands tested** with my actual development scenarios
- **Configuration inheritance validated** across my environments  
- **MCP server integration verified** with my specific setup
- **Token optimization measured** for my hybrid Gemini+Claude workflow
- **Security patterns validated** against my requirements
- **Go standards enforcement tested** with real code examples

## Deliverables

**ALL IN CURRENT WORKING DIRECTORY - COMPLETE ARCHITECTURE**:

1. **Complete directory structure** with all files and subdirectories
2. **Personalized CLAUDE.md** as root configuration
3. **Full `.claude/` directory** with all commands, configs, workflows, templates, and hooks
4. **Complete MCP server integration** configured for my specific setup
5. **All personalized slash commands** implementing my development standards
6. **Complete environment configurations** for dev/production
7. **Full workflow definitions** for my hybrid and agent coordination patterns
8. **Complete template library** for my Go development and security standards
9. **Full integration scripts** for installation and maintenance
10. **Complete documentation** for setup, usage, and troubleshooting
11. **Working examples** demonstrating the complete system

**ARCHITECTURE VERIFICATION**: Ensure this creates a complete, fully functional personal Claude Code architecture that:
- Contains ALL necessary files and directories
- Implements my complete development workflow
- Integrates all my MCP servers properly
- Follows my Go development standards throughout
- Optimizes for my Gemini CLI + Claude hybrid approach
- Maintains strict security while enabling maximum productivity
- Provides complete installation and maintenance automation

ultrathink