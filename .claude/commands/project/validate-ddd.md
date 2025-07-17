# Validate DDD Command

<instructions>
  <context>
    Domain-Driven Design (DDD) and Clean Architecture compliance validation with comprehensive structural checks. Validates domain boundaries, dependency inversion, repository patterns, and service layer organization to ensure strict adherence to DDD principles.
  </context>
  
  <requirements>
    - DDD project structure exists with domains and features
    - Clean Architecture layers implemented (domains, features, infrastructure, shared)
    - Repository interfaces and implementations present
    - Dependency injection configuration available
  </requirements>
  
  <execution>
    1. **Domain Structure Validation**
       - Verify proper domain/feature separation and boundaries
       - Check for correct entity and value object implementation
       - Validate aggregate root patterns and business rules
       - Ensure domain services contain only domain logic
    
    2. **Clean Architecture Layer Compliance**
       - Scan dependency flow: controllers → services/use-cases → entities → repositories → infrastructure
       - Check for proper dependency inversion patterns
       - Validate that domain layer has no external dependencies
       - Ensure infrastructure implements domain interfaces
    
    3. **Repository Pattern Validation**
       - Verify repository interfaces exist in domain layer
       - Check implementations exist in infrastructure layer
       - Validate proper data access abstraction
       - Ensure domain entities don't leak to infrastructure
    
    4. **Business Logic Distribution**
       - Check domain services contain single-domain logic
       - Validate use-cases coordinate multiple domains properly
       - Ensure controllers are thin and delegate to services
       - Verify business rules are not in infrastructure layer
    
    5. **Cross-Domain Interaction Analysis**
       - Validate proper feature-to-domain dependencies
       - Check for forbidden domain-to-domain direct coupling
       - Ensure shared kernel usage follows DDD principles
       - Verify bounded context integrity
    
    6. **Architecture Health Reporting**
       - Generate domain model visualization and health metrics
       - Provide detailed violation reports with fix recommendations
       - Create dependency graph analysis and circular dependency detection
       - Export architectural compliance scores and improvement suggestions
  </execution>
  
  <validation>
    - [ ] Domain boundaries properly isolated
    - [ ] Dependency inversion correctly implemented
    - [ ] Repository pattern follows DDD guidelines
    - [ ] Business logic resides in appropriate layers
    - [ ] No domain-to-infrastructure dependencies
    - [ ] Use-cases properly coordinate domains
    - [ ] Entity and aggregate patterns correct
    - [ ] Cross-domain interactions validated
  </validation>
  
  <examples>
    ```bash
    # Basic DDD validation
    /project:validate-ddd
    
    # Expected output:
    # ✅ Domain boundaries: PASSED
    # ✅ Repository pattern: PASSED
    # ❌ Dependency inversion: 2 violations found
    # ✅ Business logic distribution: PASSED
    # 📊 Overall DDD compliance: 88/100
    ```
    
    ```bash
    # Validation with architecture diagram
    /project:validate-ddd --diagram --output=architecture-report.html
    
    # Creates comprehensive analysis:
    # - Domain model visualization
    # - Dependency flow diagrams
    # - Violation details with code examples
    # - Refactoring recommendations
    ```
    
    ```bash
    # Validation for specific domain
    /project:validate-ddd --domain=user --check-aggregates
    
    # Focuses on user domain:
    # - Validates user aggregate boundaries
    # - Checks domain service responsibilities
    # - Ensures proper repository implementation
    # - Validates cross-domain interactions
    ```
  </examples>
</instructions>