# System Patterns

## Architecture Patterns

### Component Architecture
- **Single Page Application (SPA)**: React-based with component composition
- **State Management**: React hooks (useState, useRef) for local state management
- **Props Drilling**: Direct prop passing for component communication

### Data Flow Patterns
- **Unidirectional Data Flow**: Parent-to-child prop passing
- **Event Bubbling**: Child-to-parent communication via callbacks
- **Async State Management**: Loading states and error handling for API calls

## API Integration Patterns

### Google Generative AI Integration
- **Function Calling**: Structured responses using predefined functions
- **File Upload**: Video file upload and processing workflow
- **Prompt Engineering**: Mode-based prompting with customization options

### Response Handling
- **Function Call Processing**: Dynamic function execution based on AI responses
- **Data Transformation**: Converting AI responses to application state
- **Error Recovery**: Graceful handling of API failures

## UI/UX Patterns

### Layout Patterns
- **Sidebar Navigation**: Collapsible mode selector with responsive behavior
- **Split View**: Video player and analysis results side-by-side
- **Responsive Design**: Adaptive layout for different screen sizes

### Interaction Patterns
- **Drag & Drop**: Video file upload interface
- **Click-to-Navigate**: Timecode clicking for video navigation
- **Progressive Disclosure**: Mode selection with sub-mode expansion

## State Management Patterns

### Local State
- **Controlled Components**: Form inputs with React state
- **Derived State**: Computed values based on primary state
- **Effect Management**: Side effects handling with proper cleanup

### Data Persistence
- **Session Storage**: Video URL and file references
- **Temporary State**: Analysis results during session
- **Configuration State**: User preferences and mode selections

## Error Handling Patterns
- **Boundary Conditions**: Video load error states
- **User Feedback**: Loading indicators and error messages
- **Graceful Degradation**: Fallback UI when features unavailable
