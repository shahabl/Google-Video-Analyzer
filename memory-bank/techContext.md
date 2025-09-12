# Technical Context

## Technology Stack

### Core Framework
- **React 19**: Latest React version with modern features
- **TypeScript**: Type safety and developer experience (configured via tsconfig.json)
- **Vite**: Fast build tool and development server

### AI & API Integration
- **@google/generative-ai (v0.24.0)**: Primary AI integration
- **@google/genai (v0.7.0)**: Additional Google AI utilities
- **Function Calling**: Structured AI responses with predefined functions

### Data Visualization
- **D3.js Components**:
  - `d3-array (v3.2.4)`: Data manipulation and statistics
  - `d3-shape (v3.2.0)`: Shape generators for charts
  - `d3-scale (v4.0.2)`: Scale functions for data mapping

### Utilities
- **classnames (v2.5.1)**: Conditional CSS class management
- **@types/node (v22.14.0)**: Node.js type definitions

## Build Configuration

### Vite Configuration
- **ES Modules**: Modern JavaScript module system
- **TypeScript Support**: Built-in TypeScript compilation
- **Development Server**: Hot module replacement and fast refresh

### Scripts
- `npm run dev`: Development server
- `npm run build`: Production build
- `npm run preview`: Preview production build

## File Structure Patterns

### Component Organization
- **Main App Component**: `App.tsx` - Primary application logic
- **Specialized Components**: 
  - `VideoPlayer.tsx` - Video playback and controls
  - `Chart.tsx` - Data visualization component
- **Utility Modules**:
  - `api.ts` - API integration functions
  - `functions.ts` - AI function definitions
  - `modes.ts` - Analysis mode configurations
  - `utils.ts` - General utility functions

### Configuration Files
- `package.json`: Dependencies and scripts
- `tsconfig.json`: TypeScript configuration
- `vite.config.ts`: Build tool configuration
- `index.html`: HTML template

## Development Environment

### Prerequisites
- **Node.js**: Required for package management and build process
- **npm**: Package manager for dependencies
- **Gemini API Key**: Required for AI functionality (set in .env.local)

### Local Development
- **Port**: Vite dev server (typically 3000 or 5173)
- **Hot Reload**: Automatic browser refresh on code changes
- **TypeScript**: Real-time type checking during development

## API Dependencies

### External Services
- **Google Generative AI**: Core AI processing service
- **File Upload Service**: Video file processing and storage

### Function Call Interface
- `set_timecodes`: Standard timecode setting
- `set_timecodes_with_objects`: Timecodes with object detection
- `set_timecodes_with_numeric_values`: Numeric data for charts

## Performance Considerations
- **Lazy Loading**: Components loaded on demand
- **State Optimization**: Minimal re-renders through proper state management
- **File Handling**: Efficient video file upload and processing
- **Memory Management**: Proper cleanup of video URLs and references
