# TechAndAIOverlords

A futuristic tech platform showcasing AI tools and offering a newsletter subscription for staying updated on the latest in AI and technology.

## Project Overview

TechAndAIOverlords is a Next.js application that combines a visually striking futuristic design with practical functionality. The platform offers:

1. A newsletter subscription service for AI and tech enthusiasts
2. A curated directory of AI tools organized by categories
3. Search and filtering capabilities to discover relevant AI tools

This project serves as a demonstration of modern web development practices, with thorough documentation throughout the codebase.

## Tech Stack

- **Frontend**: Next.js with TypeScript
- **Styling**: TailwindCSS with custom animations
- **Database**: PostgreSQL via Supabase
- **ORM**: Prisma
- **Form Validation**: Zod
- **Email**: Nodemailer for email delivery

## Project Documentation

### Quick Start
- [Project README](../README.md) - Quick project overview and structure

### Core Documentation
- [Product Requirements Document (PRD)](techandaioverlords-prd.md) - Detailed project requirements and specifications
- [Delivery Plan](techandaioverlords-delivery-plan.md) - Project phases and implementation timeline
- [User Flows](techandaioverlords-user-flows.mermaid) - Visual representation of key user interactions
- [GitHub Beginners Guide](github-beginners-guide.md) - Guide for version control and collaboration

### Phase-Specific Documentation
The project is implemented in four phases, each with detailed documentation:

#### Phase 1: Project Setup & Foundation
- [Phase 1 Checklist](Phase1/phase1-checklist.md) - Setup tasks and requirements
- [Phase 1 Architecture Diagram](Phase1/phase1-diagram.mermaid) - Visual representation of initial architecture

#### Phase 2: Core Landing Page
Documentation to be added during implementation.

#### Phase 3: AI Tools Directory
Documentation to be added during implementation.

#### Phase 4: Polish & Documentation
Documentation to be added during implementation.

## Getting Started

### Prerequisites

- Node.js 16.x or higher
- npm or yarn
- Git
- A Supabase account (for database)

### Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/techandaioverlords.git
cd techandaioverlords
```

2. Install dependencies:

```bash
npm install
# or
yarn install
```

3. Set up environment variables:

Create a `.env.local` file in the root directory with the following variables:

```
# Database
DATABASE_URL="postgresql://username:password@host:port/database"

# Email (for newsletter confirmation)
EMAIL_SERVER=smtp://username:password@smtp.example.com:587
EMAIL_FROM=noreply@yourdomain.com

# Supabase (if using Supabase Auth)
NEXT_PUBLIC_SUPABASE_URL=your_supabase_url
NEXT_PUBLIC_SUPABASE_ANON_KEY=your_supabase_anon_key
```

4. Initialize the database schema:

```bash
npx prisma db push
```

5. Generate Prisma client:

```bash
npx prisma generate
```

6. Seed the database with sample data (optional):

```bash
npm run seed
# or
yarn seed
```

### Running the Development Server

```bash
npm run dev
# or
yarn dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser to see the application.

### Building for Production

```bash
npm run build
# or
yarn build
```

Then start the production server:

```bash
npm start
# or
yarn start
```

## Project Structure

```
techandaioverlords/
├── components/           # React components
│   ├── layout/           # Layout components (header, footer, etc.)
│   ├── newsletter/       # Newsletter signup components
│   ├── tools/            # Tools directory components
│   └── ui/               # Reusable UI components
├── lib/                  # Utility functions and helpers
│   ├── prisma.ts         # Prisma client instance
│   └── validators.ts     # Form validation schemas
├── pages/                # Next.js pages
│   ├── api/              # API routes
│   │   ├── subscribe.ts  # Newsletter subscription endpoint
│   │   ├── confirm.ts    # Email confirmation endpoint
│   │   └── tools/        # Tools API endpoints
│   ├── _app.tsx          # Custom App component
│   ├── index.tsx         # Landing page
│   └── tools/            # Tools directory pages
├── prisma/               # Prisma schema and migrations
│   ├── schema.prisma     # Database schema
│   └── seed.ts           # Database seeding script
├── public/               # Static assets
├── styles/               # Global styles
├── types/                # TypeScript type definitions
├── .env.local            # Local environment variables
├── next.config.js        # Next.js configuration
├── tailwind.config.js    # TailwindCSS configuration
└── tsconfig.json         # TypeScript configuration
```

## Key Features

### Newsletter Signup

The newsletter signup flow includes:

1. Form validation using Zod
2. Server-side validation and processing
3. Email confirmation via a secure token
4. Visual feedback throughout the process

### AI Tools Directory

The tools directory includes:

1. Categorized tool listings
2. Search functionality
3. Category filtering
4. Responsive grid layout
5. External links to tool websites

## Development Guidelines

### Coding Standards

- Use TypeScript for all code files
- Follow ESLint and Prettier configurations
- Include thorough comments for all non-obvious code
- Use named exports instead of default exports

### Component Structure

All components should follow this structure:

```tsx
// Import statements
import { FC } from 'react';
import { SomeProps } from '@/types';

// Types
interface ComponentProps {
  // Props definition
}

// Component
export const ComponentName: FC<ComponentProps> = ({ prop1, prop2 }) => {
  // Component logic

  return (
    // JSX
  );
};

// Add thorough comments explaining the component's purpose and usage
```

### API Routes

API routes should:

1. Include proper input validation
2. Return consistent response structures
3. Include appropriate error handling
4. Use HTTP status codes correctly

### Styling Guidelines

Follow the styling guidelines in the [Style Guide](./STYLE_GUIDE.md) document for consistent visual appearance.

## Testing

### Running Tests

```bash
npm test
# or
yarn test
```

### Test Structure

- Unit tests for utility functions
- Component tests for UI elements
- Integration tests for API routes
- End-to-end tests for key user flows

## Deployment

### Vercel Deployment

This Next.js application is optimized for deployment on Vercel:

1. Connect your GitHub repository to Vercel
2. Configure environment variables in the Vercel dashboard
3. Deploy the application

### Alternative Deployments

For other deployment options, build the application and deploy the `.next` directory to your hosting provider of choice.

## Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details.

## Acknowledgements

- [Next.js](https://nextjs.org/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Prisma](https://www.prisma.io/)
- [Supabase](https://supabase.io/)

## Documentation Structure

This master README will be expanded into sub-READMEs as the codebase is developed:

- `docs/INSTALLATION.md` - Detailed installation instructions
- `docs/API.md` - API documentation
- `docs/COMPONENTS.md` - Component documentation
- `docs/STYLING.md` - Style guide and Tailwind utilities
- `docs/DEPLOYMENT.md` - Deployment instructions
- `docs/TESTING.md` - Testing documentation

Each of these documents will provide in-depth information on their respective topics, while this master README serves as the central hub for project documentation.