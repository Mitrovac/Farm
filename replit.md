# Farm Fault Tracker - Replit Configuration

## Overview

This is a full-stack web application for tracking and managing machine faults across agricultural farms. The system provides real-time fault management, team collaboration, and deadline tracking for farm equipment maintenance operations.

## System Architecture

The application follows a modern full-stack architecture:

- **Frontend**: React with TypeScript, using Vite as the build tool
- **Backend**: Express.js with TypeScript, serving both API endpoints and static files
- **Database**: PostgreSQL with Drizzle ORM for database operations
- **Authentication**: Replit OIDC integration with session management
- **Real-time Updates**: WebSocket implementation for live data synchronization
- **UI Framework**: Tailwind CSS with shadcn/ui component library

## Key Components

### Frontend Architecture
- **React Router**: Uses Wouter for client-side routing
- **State Management**: React Query (TanStack Query) for server state management
- **Component Library**: shadcn/ui components built on Radix UI primitives
- **Styling**: Tailwind CSS with custom Material Design color palette
- **Form Handling**: React Hook Form with Zod validation

### Backend Architecture
- **API Layer**: RESTful API with Express.js
- **Database Layer**: Drizzle ORM with PostgreSQL
- **Authentication**: Passport.js with OpenID Connect strategy
- **Session Management**: PostgreSQL-backed sessions using connect-pg-simple
- **Real-time Communication**: WebSocket server for live updates

### Database Schema
- **Users**: Stores user profile information from Replit Auth
- **Farms**: Farm locations and basic information
- **Machines**: Equipment associated with specific farms
- **Faults**: Issue tracking with status, priority, and assignment
- **Comments**: Threaded discussions on fault records
- **Sessions**: Authentication session storage

## Data Flow

1. **Authentication Flow**: Users authenticate via Replit OIDC, sessions stored in PostgreSQL
2. **API Requests**: Frontend makes authenticated requests to Express API endpoints
3. **Database Operations**: Drizzle ORM handles database queries and mutations
4. **Real-time Updates**: WebSocket broadcasts changes to connected clients
5. **State Synchronization**: React Query automatically refetches affected data

## External Dependencies

### Database
- **Neon Database**: Serverless PostgreSQL provider
- **Connection Pooling**: @neondatabase/serverless with WebSocket support

### Authentication
- **Replit Auth**: OIDC provider for user authentication
- **Session Storage**: PostgreSQL-backed session management

### UI Libraries
- **Radix UI**: Accessible component primitives
- **Tailwind CSS**: Utility-first CSS framework
- **Lucide React**: Icon library

### Development Tools
- **Vite**: Frontend build tool with HMR
- **TypeScript**: Type safety across the stack
- **Drizzle Kit**: Database migration and introspection tools

## Deployment Strategy

The application is designed for deployment on Replit with the following considerations:

1. **Environment Variables**: DATABASE_URL, SESSION_SECRET, REPL_ID, ISSUER_URL
2. **Build Process**: Vite builds the frontend, esbuild bundles the backend
3. **Production Server**: Single Express server serves both API and static files
4. **Database Migrations**: Drizzle Kit handles schema changes
5. **Development Mode**: Vite dev server with Express API in middleware mode

## Changelog

```
Changelog:
- July 08, 2025. Initial setup
```

## User Preferences

```
Preferred communication style: Simple, everyday language.
```