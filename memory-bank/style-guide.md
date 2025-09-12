# Style Guide

## Code Style Standards

### TypeScript/JavaScript
- **File Extensions**: `.tsx` for React components, `.ts` for utilities
- **Import Style**: ES6 imports with clear dependency organization
- **Variable Naming**: camelCase for variables and functions
- **Component Naming**: PascalCase for React components
- **Constants**: UPPER_SNAKE_CASE for constants

### React Patterns
- **Functional Components**: Prefer function components over class components
- **Hooks Usage**: Use React hooks for state and lifecycle management
- **Props Interface**: Define clear prop types (implicit through usage)
- **Event Handlers**: Use arrow functions for event handlers

### State Management
- **useState**: For local component state
- **useRef**: For DOM references and mutable values
- **Derived State**: Compute values from existing state rather than storing separately
- **State Updates**: Use functional updates for state that depends on previous state

## UI/UX Guidelines

### Layout Principles
- **Responsive Design**: Mobile-first approach with adaptive layouts
- **Sidebar Pattern**: Collapsible navigation with clear state indicators
- **Split View**: Balanced video and results presentation
- **Progressive Disclosure**: Show relevant options based on user selections

### Color & Theming
- **Theme Detection**: Automatic light/dark mode based on system preferences
- **CSS Custom Properties**: Use for consistent theming
- **Semantic Colors**: Meaningful color usage for states and actions

### Interactive Elements
- **Button States**: Clear active, hover, and disabled states
- **Loading Indicators**: Visual feedback for async operations
- **Error States**: Clear error messaging and recovery options
- **Accessibility**: Proper ARIA labels and keyboard navigation

## File Organization

### Component Structure
```
Component.tsx
├── Imports (external libraries first, then local)
├── Type definitions (if needed)
├── Main component function
├── Helper functions (if any)
└── Export statement
```

### Utility Functions
- **Single Responsibility**: Each function should have one clear purpose
- **Pure Functions**: Prefer pure functions when possible
- **Error Handling**: Consistent error handling patterns
- **Documentation**: Clear function names that explain purpose

## Naming Conventions

### Files & Directories
- **Components**: PascalCase (e.g., `VideoPlayer.tsx`)
- **Utilities**: camelCase (e.g., `utils.ts`)
- **Configuration**: lowercase with extensions (e.g., `vite.config.ts`)

### Variables & Functions
- **State Variables**: Descriptive names (e.g., `isLoading`, `videoError`)
- **Event Handlers**: Prefix with `on` or `handle` (e.g., `onModeSelect`)
- **Boolean Variables**: Use `is`, `has`, `can` prefixes
- **Constants**: Descriptive and UPPER_CASE

## CSS Guidelines

### Class Naming
- **Utility Classes**: Use classnames library for conditional classes
- **Component Classes**: Match component names
- **State Classes**: Clear state indicators (e.g., `active`, `loading`)

### Responsive Design
- **Mobile First**: Design for mobile, enhance for desktop
- **Breakpoints**: Use consistent breakpoint values
- **Flexible Layouts**: Use flexbox and grid for responsive layouts

## Performance Best Practices

### React Optimization
- **Avoid Unnecessary Re-renders**: Proper dependency arrays
- **Component Memoization**: Use React.memo when appropriate
- **State Structure**: Keep state flat and normalized

### Asset Management
- **Image Optimization**: Appropriate formats and sizes
- **Code Splitting**: Split large components when beneficial
- **Bundle Size**: Monitor and optimize bundle size

## Error Handling Standards

### User-Facing Errors
- **Clear Messages**: User-friendly error descriptions
- **Recovery Actions**: Provide clear next steps
- **Visual Indicators**: Obvious error states

### Development Errors
- **Console Logging**: Meaningful development logs
- **Error Boundaries**: Proper error containment
- **Debugging**: Clear debugging information
