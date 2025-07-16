# Test Template

<instructions>
  <context>
    Comprehensive test template covering unit, integration, and end-to-end testing patterns. Includes common testing scenarios, mocking strategies, and best practices for maintainable test suites.
  </context>
  
  <requirements>
    - Testing framework configured (Jest, Vitest, Mocha, etc.)
    - Mocking library available (jest.mock, sinon, etc.)
    - Test utilities and helpers set up
    - Coverage reporting configured
  </requirements>
  
  <template>
    ## Unit Test Structure
    
    ```typescript
    // [ModuleName].test.ts
    import { [ModuleName] } from './[ModuleName]';
    import { mockDependency } from '../__mocks__/mockDependency';
    
    // Mock external dependencies
    jest.mock('../dependency', () => ({
      dependency: mockDependency
    }));
    
    describe('[ModuleName]', () => {
      beforeEach(() => {
        // Setup before each test
        jest.clearAllMocks();
      });
      
      afterEach(() => {
        // Cleanup after each test
        jest.resetAllMocks();
      });
      
      describe('happy path scenarios', () => {
        it('should handle valid input correctly', () => {
          // Arrange
          const input = { valid: 'data' };
          const expected = { processed: 'data' };
          
          // Act
          const result = [ModuleName].process(input);
          
          // Assert
          expect(result).toEqual(expected);
        });
      });
      
      describe('error scenarios', () => {
        it('should handle invalid input gracefully', () => {
          // Arrange
          const invalidInput = null;
          
          // Act & Assert
          expect(() => [ModuleName].process(invalidInput))
            .toThrow('Invalid input provided');
        });
      });
      
      describe('edge cases', () => {
        it('should handle empty input', () => {
          // Arrange
          const emptyInput = {};
          
          // Act
          const result = [ModuleName].process(emptyInput);
          
          // Assert
          expect(result).toEqual({});
        });
      });
    });
    ```
    
    ## Integration Test Structure
    
    ```typescript
    // [ModuleName].integration.test.ts
    import { setupTestDatabase } from '../utils/testDatabase';
    import { [ModuleName] } from './[ModuleName]';
    
    describe('[ModuleName] Integration Tests', () => {
      let testDb: any;
      
      beforeAll(async () => {
        // Setup test database
        testDb = await setupTestDatabase();
      });
      
      afterAll(async () => {
        // Cleanup test database
        await testDb.cleanup();
      });
      
      beforeEach(async () => {
        // Reset database state
        await testDb.reset();
      });
      
      it('should integrate with database correctly', async () => {
        // Arrange
        const testData = { name: 'test', value: 'data' };
        
        // Act
        const result = await [ModuleName].save(testData);
        
        // Assert
        expect(result.id).toBeDefined();
        
        const savedData = await testDb.findById(result.id);
        expect(savedData.name).toBe(testData.name);
      });
      
      it('should handle database errors gracefully', async () => {
        // Arrange
        const invalidData = { /* invalid structure */ };
        
        // Act & Assert
        await expect([ModuleName].save(invalidData))
          .rejects.toThrow('Database validation error');
      });
    });
    ```
    
    ## Component Test Structure
    
    ```typescript
    // [ComponentName].test.tsx
    import { render, screen, fireEvent, waitFor } from '@testing-library/react';
    import userEvent from '@testing-library/user-event';
    import { [ComponentName] } from './[ComponentName]';
    
    // Mock external dependencies
    jest.mock('../hooks/useApi', () => ({
      useApi: () => ({
        data: mockData,
        loading: false,
        error: null
      })
    }));
    
    describe('[ComponentName]', () => {
      const defaultProps = {
        title: 'Test Title',
        onAction: jest.fn()
      };
      
      beforeEach(() => {
        jest.clearAllMocks();
      });
      
      it('renders correctly', () => {
        render(<[ComponentName] {...defaultProps} />);
        
        expect(screen.getByText('Test Title')).toBeInTheDocument();
        expect(screen.getByRole('button')).toBeInTheDocument();
      });
      
      it('handles user interactions', async () => {
        const user = userEvent.setup();
        render(<[ComponentName] {...defaultProps} />);
        
        const button = screen.getByRole('button');
        await user.click(button);
        
        expect(defaultProps.onAction).toHaveBeenCalledTimes(1);
      });
      
      it('handles loading states', () => {
        // Mock loading state
        jest.mocked(useApi).mockReturnValue({
          data: null,
          loading: true,
          error: null
        });
        
        render(<[ComponentName] {...defaultProps} />);
        
        expect(screen.getByText('Loading...')).toBeInTheDocument();
      });
      
      it('handles error states', () => {
        // Mock error state
        jest.mocked(useApi).mockReturnValue({
          data: null,
          loading: false,
          error: 'Test error'
        });
        
        render(<[ComponentName] {...defaultProps} />);
        
        expect(screen.getByText('Error: Test error')).toBeInTheDocument();
      });
    });
    ```
    
    ## E2E Test Structure
    
    ```typescript
    // [Feature].e2e.test.ts
    import { test, expect } from '@playwright/test';
    
    test.describe('[Feature] E2E Tests', () => {
      test.beforeEach(async ({ page }) => {
        // Setup test environment
        await page.goto('/test-page');
      });
      
      test('should complete user workflow', async ({ page }) => {
        // Step 1: Navigate to feature
        await page.click('[data-testid="feature-button"]');
        
        // Step 2: Fill form
        await page.fill('[data-testid="input-field"]', 'test value');
        
        // Step 3: Submit
        await page.click('[data-testid="submit-button"]');
        
        // Step 4: Verify result
        await expect(page.locator('[data-testid="success-message"]'))
          .toHaveText('Operation completed successfully');
      });
      
      test('should handle validation errors', async ({ page }) => {
        // Submit without required fields
        await page.click('[data-testid="submit-button"]');
        
        // Check for error message
        await expect(page.locator('[data-testid="error-message"]'))
          .toBeVisible();
      });
    });
    ```
    
    ## Mock Template
    
    ```typescript
    // __mocks__/[ModuleName].ts
    export const mock[ModuleName] = {
      process: jest.fn(),
      save: jest.fn(),
      load: jest.fn(),
      delete: jest.fn()
    };
    
    export const mockData = {
      id: '123',
      name: 'Test Item',
      value: 'Test Value',
      createdAt: new Date('2023-01-01'),
      updatedAt: new Date('2023-01-01')
    };
    
    export const mockError = new Error('Test error message');
    ```
  </template>
  
  <patterns>
    ### Common Testing Patterns
    
    - **AAA Pattern:** Arrange, Act, Assert
    - **Given-When-Then:** BDD-style test structure
    - **Red-Green-Refactor:** TDD development cycle
    - **Test Doubles:** Mocks, stubs, spies, fakes
    - **Test Data Builders:** Factory patterns for test data
    - **Page Object Model:** E2E test organization
  </patterns>
</instructions>