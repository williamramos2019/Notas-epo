# Overview

This is a full-stack document management system designed to process emails with attachments, extract financial data from documents (PDFs and images), and provide a dashboard for managing financial documents. The system integrates with Microsoft Identity Platform for authentication and uses OCR/PDF parsing to extract key information like names, values, issue dates, and due dates from uploaded documents.

The application features a React frontend with a modern design using shadcn/ui components, an Express.js backend with TypeScript, and PostgreSQL database with Drizzle ORM for data persistence. Users can authenticate via Microsoft OAuth, sync emails, upload documents manually, and view extracted financial data through various interfaces including tables, grids, and charts.

# User Preferences

Preferred communication style: Simple, everyday language.
Project feedback: Sistema funcionando muito bem, usuário satisfeito com resultado final.

# System Architecture

## Frontend Architecture
- **Framework**: React with TypeScript for type safety and modern development
- **Styling**: TailwindCSS for utility-first styling with shadcn/ui component library
- **State Management**: TanStack Query for server state management and caching
- **Routing**: Wouter for lightweight client-side routing
- **Build Tool**: Vite for fast development and optimized builds

## Backend Architecture  
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript for full-stack type safety
- **Authentication**: Replit Auth integration with OpenID Connect for Microsoft Identity Platform
- **Session Management**: Express sessions with PostgreSQL session store
- **File Processing**: Multer for file uploads with support for PDFs and images
- **API Design**: RESTful endpoints with JSON responses

## Database Layer
- **Database**: PostgreSQL for relational data storage
- **ORM**: Drizzle ORM for type-safe database operations
- **Schema**: Structured tables for users, messages, attachments, documents, and upload queue
- **Migrations**: Drizzle Kit for database schema management

## Authentication & Authorization
- **Provider**: Microsoft Identity Platform via Replit Auth
- **Session Storage**: PostgreSQL-backed sessions with 7-day TTL
- **Route Protection**: Middleware-based authentication checks on protected routes
- **User Management**: Automatic user creation and profile syncing

## File Processing Pipeline
- **Upload Handling**: Multer middleware with file type validation (PDF, JPEG, PNG)
- **Storage**: Local filesystem storage in uploads directory
- **Queue System**: Database-driven upload queue for processing status tracking
- **Document Extraction**: Planned integration with PDF parsing and OCR libraries for data extraction

## Frontend Component Architecture
- **Layout Components**: Header, Navigation, and page-specific layouts
- **Feature Components**: Dashboard stats, charts, document grids, email lists, upload areas
- **UI Components**: Comprehensive shadcn/ui component library with consistent theming
- **Responsive Design**: Mobile-first approach with Tailwind responsive utilities

## API Structure
- **Authentication**: `/api/auth/*` endpoints for user management
- **Data Management**: RESTful endpoints for messages, documents, attachments
- **File Operations**: Upload and processing endpoints with progress tracking
- **Dashboard**: Aggregated statistics and analytics endpoints

# External Dependencies

## Core Framework Dependencies
- **@neondatabase/serverless**: PostgreSQL database driver optimized for serverless environments
- **drizzle-orm**: Type-safe ORM for database operations
- **express**: Web application framework for Node.js
- **@tanstack/react-query**: Data fetching and caching library

## Authentication & Session Management
- **openid-client**: OpenID Connect client for Microsoft authentication
- **passport**: Authentication middleware
- **express-session**: Session management
- **connect-pg-simple**: PostgreSQL session store

## UI & Styling
- **@radix-ui/react-***: Comprehensive set of accessible UI primitives
- **tailwindcss**: Utility-first CSS framework
- **class-variance-authority**: Utility for creating type-safe component variants
- **lucide-react**: Icon library with React components

## File Processing
- **multer**: Multipart/form-data handling for file uploads
- **@types/multer**: TypeScript definitions for multer

## Development Tools
- **vite**: Build tool and development server
- **typescript**: TypeScript compiler and language support
- **tsx**: TypeScript execution engine for Node.js
- **esbuild**: Fast JavaScript bundler for production builds

## Planned Integrations
- **smalot/pdfparser**: PHP library for PDF text extraction (mentioned in requirements)
- **thiagoalessio/tesseract_ocr**: OCR library for image text extraction (mentioned in requirements)
- **Chart.js**: Charting library loaded via CDN for dashboard visualizations