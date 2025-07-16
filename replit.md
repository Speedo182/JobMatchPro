# Dooajob Recruitment Platform

## Overview

Dooajob is a comprehensive recruitment platform that connects businesses, recruiters, and candidates through intelligent automation and seamless workflows. The application operates on a subscription-based model with three tiers (Basic, Professional, and Enterprise) and provides role-specific dashboards for each user type.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with shadcn/ui component library
- **State Management**: React Context for authentication, TanStack Query for server state
- **Routing**: Wouter (lightweight React router)
- **Build Tool**: Vite for development and production builds

### Backend Architecture
- **Runtime**: Node.js with Express.js
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM
- **Authentication**: JWT-based authentication with bcryptjs for password hashing
- **Session Management**: Express sessions with PostgreSQL store

### Data Storage
- **Database**: PostgreSQL (configured for Replit database)
- **Connection**: Replit PostgreSQL for scalable database operations
- **Schema**: Comprehensive recruitment platform schema with role-based access

## Key Components

### Authentication System
- JWT token-based authentication
- Role-based access control (business, recruiter, candidate)
- Password hashing with bcryptjs
- Protected routes with middleware

### User Roles and Dashboards
1. **Business Dashboard**: Job posting, application management, subscription tracking
2. **Recruiter Dashboard**: Job notifications, candidate browsing, application submissions
3. **Candidate Dashboard**: Profile management, job applications, CV uploads

### Database Schema
- **Users**: Core user information with role-based differentiation
- **Businesses**: Company profiles with subscription tiers and usage tracking
- **Recruiters**: Recruiter profiles with specialization and commission rates
- **Candidates**: Candidate profiles with skills and experience
- **Jobs**: Job postings with status tracking and requirements
- **Applications**: Application submissions linking candidates to jobs
- **Job Notifications**: Automated notifications for recruiters about new job postings

### UI/UX Components
- Responsive design with mobile-first approach
- Consistent component library using shadcn/ui
- Form validation and error handling
- Toast notifications for user feedback
- Modal dialogs for authentication and forms

## Data Flow

### Authentication Flow
1. User registers/logs in through auth modal
2. JWT token generated and stored in localStorage
3. Token included in API requests for protected routes
4. Server validates token and attaches user context

### Job Posting Flow
1. Business creates job posting through dashboard
2. Job automatically triggers notifications to relevant recruiters
3. Recruiters receive real-time notifications
4. Candidates can search and apply for jobs

### Application Flow
1. Candidates submit applications with CV uploads
2. Applications tracked in database with status updates
3. Businesses and recruiters can review applications
4. Status updates trigger notifications to relevant parties

## External Dependencies

### Core Libraries
- **@neondatabase/serverless**: PostgreSQL database connection
- **drizzle-orm**: Type-safe database ORM
- **@tanstack/react-query**: Server state management
- **bcryptjs**: Password hashing
- **jsonwebtoken**: JWT authentication
- **express**: Web server framework

### UI Libraries
- **@radix-ui/***: Accessible UI primitives
- **tailwindcss**: Utility-first CSS framework
- **lucide-react**: Icon library
- **class-variance-authority**: Component variant management

### Development Tools
- **vite**: Build tool and dev server
- **typescript**: Type checking
- **tsx**: TypeScript execution
- **esbuild**: Production bundling

## Recent Changes

### January 12, 2025 - Complete 4-Portal System & Advanced Dashboards
- **Comprehensive Portal Architecture**: Full 4-portal implementation
  - **Advanced Business Dashboard**: Complete CRM-style interface with analytics, job management, application tracking, and performance insights
  - **Advanced Recruiter Dashboard**: Professional workspace with opportunities, candidate pipeline, placements tracking, and commission management
  - **Advanced Candidate Portal**: Personalized job search, application management, profile building, and career development tools
  - **Advanced Admin Portal**: Full platform management with user oversight, system health monitoring, and analytics
- **Role-Based Integration**: Seamless portal routing
  - Dynamic dashboard loading based on user role
  - Enhanced profile setup modal with role-specific forms
  - Comprehensive dashboard tour system (1-5 steps per role)
  - Modern authentication with React hooks structure fixed
- **Database & Storage**: Complete integration resolved
  - Fixed storage interface compatibility issues
  - Added missing updateUser method in storage implementation
  - Enhanced authentication system with proper error handling
  - Comprehensive schema support for all user types

### January 12, 2025 - Real-Time Notification System Implementation
- **Notification Infrastructure**: Complete real-time system
  - WebSocket server for instant push notifications
  - SendGrid email integration for professional email alerts
  - Notification bell component with unread count badges
  - Real-time connection status indicators
- **Notification Types**: Comprehensive alert system
  - Job posting alerts to recruiters
  - Application received notifications to businesses
  - Application status updates to candidates
  - Email templates with professional styling
- **Database Integration**: Using Replit PostgreSQL database
  - Notification storage and management
  - User preference tracking
  - Real-time data synchronization
- **Stripe Payments**: Three-tier subscription system with 14-day trials

### January 12, 2025 - Complete Professional Redesign & Role-Based Portals
- **Enhanced Professional Design**: Premium CRM-style interface
  - Desktop grid layout with sticky sidebar navigation
  - Enhanced color palette with gradient buttons and animations
  - Logo blending effects and professional styling
  - Improved mobile responsive design with professional aesthetics
- **Role-Based Dashboard System**: Comprehensive user portals
  - **Candidate Portal**: Jobs available, CV upload, account settings
  - **Business Portal**: Job posting, candidate review, billing history
  - **Recruiter Portal**: Full platform access with all features
  - Dynamic navigation based on user role with role badges
- **Complete Page Suite**: All user journey pages implemented
  - Enhanced Submit Job page with better logo integration
  - Professional Job Listings with search functionality
  - Submit Candidate with file uploads and verification
  - Edit Job with Job ID display and download features
  - Review Candidates with status management and filtering
  - Billing & Payments with transaction history
  - Enhanced Thank You page with process explanation
- **Desktop CRM Experience**: Professional business interface
  - Two-column layout for desktop users
  - Sticky sidebar with role-appropriate navigation
  - Enhanced typography and spacing for business use
  - Card-based layouts with hover effects and gradients
- **Authentication System**: Replit Auth with Google login integration
- **Database**: PostgreSQL with proper sessions table and user management
- **User Experience**: Market-ready, professional recruitment platform

## Deployment Strategy

### Development
- Vite dev server for frontend with HMR
- tsx for running TypeScript server directly
- Environment-based configuration

### Production Build
- Vite builds optimized frontend bundle
- esbuild bundles server code for Node.js
- Static assets served from dist/public
- Server runs from dist/index.js

### Environment Configuration
- DATABASE_URL: Replit PostgreSQL connection string
- SENDGRID_API_KEY: Email notification service (configured)
- STRIPE_SECRET_KEY: Backend payment processing (configured)
- VITE_STRIPE_PUBLIC_KEY: Frontend payment integration (configured)
- NODE_ENV for environment-specific behavior

### Database Management
- Drizzle migrations in migrations/ directory
- Schema definitions in shared/schema.ts
- Push command for development schema updates

The application follows a monorepo structure with clear separation between client, server, and shared code, enabling efficient development and deployment workflows. Focus remains on practical business solutions without web3 or crypto features.