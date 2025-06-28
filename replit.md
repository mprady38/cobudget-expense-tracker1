# CoBudget - Personal Expense Tracking Application

## Overview
CoBudget is a full-stack web application for tracking personal finances between two users (Prady and Rishita). It's built using React with TypeScript on the frontend, Express.js on the backend, and PostgreSQL for data persistence. The application uses Replit's authentication system and provides a responsive interface for managing income and expenses with visual analytics.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Build Tool**: Vite for fast development and optimized builds
- **Styling**: Tailwind CSS with shadcn/ui component library
- **UI Components**: Radix UI primitives for accessibility
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for client-side routing
- **Charts**: Recharts for data visualization

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Database ORM**: Drizzle ORM with Neon PostgreSQL
- **Authentication**: Replit Auth with OpenID Connect
- **Session Management**: PostgreSQL-backed sessions using connect-pg-simple
- **API Design**: RESTful endpoints with proper error handling

### Database Schema
- **Users Table**: Stores user profile information (required for Replit Auth)
- **Sessions Table**: Manages user sessions (required for Replit Auth)
- **Income Table**: Monthly income tracking per user
- **Expenses Table**: Individual expense records with categorization

## Key Components

### Authentication System
- **Provider**: Replit Auth with Google OAuth integration
- **Authorization**: Restricted to specific email addresses (mpradyumna38@gmail.com, allikarishita.44@gmail.com)
- **Session Storage**: PostgreSQL-backed sessions with 7-day TTL
- **User Management**: Automatic user creation/update on login

### Data Models
- **Income**: Monthly salary and carry-over amounts per user
- **Expenses**: Categorized spending with date, amount, description, and payment method
- **Analytics**: Real-time calculations for spending patterns and trends

### UI/UX Features
- **Responsive Design**: Mobile-first approach with sidebar navigation
- **Dark Mode Support**: CSS variables for theme switching
- **Loading States**: Skeleton components and loading indicators
- **Form Validation**: Zod schemas with React Hook Form
- **Toast Notifications**: User feedback for actions

## Data Flow

1. **Authentication Flow**:
   - User clicks Google login → Replit Auth → User creation/update → Session establishment

2. **Income Management**:
   - User enters monthly salary and carry-over → Validation → Database storage → UI update

3. **Expense Tracking**:
   - User creates expense → Category/payment method selection → Database storage → Analytics recalculation

4. **Analytics Generation**:
   - Real-time aggregation of expenses by category, month, and user
   - Visual representation through charts and financial cards

## External Dependencies

### Core Technologies
- **Database**: Neon PostgreSQL (serverless PostgreSQL)
- **Authentication**: Replit Auth service
- **UI Library**: shadcn/ui with Radix UI primitives
- **Charting**: Recharts library
- **Date Handling**: date-fns library

### Development Tools
- **TypeScript**: Type safety across the stack
- **ESLint/Prettier**: Code quality and formatting
- **Vite**: Development server and build tool

## Deployment Strategy

### Development Environment
- **Runtime**: Node.js with ES modules
- **Development Server**: Vite dev server with HMR
- **Database**: Environment-based DATABASE_URL connection

### Production Build
- **Frontend**: Vite build output served as static files
- **Backend**: ESBuild compilation to single JavaScript file
- **Environment Variables**: DATABASE_URL, SESSION_SECRET, REPL_ID, ISSUER_URL

### Database Migrations
- **Tool**: Drizzle Kit for schema management
- **Strategy**: Push-based migrations for development
- **Schema Location**: `shared/schema.ts` for type sharing

## Changelog
```
Changelog:
- June 28, 2025. Complete CoBudget expense tracker implementation with mobile APK generation
  - Built full-stack app with React/TypeScript frontend and Express backend
  - Implemented Google OAuth authentication via Replit Auth
  - Created PostgreSQL database with users, income, and expenses tables
  - Built responsive UI with dashboard, income/expense forms, and charts
  - Added financial analytics with category breakdowns and monthly trends
  - Configured for two specific users: Prady and Rishita
  - Fixed SQL query issues and React navigation warnings
  - Added Capacitor mobile framework for Android APK generation
  - Set up GitHub Actions workflow for automatic APK building
  - Created GitHub-ready project package (2.4MB) with complete documentation
  - Prepared alternative to discontinued Ionic Appflow using GitHub automation
```

## User Preferences
```
Preferred communication style: Simple, everyday language.
```