# Farming Pro Bot - Telegram Web App

## Overview

This is a Telegram Web App built for a farming game bot where users can earn USDT through various activities like farming, completing tasks, referring others, and using boosts. The application follows a modern full-stack architecture with React frontend and Express backend, using PostgreSQL for data persistence.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript
- **Styling**: Tailwind CSS with custom CSS variables for theming
- **UI Components**: Radix UI components via shadcn/ui
- **State Management**: TanStack Query (React Query) for server state
- **Routing**: Wouter for client-side routing
- **Build Tool**: Vite for development and building

### Backend Architecture
- **Framework**: Express.js with TypeScript
- **Runtime**: Node.js with ES modules
- **Database**: PostgreSQL with Drizzle ORM
- **Database Provider**: Neon Database (serverless PostgreSQL)
- **API Design**: RESTful endpoints
- **Development**: Hot reload with Vite integration

## Key Components

### Database Schema
The application uses a comprehensive schema with the following main entities:
- **Users**: Core user data including balance, farming status, and referral info
- **Tasks**: Available tasks with rewards and completion tracking
- **Boosts**: Performance multipliers that users can purchase
- **Referrals**: Multi-level referral system (3 levels)
- **Transactions**: Financial transaction history
- **Settings**: Application configuration

### Core Features
1. **Farming System**: Time-based earning mechanism with 4-hour cycles
2. **Task System**: Social media tasks with USDT rewards
3. **Referral System**: 3-level commission structure
4. **Boost System**: Temporary farming rate multipliers
5. **Wallet System**: Balance management and transaction history
6. **Admin Panel**: User management and system oversight

### UI Structure
- **Mobile-first Design**: Optimized for Telegram Web App
- **Bottom Navigation**: 5 main sections (Farm, Tasks, Referral, Wallet, Boost)
- **Dark Theme**: Custom color scheme with accent colors
- **Responsive Components**: Adaptive layouts for different screen sizes

## Data Flow

### User Authentication
- Users are identified by Telegram ID
- Auto-registration on first access
- Session management through Telegram Web App context

### Farming Process
1. User starts farming session (4-hour duration)
2. System tracks farming start/end times
3. Earnings calculated based on rate and boost multipliers
4. Users claim rewards after completion

### Task Completion
1. User views available tasks
2. Completes external actions (social media follows, etc.)
3. Claims task rewards
4. System updates user balance and task completion status

### Referral System
1. Users share referral links
2. New users register with referral code
3. System creates referral relationships
4. Commissions distributed across 3 levels

## External Dependencies

### Core Libraries
- **@tanstack/react-query**: Server state management
- **drizzle-orm**: Database ORM and migrations
- **@neondatabase/serverless**: PostgreSQL database driver
- **express**: Web server framework
- **wouter**: Client-side routing
- **zod**: Runtime type validation

### UI Libraries
- **@radix-ui/***: Accessible UI primitives
- **tailwindcss**: CSS framework
- **lucide-react**: Icon library
- **class-variance-authority**: Component variant system

### Development Tools
- **vite**: Build tool and dev server
- **typescript**: Type system
- **tsx**: TypeScript execution
- **esbuild**: JavaScript bundler

## Deployment Strategy

### Build Process
1. **Frontend**: Vite builds React app to `dist/public`
2. **Backend**: ESBuild bundles server code to `dist/index.js`
3. **Database**: Drizzle handles schema migrations

### Environment Configuration
- **DATABASE_URL**: PostgreSQL connection string
- **NODE_ENV**: Environment (development/production)
- Development includes Vite dev server integration
- Production serves static files from Express

### Database Management
- Schema defined in `shared/schema.ts`
- Migrations stored in `./migrations`
- Push schema changes with `npm run db:push`

## User Preferences

Preferred communication style: Simple, everyday language.

## Changelog

Changelog:
- July 08, 2025. Initial setup
- July 08, 2025. Added Telegram Bot API integration with webhook support
- July 08, 2025. Implemented withdrawal requirements: $12 minimum, $5 first deposit, $3 per withdrawal
- July 08, 2025. Added deposit/withdrawal validation system with comprehensive tracking
- July 08, 2025. Added PostgreSQL database with full migration from memory storage