# Google Video Analyzer - Project Brief

## Project Overview
**Google Video Analyzer** is a React-based web application that leverages Google's Generative AI to analyze video content and provide various insights through different analysis modes.

## Core Functionality
- **Video Upload**: Drag-and-drop video file upload
- **AI Analysis**: Multiple analysis modes using Google's Gemini API
- **Interactive Results**: Clickable timecodes to jump to specific video moments
- **Visualization**: Chart mode for data visualization using D3.js

## Analysis Modes
- **Table Mode**: Structured data with timecodes, descriptions, and objects
- **Chart Mode**: Visual data representation with multiple chart types
- **List Mode**: Simple list format of analysis results
- **Custom Mode**: User-defined prompts for custom analysis

## Technical Stack
- **Frontend**: React 19, TypeScript
- **Build Tool**: Vite
- **AI Integration**: Google Generative AI (@google/generative-ai)
- **Visualization**: D3.js (d3-array, d3-shape, d3-scale)
- **Styling**: CSS with classnames utility

## Key Features
- Responsive design with collapsible sidebar
- Theme support (light/dark mode detection)
- Real-time video playback synchronization
- Function calling integration with AI model
- Error handling for video upload and processing

## Current State
- Fully functional video analysis application
- Ready for enhancements or modifications
- Well-structured codebase with clear component separation
