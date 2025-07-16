# Contributing to Claude Code Modular Framework

Thank you for your interest in contributing to the Claude Code Modular Framework! This document provides guidelines for contributing to this project.

## 🤝 How to Contribute

### Types of Contributions

We welcome several types of contributions:

- **New Commands** - Add new slash commands to the framework
- **Command Improvements** - Enhance existing commands with better functionality
- **Documentation** - Improve documentation, examples, and guides
- **Bug Fixes** - Fix issues with existing commands or configuration
- **Templates** - Create new templates for common use cases
- **Examples** - Add real-world usage examples
- **Configuration** - Improve configuration options and patterns

## 📋 Getting Started

### Prerequisites

- **Claude Code** installed and configured
- **Git** for version control
- **Node.js** (for running validation scripts)
- **Basic understanding** of the framework structure

### Development Setup

1. **Fork the repository:**
   ```bash
   git clone https://github.com/your-username/claude-modular.git
   cd claude-modular
   ```

2. **Create a feature branch:**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Make your changes** following the guidelines below

4. **Test your changes** with the validation scripts

5. **Submit a pull request**

## 🏗️ Command Development Guidelines

### Command Structure

All commands must follow the XML-structured format:

```xml
<instructions>
  <context>
    Brief description of when and why to use this command
  </context>
  
  <requirements>
    - Specific prerequisites and dependencies
    - Required file structures or tools
    - Environment setup needs
  </requirements>
  
  <execution>
    Step-by-step implementation with verification points
  </execution>
  
  <validation>
    Quality checks and acceptance criteria
  </validation>
  
  <examples>
    Concrete usage examples with expected outputs
  </examples>
</instructions>
```

### Command Categories

Commands are organized into these categories:

- **project/** - Project management and scaffolding
- **development/** - Development workflow and code quality
- **testing/** - Test generation and validation
- **deployment/** - Deployment and operations
- **documentation/** - Documentation generation and maintenance

### Naming Conventions

- **File names**: Use kebab-case (e.g., `create-feature.md`)
- **Command names**: Use descriptive names (e.g., `/project:create-feature`)
- **Categories**: Use singular nouns (e.g., `project`, not `projects`)

### Command Requirements

Each command must include:

1. **Clear context** - When and why to use the command
2. **Prerequisites** - What needs to be set up first
3. **Step-by-step execution** - Detailed implementation steps
4. **Validation criteria** - How to verify success
5. **Realistic examples** - Working examples with expected outputs
6. **Error handling** - Common issues and solutions

## 📝 Documentation Guidelines

### Writing Style

- **Clear and concise** - Avoid unnecessary complexity
- **Action-oriented** - Use imperative voice
- **Consistent terminology** - Use the same terms throughout
- **Inclusive language** - Avoid assumptions about reader background

### Documentation Structure

- **Overview** - Brief description of purpose
- **Prerequisites** - What readers need to know/have
- **Step-by-step instructions** - Clear, numbered steps
- **Examples** - Real-world usage scenarios
- **Troubleshooting** - Common issues and solutions

### Code Examples

- **Working examples** - Test all code examples
- **Multiple scenarios** - Show different use cases
- **Expected outputs** - Show what users should see
- **Error cases** - Include error handling examples

## 🧪 Testing Guidelines

### Command Testing

Before submitting a command, test it with:

1. **Fresh environment** - Test on clean setup
2. **Multiple scenarios** - Test different use cases
3. **Error conditions** - Test failure scenarios
4. **Different environments** - Test dev, staging, production configs

### Validation Checklist

- [ ] Command follows XML structure
- [ ] All examples work as documented
- [ ] Prerequisites are clearly stated
- [ ] Validation criteria are testable
- [ ] Error handling is comprehensive
- [ ] Documentation is clear and complete

## 🔧 Configuration Guidelines

### Configuration Changes

When adding configuration options:

1. **Base configuration** - Add to `settings.json`
2. **Environment overrides** - Consider dev/staging/prod needs
3. **Validation** - Ensure configuration is validated
4. **Documentation** - Update configuration guide
5. **Migration** - Consider existing installations

### Security Considerations

- **No secrets** - Never include actual secrets in examples
- **Environment variables** - Use env vars for sensitive data
- **Permission checks** - Validate user permissions
- **Audit logging** - Log security-relevant actions

## 📊 Quality Standards

### Code Quality

- **Consistent formatting** - Follow project style
- **Clear comments** - Explain complex logic
- **Error handling** - Handle edge cases gracefully
- **Performance** - Consider token usage and efficiency

### Documentation Quality

- **Comprehensive** - Cover all aspects of the feature
- **Accurate** - Ensure all information is correct
- **Up-to-date** - Keep documentation current
- **Accessible** - Make it easy to understand

## 🚀 Submission Process

### Pull Request Guidelines

1. **Descriptive title** - Clearly describe the change
2. **Detailed description** - Explain what and why
3. **Testing notes** - Describe how you tested
4. **Breaking changes** - Highlight any breaking changes
5. **Documentation updates** - Include doc updates

### Pull Request Template

```markdown
## Description
Brief description of the changes

## Type of Change
- [ ] New command
- [ ] Command improvement
- [ ] Bug fix
- [ ] Documentation update
- [ ] Configuration change

## Testing
- [ ] Tested in development environment
- [ ] Tested multiple scenarios
- [ ] Validated examples work
- [ ] Checked error handling

## Checklist
- [ ] Code follows project style guidelines
- [ ] Self-review completed
- [ ] Documentation updated
- [ ] Examples tested and working
- [ ] Breaking changes documented
```

### Review Process

1. **Automated checks** - CI/CD validation
2. **Code review** - Maintainer review
3. **Testing** - Community testing
4. **Documentation review** - Doc accuracy check
5. **Approval** - Final approval and merge

## 🐛 Bug Reports

### Bug Report Template

```markdown
## Bug Description
Clear description of the bug

## Steps to Reproduce
1. Step one
2. Step two
3. Step three

## Expected Behavior
What should happen

## Actual Behavior
What actually happens

## Environment
- Claude Code version:
- Operating system:
- Project type:
- Configuration:

## Additional Context
Any other relevant information
```

### Bug Triage Process

1. **Validation** - Confirm the bug exists
2. **Categorization** - Assign severity and priority
3. **Assignment** - Assign to appropriate maintainer
4. **Resolution** - Fix and test the bug
5. **Verification** - Confirm fix works

## 💡 Feature Requests

### Feature Request Template

```markdown
## Feature Description
Clear description of the proposed feature

## Problem Statement
What problem does this solve?

## Proposed Solution
How should this feature work?

## Alternatives Considered
What other approaches were considered?

## Implementation Ideas
Any thoughts on implementation?
```

### Feature Evaluation Process

1. **Community discussion** - Gather feedback
2. **Feasibility assessment** - Technical evaluation
3. **Priority assignment** - Rank against other features
4. **Implementation planning** - Design and timeline
5. **Development** - Implementation and testing

## 🏆 Recognition

### Contributor Recognition

Contributors are recognized through:

- **GitHub contributions** - Visible in repository
- **Release notes** - Mentioned in changelog
- **Documentation** - Listed in contributors section
- **Community highlights** - Featured in discussions

### Becoming a Maintainer

Active contributors may be invited to become maintainers based on:

- **Consistent contributions** - Regular, quality contributions
- **Community involvement** - Helping other contributors
- **Technical expertise** - Deep understanding of the framework
- **Leadership** - Guiding project direction

## 📞 Getting Help

### Support Channels

- **GitHub Issues** - Bug reports and feature requests
- **GitHub Discussions** - General questions and ideas
- **Documentation** - Comprehensive guides and examples
- **Community** - Connect with other contributors

### Maintainer Contact

- **Technical questions** - Use GitHub discussions
- **Security issues** - Email security@example.com
- **Project governance** - Use GitHub issues

## 📄 License

By contributing to this project, you agree that your contributions will be licensed under the MIT License.

## 🙏 Thank You

Thank you for contributing to the Claude Code Modular Framework! Your contributions help make development more productive and enjoyable for everyone.

---

**Together, we're building the future of AI-assisted development.**