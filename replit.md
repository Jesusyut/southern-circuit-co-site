# Southern Circuit Co. - Electrical Services Website

## Overview

Southern Circuit Co. is a professional electrical services company based in Queen Creek, Arizona, serving residential and commercial clients in the East Valley. This is a marketing website built to generate leads through service information display, portfolio showcase, and contact form submissions. The application features a southwestern/western brand identity while maintaining professional service industry standards.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

**Framework & Build System**
- **React 18 with TypeScript** - Component-based UI library for building the single-page application
- **Vite** - Modern build tool providing fast development server with HMR (Hot Module Replacement)
- **Wouter** - Lightweight client-side routing with two routes:
  - `/` - Main landing page
  - `/admin` - Admin panel for viewing contact submissions (requires authentication)

**UI Component System**
- **shadcn/ui** - Radix UI-based component library with Tailwind CSS styling
- **Style approach**: "new-york" variant with custom southwestern design tokens
- **Component structure**: Reusable UI components in `client/src/components/ui/`
- **Page components**: Main sections (Header, Hero, Services, About, Portfolio, Contact, Footer) composed into Home page

**Styling Architecture**
- **Tailwind CSS** - Utility-first CSS framework
- **Custom design system** defined in `design_guidelines.md`:
  - Typography: Bebas Neue/Oswald for headings, Montserrat for subheadings, Inter for body
  - Southwestern color palette with custom CSS variables
  - Consistent spacing primitives (4, 8, 12, 16 units)
  - Responsive breakpoints with mobile-first approach
- **CSS Variables**: HSL-based color system supporting light/dark modes
- **Custom interactions**: Hover and active state elevation effects

**State Management**
- **TanStack Query (React Query)** - Server state management and data fetching
- **React Hook Form** with Zod validation - Form state and validation (contact form)
- **Local component state** with React hooks

### Backend Architecture

**Server Framework**
- **Express.js** - HTTP server with API endpoints
- **Active endpoints**:
  - `POST /api/contact` - Save contact form submissions to database
  - `GET /api/contact-submissions` - Retrieve all submissions (requires ADMIN_TOKEN)
  - `POST /capi/contact` - Meta Conversions API for tracking
  - `GET /pixel-config` - Meta Pixel configuration
- **Development mode**: Vite middleware integration for HMR
- **Production mode**: Serves pre-built static assets

**Session & Storage**
- **DatabaseStorage** class - Hybrid storage using PostgreSQL for contact submissions
- **In-memory storage** for user management (MemStorage fallback)
- **Contact submissions** persist to PostgreSQL database

**API Design Pattern**
- RESTful convention with `/api` prefix for all backend routes
- Request/response logging middleware for API calls
- JSON body parsing with raw body access for webhook support
- Token-based authentication for admin endpoints

### Data Storage

**Database**
- **PostgreSQL** via Neon serverless driver
- **Drizzle ORM** - Type-safe database toolkit
- **Schema location**: `shared/schema.ts`
- **Current schema**: 
  - `users` table - Template user table (UUID primary key, username, password)
  - `contact_submissions` table - Stores contact form submissions (name, email, phone, service, message, timestamp)
- **Migration strategy**: Drizzle Kit with migrations in `./migrations` directory
- **Active usage**: Contact form submissions are persisted to the database

### External Dependencies

**Third-Party Services**
- **Google Fonts** - Bebas Neue, Oswald, Montserrat, Inter typography
- **Instagram** - Social media integration (link to @southerncircuitco)

**Development Tools**
- **Replit-specific plugins**:
  - `@replit/vite-plugin-runtime-error-modal` - Error overlay in development
  - `@replit/vite-plugin-cartographer` - Code navigation
  - `@replit/vite-plugin-dev-banner` - Development mode indicator

**Image Assets**
- Static images in `attached_assets/` directory:
  - Brand logo (`skull-logo.png`)
  - Generated service/portfolio images
  - Hero background (Arizona desert landscape)

**Form Handling**
- Contact form submissions saved to PostgreSQL database via `/api/contact` endpoint
- TanStack Query mutations handle form submission with loading states
- Toast notifications for success/error feedback
- Admin page at `/admin` displays all submissions (requires ADMIN_TOKEN authentication)

### Deployment Architecture

**Build Process**
1. Frontend: Vite builds React app to `dist/public`
2. Backend: esbuild bundles Express server to `dist/index.js`
3. Production: Node.js serves static files and API routes

**Environment Requirements**
- `DATABASE_URL` - PostgreSQL connection string (required for contact form submissions)
- `ADMIN_TOKEN` - Secret token for accessing admin panel at `/admin` (required for viewing submissions)
- `META_PIXEL_ID` - Meta/Facebook Pixel ID for conversion tracking
- `META_CAPI_TOKEN` - Meta Conversions API access token
- `META_TEST_EVENT_CODE` - Optional test event code for Meta tracking verification
- `SESSION_SECRET` - Session encryption secret
- `NODE_ENV` - development/production mode switching
- `REPL_ID` - Replit environment detection

**Port Configuration**
- Development: Vite dev server with Express middleware
- Production: Single Express server serving static build and API