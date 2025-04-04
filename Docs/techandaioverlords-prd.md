# Product Requirements Document (PRD)

## 1. Project Overview

**Project Name:** TechAndAIOverlords

**Description:** An educational demo website showcasing AI tools across various categories and collecting newsletter signups. The site will serve as a demonstration project for documentation preparation rather than focusing on actual implementation.

**Primary Objective:** To create comprehensive documentation for a simple demo project that can be explained within an hour, demonstrating proper documentation practices for a vibe coding project.

**Target Audience:** Non-technical individuals interested in vibe coding and AI tools.

## 2. User Personas

### Primary Persona: AI Enthusiast
- Non-technical background but interested in AI technologies
- Looking to stay updated on AI trends through newsletters
- Seeking accessible information about useful AI tools

### Secondary Persona: Skool Students
- Learning about proper documentation practices
- Using this project as an educational reference
- Needs clear, well-commented documentation to understand the process

## 3. Core Features

### 3.1 Landing Page
- Hero section with engaging headline and subheading
- Newsletter signup form (collecting name, email, and optional reason for visit)
- Email confirmation process
- Visual elements reflecting the futuristic tech aesthetic shown in reference images

### 3.2 AI Tools Directory
- Categorized listing of AI tools across 6 categories:
  - AI Writing
  - AI Coding
  - AI Video Editing
  - AI Photo Editing
  - AI Task Management
  - AI Productivity

### 3.3 Search and Filtering
- Category-based filtering
- Text search functionality for finding specific tools
- Clear visual indicators for active filters

## 4. Technical Requirements

### 4.1 Architecture
- Next.js framework
- Clear separation between client and server functionality
- Server-side API endpoints for all database operations
- No direct client-to-database connections

### 4.2 Database
- Supabase as the database provider
- Prisma ORM for database interaction
- Use of `prisma db push` for schema deployment (not migrations)
- Schema defined in Prisma schema file

### 4.3 Security Considerations
- Server-side validation of all form inputs
- Secure handling of user data
- CSRF protection
- Rate limiting for form submissions

## 5. User Flows

### 5.1 Newsletter Signup Flow
1. User lands on homepage
2. User fills out the newsletter form (name, email, optional reason)
3. User submits the form
4. System validates inputs
5. System sends confirmation email
6. User confirms subscription via email link
7. System stores confirmed subscription in database via Prisma

### 5.2 AI Tools Discovery Flow
1. User navigates to tools section
2. User browses tools by category or uses search
3. User applies filters to narrow down results
4. User clicks on a tool of interest
5. User is directed to the external tool website

## 6. UI/UX Requirements

### 6.1 Visual Design
- Dark-themed background
- Vibrant neon accent colors, primarily blue/teal
- Futuristic geometric elements and abstract tech visuals
- Clean, modern typography
- Minimalist layout with focus on content

### 6.2 Responsive Design
- Fully responsive across desktop, tablet, and mobile devices
- Adaptive layouts for different screen sizes
- Touch-friendly interface elements for mobile users

## 7. Documentation Requirements

### 7.1 Code Documentation
- Thorough commenting throughout the codebase
- Clear explanation of component purposes and functions
- Documentation of state management and data flow
- API endpoint documentation

### 7.2 Setup Documentation
- Environment setup instructions
- Dependencies and installation guide
- Configuration steps for Supabase and Prisma
- Instructions for using `prisma db push` instead of migrations

### 7.3 Project Structure Documentation
- Folder organization explanation
- File naming conventions
- Component hierarchy

## 8. Timeline and Milestones

Given the immediate timeline requirement ("Now"), this section focuses on documentation phases rather than development:

1. **Initial Documentation Setup** - Day 1
   - Project overview
   - Technical requirements
   - Architecture diagrams

2. **Detailed Feature Documentation** - Day 1-2
   - User flows
   - API endpoints
   - Database schema

3. **UI/UX Documentation** - Day 2
   - Wireframes/mockups based on inspiration images
   - Style guide

4. **Final Review and Presentation Prep** - Day 2-3
   - Consolidate all documentation
   - Prepare presentation for Skool students

## 9. Success Metrics

For the documentation phase:
- Completeness of documentation
- Clarity of explanations
- Educational value for Skool students
- Ability to explain the entire project within one hour

## 10. API Endpoints



### Newsletter Subscription Endpoints
- `POST /api/subscribe` - Create new subscription
- `GET /api/confirm/:token` - Confirm subscription

### Tools Directory Endpoints
- `GET /api/tools` - Get all tools
- `GET /api/tools/search` - Search tools by name or description
- `GET /api/tools/filter` - Filter tools by category
- `GET /api/tools/categories` - Get all categories

### Search and Filtering Parameters
- `GET /api/tools/search?q=keyword` - Text search functionality
- `GET /api/tools/filter?category=categoryName` - Category filtering
- `GET /api/tools/search?q=keyword&category=categoryName` - Combined search and filtering

## 11. Prisma Schema

```prisma
// This is your Prisma schema file,
// learn more about it in the docs: https://pris.ly/d/prisma-schema

generator client {
  provider = "prisma-client-js"
}

datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}



model Subscriber {
  id         String   @id @default(uuid())
  email      String   @unique
  name       String
  reason     String?
  confirmed  Boolean  @default(false)
  token      String?  @unique
  createdAt  DateTime @default(now())
  updatedAt  DateTime @updatedAt
}

model Category {
  id        String   @id @default(uuid())
  name      String   @unique
  createdAt DateTime @default(now())
  updatedAt DateTime @updatedAt
  tools     Tool[]
}

model Tool {
  id          String   @id @default(uuid())
  name        String
  description String
  url         String
  categoryId  String
  category    Category @relation(fields: [categoryId], references: [id])
  createdAt   DateTime @default(now())
  updatedAt   DateTime @updatedAt
}
```

## 12. Prisma Setup Instructions

1. Install Prisma dependencies:
   ```bash
   npm install prisma @prisma/client
   ```

2. Initialize Prisma:
   ```bash
   npx prisma init
   ```

3. Configure the database connection in `.env`:
   ```
   DATABASE_URL="postgresql://username:password@localhost:5432/techandaioverlords"
   ```

4. Define schema as specified in section 11

5. Use `prisma db push` to apply schema to database:
   ```bash
   npx prisma db push
   ```

6. Generate Prisma client:
   ```bash
   npx prisma generate
   ```

7. Create a database utility file for Prisma instance:
   ```bash
   # Create a lib/prisma.ts file with PrismaClient setup
   ```