# Component Template

<instructions>
  <context>
    Template for creating consistent, reusable components following project patterns and best practices. Includes TypeScript support, accessibility features, and comprehensive testing setup.
  </context>
  
  <requirements>
    - Component library framework configured
    - TypeScript and type definitions available
    - Testing framework with component testing support
    - Styling system or CSS framework integrated
  </requirements>
  
  <template>
    ## Component Structure
    
    ```typescript
    // [ComponentName]/[ComponentName].tsx
    import React from 'react';
    import { [ComponentName]Props } from './[ComponentName].types';
    import { [ComponentName]Styles } from './[ComponentName].styles';
    
    export const [ComponentName]: React.FC<[ComponentName]Props> = ({
      // Destructure props with defaults
      children,
      className = '',
      variant = 'default',
      disabled = false,
      ...props
    }) => {
      // Component logic here
      
      return (
        <div
          className={`${[ComponentName]Styles.container} ${[ComponentName]Styles[variant]} ${className}`}
          {...props}
        >
          {children}
        </div>
      );
    };
    
    [ComponentName].displayName = '[ComponentName]';
    ```
    
    ## Type Definitions
    
    ```typescript
    // [ComponentName]/[ComponentName].types.ts
    export interface [ComponentName]Props {
      children?: React.ReactNode;
      className?: string;
      variant?: 'default' | 'primary' | 'secondary';
      disabled?: boolean;
    }
    ```
    
    ## Styles
    
    ```typescript
    // [ComponentName]/[ComponentName].styles.ts
    export const [ComponentName]Styles = {
      container: 'component-[component-name]',
      default: 'component-[component-name]--default',
      primary: 'component-[component-name]--primary',
      secondary: 'component-[component-name]--secondary',
      disabled: 'component-[component-name]--disabled'
    };
    ```
    
    ## Tests
    
    ```typescript
    // [ComponentName]/[ComponentName].test.tsx
    import { render, screen } from '@testing-library/react';
    import userEvent from '@testing-library/user-event';
    import { [ComponentName] } from './[ComponentName]';
    
    describe('[ComponentName]', () => {
      it('renders correctly', () => {
        render(<[ComponentName]>Test Content</[ComponentName]>);
        expect(screen.getByText('Test Content')).toBeInTheDocument();
      });
      
      it('applies variant classes correctly', () => {
        render(<[ComponentName] variant="primary">Test</[ComponentName]>);
        expect(screen.getByText('Test')).toHaveClass('component-[component-name]--primary');
      });
      
      it('handles disabled state', () => {
        render(<[ComponentName] disabled>Test</[ComponentName]>);
        expect(screen.getByText('Test')).toHaveClass('component-[component-name]--disabled');
      });
    });
    ```
    
    ## Stories
    
    ```typescript
    // [ComponentName]/[ComponentName].stories.tsx
    import type { Meta, StoryObj } from '@storybook/react';
    import { [ComponentName] } from './[ComponentName]';
    
    const meta: Meta<typeof [ComponentName]> = {
      title: 'Components/[ComponentName]',
      component: [ComponentName],
      parameters: {
        layout: 'centered',
      },
      tags: ['autodocs'],
    };
    
    export default meta;
    type Story = StoryObj<typeof meta>;
    
    export const Default: Story = {
      args: {
        children: 'Default [ComponentName]',
      },
    };
    
    export const Primary: Story = {
      args: {
        variant: 'primary',
        children: 'Primary [ComponentName]',
      },
    };
    
    export const Disabled: Story = {
      args: {
        disabled: true,
        children: 'Disabled [ComponentName]',
      },
    };
    ```
    
    ## Index
    
    ```typescript
    // [ComponentName]/index.ts
    export { [ComponentName] } from './[ComponentName]';
    export type { [ComponentName]Props } from './[ComponentName].types';
    ```
  </template>
  
  <customization>
    ### Customization Options
    
    - **Framework:** React, Vue, Angular, etc.
    - **Styling:** CSS Modules, Styled Components, Tailwind
    - **Testing:** Jest, Vitest, Cypress
    - **Documentation:** Storybook, Docusaurus, GitBook
    - **Accessibility:** ARIA attributes, keyboard navigation
    - **Responsive:** Mobile-first, breakpoint handling
  </customization>
</instructions>