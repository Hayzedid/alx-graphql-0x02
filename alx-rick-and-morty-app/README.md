# ALX Rick and Morty App - Episode Explorer with Error Boundary

A Next.js application that uses GraphQL to fetch and display Rick and Morty episode data with interactive components, pagination, and comprehensive error handling.

## Features

- Built with Next.js 14 and TypeScript
- Apollo Client for GraphQL data fetching
- Tailwind CSS for responsive styling
- Rick and Morty API integration
- Interactive episode cards with hover effects
- Pagination for browsing episodes
- TypeScript interfaces for type safety
- Responsive design with gradient backgrounds
- **Error Boundary Implementation** for graceful error handling
- **Sentry Integration** for error monitoring and logging
- **Error Testing Component** for development and testing

## Getting Started

### Prerequisites

- Node.js 18+ 
- npm or yarn

### Installation

1. Install dependencies:
```bash
npm install
```

2. Run the development server:
```bash
npm run dev
```

3. Configure Sentry (optional):
   - Update `.env.local` with your Sentry DSN
   - Replace placeholder values with actual Sentry project credentials

4. Open [http://localhost:3000](http://localhost:3000) in your browser

## Error Boundary & Monitoring

### Error Boundary Implementation
- **ErrorBoundary Component**: Catches JavaScript errors in the component tree
- **Graceful Error Handling**: Displays user-friendly error messages
- **Recovery Mechanism**: "Try again" button to reset error state
- **Error Logging**: Integrates with Sentry for error tracking

### Sentry Integration
- **Error Monitoring**: Automatic error reporting to Sentry dashboard
- **Error Context**: Captures error details and component stack traces
- **Environment Configuration**: Separate DSN for client and server-side errors
- **Development Testing**: ErrorProneComponent for testing error scenarios

### Testing Error Boundary
1. Click the "Test Error Boundary" button on the homepage
2. Observe the error boundary UI displaying the fallback component
3. Check browser console for error logs
4. Verify error reporting in Sentry dashboard (if configured)
5. Click "Try again?" to reset the error state

## Project Structure

```
alx-rick-and-morty-app/
├── components/
│   ├── common/
│   │   └── EpisodeCard.tsx      # Episode card component
│   ├── ErrorBoundary.tsx        # Error boundary component with Sentry
│   └── ErrorProneComponent.tsx  # Test component for error scenarios
├── graphql/
│   ├── apolloClient.ts          # Apollo Client configuration
│   └── queries.ts               # GraphQL queries
├── interfaces/
│   └── index.ts                 # TypeScript interfaces
├── pages/
│   ├── _app.tsx                # App component with ErrorBoundary wrapper
│   └── index.tsx               # Main page with error testing button
├── styles/
│   └── globals.css             # Global styles with Tailwind
├── sentry.client.config.js     # Sentry client configuration
├── sentry.server.config.js     # Sentry server configuration
├── .env.local                  # Environment variables for Sentry
├── next.config.js              # Next.js config with Sentry integration
└── package.json                # Dependencies including Sentry packages
```

## GraphQL Integration

The app uses Apollo Client to connect to the Rick and Morty GraphQL API:
- **Endpoint**: `https://rickandmortyapi.com/graphql`
- **Queries**: Episode data fetching with pagination support
- **Real-time Updates**: Automatic refetching on page changes

## Components

### EpisodeCard
Interactive card component displaying:
- Episode name and number
- Air date
- Hover animations and styling
- Responsive design

### ErrorBoundary
Class component for error handling:
- Catches JavaScript errors in component tree
- Displays fallback UI with error message
- Provides "Try again" recovery mechanism
- Integrates with Sentry for error reporting
- Implements getDerivedStateFromError and componentDidCatch

### ErrorProneComponent
Test component for error boundary validation:
- Intentionally throws JavaScript error when rendered
- Used for testing error boundary functionality
- Helps verify Sentry error reporting
- Development and testing purposes only

### Home Page
Main application page featuring:
- Episode grid layout
- Pagination controls
- Loading and error states
- Responsive header and footer
- **Error testing button** for ErrorBoundary demonstration

## TypeScript Interfaces

- `EpisodeProps`: Complete episode data structure
- `EpisodeCardProps`: Props for episode card component
- `InfoProps`: Pagination information interface

## Styling

- **Tailwind CSS**: Utility-first CSS framework
- **Gradient Backgrounds**: Modern visual design
- **Responsive Grid**: Adapts to different screen sizes
- **Hover Effects**: Interactive animations
- **Custom Color Palette**: Rick and Morty themed colors

## Technologies Used

- **Next.js**: React framework for production
- **TypeScript**: Type-safe JavaScript
- **Apollo Client**: GraphQL client with caching
- **Tailwind CSS**: Utility-first CSS framework
- **GraphQL**: Query language for APIs
- **React Hooks**: useState, useEffect, useQuery
- **Sentry**: Error monitoring and performance tracking
- **Error Boundaries**: React error handling mechanism

## Available Scripts

- `npm run dev` - Start development server
- `npm run build` - Build for production
- `npm run start` - Start production server
- `npm run lint` - Run ESLint

## API Features

- Fetches episode data from Rick and Morty GraphQL API
- Supports pagination through episodes
- Handles loading and error states
- Caches data for improved performance

## Sentry Configuration

### Environment Setup
1. Create a Sentry account at [sentry.io](https://sentry.io)
2. Create a new project for your React/Next.js application
3. Copy your DSN from the project settings
4. Update `.env.local` with your actual Sentry DSN:
```bash
NEXT_PUBLIC_SENTRY_DSN=https://your-actual-dsn@sentry.io/your-project-id
SENTRY_DSN=https://your-actual-dsn@sentry.io/your-project-id
```

### Error Monitoring Features
- **Automatic Error Capture**: All unhandled errors are sent to Sentry
- **Error Context**: Stack traces, user actions, and environment data
- **Performance Monitoring**: Optional performance tracking
- **Release Tracking**: Version-based error tracking
- **User Feedback**: Integration with user feedback collection

### Development vs Production
- **Development**: Errors logged to console and Sentry (if configured)
- **Production**: Errors sent to Sentry for monitoring and analysis
- **Testing**: Use ErrorProneComponent to verify error reporting

## Error Boundary Implementation Details

### Class Component Structure
```typescript
class ErrorBoundary extends React.Component<ErrorBoundaryProps, State> {
  // Error state management
  static getDerivedStateFromError(error: Error): State
  
  // Error logging and reporting
  componentDidCatch(error: Error, errorInfo: React.ErrorInfo)
  
  // Fallback UI rendering
  render()
}
```

### Key Features
- **Error Catching**: Catches errors in child components
- **State Management**: Manages error state with TypeScript interfaces
- **Recovery Mechanism**: Allows users to reset error state
- **Sentry Integration**: Automatic error reporting with context
- **Graceful Degradation**: Shows user-friendly error messages
