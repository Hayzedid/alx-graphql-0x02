# ALX Rick and Morty App - Episode Explorer

A Next.js application that uses GraphQL to fetch and display Rick and Morty episode data with interactive components and pagination.

## Features

- Built with Next.js 14 and TypeScript
- Apollo Client for GraphQL data fetching
- Tailwind CSS for responsive styling
- Rick and Morty API integration
- Interactive episode cards with hover effects
- Pagination for browsing episodes
- TypeScript interfaces for type safety
- Responsive design with gradient backgrounds

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

3. Open [http://localhost:3000](http://localhost:3000) in your browser

## Project Structure

```
alx-rick-and-morty-app/
├── components/
│   └── common/
│       └── EpisodeCard.tsx   # Episode card component
├── graphql/
│   ├── apolloClient.ts       # Apollo Client configuration
│   └── queries.ts            # GraphQL queries
├── interfaces/
│   └── index.ts              # TypeScript interfaces
├── pages/
│   ├── _app.tsx             # App component with Apollo Provider
│   └── index.tsx            # Main page with episode list
├── styles/
│   └── globals.css          # Global styles with Tailwind
└── package.json             # Dependencies and scripts
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

### Home Page
Main application page featuring:
- Episode grid layout
- Pagination controls
- Loading and error states
- Responsive header and footer

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
