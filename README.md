# AgencyNest - Multi-Tenant SaaS Agency Management Platform

AgencyNest is a comprehensive multi-tenant SaaS platform designed for digital agencies to manage their clients, projects, and team members. Built with Next.js 14, it provides a complete solution for agency management with white-label capabilities.


<img width="1536" height="1024" alt="790c680b-edd5-4f10-82e6-87a5f45cd65f" src="https://github.com/user-attachments/assets/b4117a54-12a0-41d5-90c7-441a6c89f8b2" />

## 🚀 Features

- **Multi-Tenant Architecture**: Each agency gets their own isolated workspace
- **Authentication & Authorization**: Secure user management with Clerk
- **Payment Processing**: Integrated Stripe payments for subscriptions and one-time fees
- **File Management**: Upload and manage files with UploadThing
- **Database Management**: Prisma ORM with MySQL database
- **Website Builder**: Integrated Builder.io for dynamic content creation
- **Agency Dashboard**: Comprehensive dashboard for managing clients and projects
- **Client Management**: Track client projects, billing, and communications

## 🛠️ Tech Stack

- **Frontend**: Next.js 14, React, TypeScript, Tailwind CSS
- **Backend**: Next.js API Routes, Prisma ORM
- **Database**: MySQL
- **Authentication**: Clerk
- **Payments**: Stripe
- **File Storage**: UploadThing

## 📋 Prerequisites

Before you begin, ensure you have the following installed:
- Node.js 18+ 
- MySQL database
- npm or yarn package manager

## 🔧 Environment Setup

Create a `.env` file in the root directory with the following variables:

```bash
# Clerk Authentication
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_clerk_publishable_key
CLERK_SECRET_KEY=your_clerk_secret_key
NEXT_PUBLIC_CLERK_SIGN_IN_URL=/agency/sign-in
NEXT_PUBLIC_CLERK_SIGN_UP_URL=/agency/sign-up
NEXT_PUBLIC_CLERK_AFTER_SIGN_IN_URL=/
NEXT_PUBLIC_CLERK_AFTER_SIGN_UP_URL=/

# Database Configuration
DB_USERNAME=your_db_username
DB_PASSWORD=your_db_password
DATABASE_URL="mysql://root:password@localhost:3306/AgencyNest"
PROD_DATABASE_URL=your_production_database_url
LOCAL_DATABASE_URL="mysql://root:password@localhost:3306/AgencyNest"
DATABPASE_PASSWORD=your_database_password

# Application URLs
NEXT_PUBLIC_URL=http://localhost:3000
NEXT_PUBLIC_DOMAIN=localhost:3000
NEXT_PUBLIC_SCHEME=http://

# File Upload (UploadThing)
UPLOADTHING_SECRET=your_uploadthing_secret
UPLOADTHING_APP_ID=your_uploadthing_app_id

# Stripe Payment Processing
NEXT_PUBLIC_STRIPE_PUBLISHABLE_KEY=your_stripe_publishable_key
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret
NEXT_PUBLIC_STRIPE_CLIENT_ID=your_stripe_client_id

# Platform Configuration
NEXT_PUBLIC_PLATFORM_SUBSCRIPTION_PERCENT=1
NEXT_PUBLIC_PLATFORM_ONETIME_FEE=2
NEXT_PUBLIC_PLATFORM_AGENY_PERCENT=1
NEXT_AgencyNest_PRODUCT_ID=your_stripe_product_id

# Builder.io (Content Management)
NEXT_PUBLIC_BUILDER_API_KEY=your_builder_api_key
```

## 🚀 Installation & Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd webprodigies-AgencyNest-main
   ```

2. **Install dependencies**
   ```bash
   npm install
   # or
   yarn install
   ```

3. **Set up your database**
   ```bash
   # Generate Prisma client
   npx prisma generate
   
   # Run database migrations
   npx prisma db push
   
   # Optional: Seed the database
   npx prisma db seed
   ```

4. **Start the development server**
   ```bash
   npm run dev
   # or
   yarn dev
   ```

5. **Open your browser**
   Navigate to `http://localhost:3000`

## 📁 Project Structure

```
AgencyNest/
├── src/
│   ├── app/                    # Next.js 14 app directory
│   │   ├── (main)/            # Main application routes
│   │   │   ├── agency/        # Agency management pages
│   │   │   ├── subaccount/    # Sub-account management
│   │   │   └── site/          # Public site pages
│   │   ├── api/               # API routes
│   │   │   ├── auth/          # Authentication endpoints
│   │   │   ├── stripe/        # Stripe webhook handlers
│   │   │   └── uploadthing/   # File upload endpoints
│   │   └── globals.css        # Global styles
│   ├── components/            # Reusable React components
│   │   ├── ui/               # Base UI components
│   │   ├── forms/            # Form components
│   │   ├── media/            # Media upload components
│   │   └── global/           # Global layout components
│   ├── lib/                  # Utility functions and configurations
│   │   ├── db.ts            # Database connection
│   │   ├── stripe.ts        # Stripe configuration
│   │   ├── uploadthing.ts   # Upload configuration
│   │   └── utils.ts         # Helper utilities
│   ├── providers/           # Context providers
│   │   ├── modal-provider.tsx
│   │   └── query-provider.tsx
│   └── types/               # TypeScript type definitions
├── prisma/                  # Database schema and migrations
│   ├── schema.prisma       # Database schema
│   └── migrations/         # Database migration files
├── public/                 # Static assets
│   ├── images/            # Image assets
│   ├── icons/             # Icon files
│   └── assets/            # Other static files
├── .env                   # Environment variables
├── .env.example          # Environment variables template
├── package.json          # Project dependencies
├── tailwind.config.js    # Tailwind CSS configuration
├── next.config.js        # Next.js configuration
└── tsconfig.json         # TypeScript configuration
```

### 📂 Key Directories Explained

- **`src/app/`**: Contains all application routes using Next.js 14 app directory structure
  - **`(main)/`**: Main application with authentication required
  - **`agency/`**: Agency onboarding and management interface
  - **`subaccount/`**: Client sub-account management dashboard
  - **`site/`**: Public-facing pages and landing pages

- **`src/components/`**: Reusable React components organized by functionality
  - **`ui/`**: Basic UI components (buttons, inputs, modals)
  - **`forms/`**: Complex form components for data entry
  - **`global/`**: Layout components used across the application

- **`src/lib/`**: Core utilities and configurations
  - Database connections, third-party service configurations, and helper functions

- **`prisma/`**: Database layer
  - Schema definitions and migration files for data persistence

## 🔗 External Services Setup

### Clerk Authentication
1. Create account at [Clerk.dev](https://clerk.dev)
2. Set up your application
3. Configure sign-in/sign-up pages
4. Add API keys to environment variables

### Stripe Payments
1. Create account at [Stripe.com](https://stripe.com)
2. Set up products and pricing
3. Configure webhooks for subscription management
4. Add API keys and webhook secrets

### UploadThing File Storage
1. Create account at [UploadThing](https://uploadthing.com)
2. Configure file upload settings
3. Add API credentials

### Manual Deployment
1. Build the application: `npm run build`
2. Start production server: `npm start`
3. Ensure all environment variables are set in production
