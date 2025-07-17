# Validate FSD Command

<instructions>
  <context>
    Feature-Sliced Design (FSD) 2.1 compliance validation with comprehensive architectural checks. Validates layer hierarchy, dependency rules, Public API patterns, and monorepo integration to ensure strict adherence to FSD principles.
  </context>
  
  <requirements>
    - FSD 2.1 project structure exists
    - Source code organized in layers (app, pages, widgets, features, entities, shared)
    - Public API files (index.ts) present in slices
    - Static analysis tools available (ESLint, TypeScript, etc.)
  </requirements>
  
  <execution>
    1. **Layer Structure Validation**
       - Verify correct layer hierarchy exists (app → pages → widgets → features → entities → shared)
       - Check for proper slice organization within each layer
       - Validate standard segments (ui, api, model, lib, config) usage
       - Confirm monorepo package structure alignment
    
    2. **Dependency Rule Enforcement**
       - Scan for forbidden same-level imports between slices
       - Check for upward imports (lower layers importing from higher)
       - Validate that all cross-layer imports respect hierarchy
       - Ensure shared layer doesn't import from FSD layers
    
    3. **Public API Pattern Compliance**
       - Verify all slices have index.ts files with proper exports
       - Check that imports use Public API (not deep imports)
       - Validate export naming conventions and completeness
       - Ensure re-exports don't bypass layer boundaries
    
    4. **Monorepo Integration Validation**
       - Check proper usage of monorepo packages (@acme/ui, @acme/api, etc.)
       - Validate app-specific code stays in app's FSD structure
       - Ensure no direct imports between apps
       - Verify shared packages are used for cross-app functionality
    
    5. **Code Organization Analysis**
       - Validate "Pages First" principle adherence
       - Check for premature abstraction to lower layers
       - Ensure components are placed in appropriate layers
       - Verify business logic distribution follows FSD guidelines
    
    6. **Compliance Reporting**
       - Generate detailed compliance report with violations
       - Provide specific fix recommendations for each issue
       - Create architectural health score and trends
       - Export results in multiple formats (JSON, HTML, markdown)
  </execution>
  
  <validation>
    - [ ] All layer dependencies respect FSD hierarchy
    - [ ] No same-level imports between slices exist
    - [ ] All slices have proper Public API exports
    - [ ] Monorepo packages used correctly
    - [ ] No bypassing of architectural boundaries
    - [ ] Standard segments used consistently
    - [ ] "Pages First" principle followed
    - [ ] Compliance report generated successfully
  </validation>
  
  <examples>
    ```bash
    # Basic FSD validation
    /project:validate-fsd
    
    # Expected output:
    # ✅ Layer hierarchy: PASSED
    # ✅ Dependency rules: PASSED  
    # ❌ Public API: 3 violations found
    # ✅ Monorepo integration: PASSED
    # 📊 Overall compliance: 85/100
    ```
    
    ```bash
    # Validation with detailed report
    /project:validate-fsd --verbose --output=report.html
    
    # Creates comprehensive report:
    # - Architectural diagram with violations
    # - Detailed violation descriptions
    # - Fix recommendations with code examples
    # - Compliance trends over time
    ```
    
    ```bash
    # Validation for specific layer
    /project:validate-fsd --layer=features --fix-suggestions
    
    # Focuses on features layer:
    # - Checks feature-specific compliance
    # - Provides automated fix suggestions
    # - Validates feature boundaries
    # - Ensures proper entity/shared usage
    ```
  </examples>
</instructions>