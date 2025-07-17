# Continue Implementation Command

<instructions>
  <context>
    Automated implementation continuation with progress tracking, testing, and deployment pipeline integration. Analyzes specs/progress.md and specs_map.md to understand current implementation status, continues development, tests with Playwright MCP, and creates pull requests automatically.
  </context>
  
  <requirements>
    - specs/ directory with specification files and specs_map.md
    - specs/progress.md for implementation tracking
    - Playwright MCP integration for frontend testing
    - Git repository with proper branch permissions and CI/CD setup
  </requirements>
  
  <execution>
    1. **Progress and Specification Analysis**
       - Read specs_map.md to identify primary specification file
       - Check for existing specs/progress.md file and parse current status
       - Analyze target specification for implementation requirements
       - Create progress file with initial status if missing
    
    2. **Implementation Planning**
       - Identify next implementation tasks from progress.md
       - Analyze dependencies and blockers for current milestone
       - Plan implementation sequence based on specification requirements
       - Validate development environment and tool availability
    
    3. **Code Implementation**
       - Continue implementation from last checkpoint in progress.md
       - Follow architectural guidelines from target specification
       - Implement features according to specification requirements
       - Apply proper error handling, validation, and best practices
    
    4. **Frontend Testing with Playwright MCP**
       - Use Playwright MCP tools for frontend component testing
       - Perform browser automation tests for new functionality
       - Validate user interactions and UI behavior
       - Capture screenshots and test evidence
    
    5. **Version Control and Deployment**
       - Create feature branch using git MCP integration
       - Commit implemented changes with descriptive messages
       - Push changes to remote repository
       - Create pull request with implementation details
    
    6. **Documentation and Progress Updates**
       - Update target specification with changelog entry and date
       - Update specs/progress.md with completed tasks and status
       - Document any architectural decisions or issues encountered
       - Stop implementation and await pull request review
  </execution>
  
  <validation>
    - [ ] specs_map.md successfully identifies target specification
    - [ ] Implementation follows specification requirements
    - [ ] Playwright MCP tests pass for frontend functionality
    - [ ] Code quality standards maintained
    - [ ] Git branch created and changes committed
    - [ ] Pull request created successfully
    - [ ] Target specification updated with changelog
    - [ ] Progress tracking information complete
  </validation>
  
  <examples>
    ```bash
    # Continue implementation from current progress
    /project:continue-implementation
    
    # Expected actions:
    # - Read specs_map.md and specs/progress.md
    # - Continue from last checkpoint
    # - Test with Playwright MCP
    # - Create branch, commit, push, and PR
    ```
    
    ```bash
    # Continue implementation with specific focus
    /project:continue-implementation --focus=authentication
    
    # Focused continuation:
    # - Prioritize authentication features
    # - Test auth flows with Playwright
    # - Update specification changelog
    # - Create PR for auth implementation
    ```
    
    ```bash
    # Continue implementation with testing emphasis
    /project:continue-implementation --test-driven
    
    # Test-focused continuation:
    # - Implement with comprehensive testing
    # - Use Playwright MCP for all UI tests
    # - Validate all user interactions
    # - Ensure test coverage before PR
    ```
  </examples>
</instructions>