# GEMINI.md - Project Context

This document provides essential context for the AI assistant to understand and effectively work on this project.

## Project Overview

This project is a web application built with a modern JavaScript stack. The primary goal is to create a form-based application with a focus on type-safety, accessibility, and a clean user interface.

The architecture leverages server-side rendering (SSR) and potentially Incremental Static Regeneration (ISR) with Next.js. Authentication is handled by Clerk, and the database is managed by Prisma, with a local SQLite setup intended to be migrated to Supabase.

## Building and Running

The following commands are inferred from the project files.

### Services

*   **Supabase Local Server:** The `.mcp.json` file defines a command to run a local Supabase development server.
    ```bash
    npx -y @supabase/mcp-server-supabase --project-ref=mzcltskhvnvmenjmbmjp
    ```

### Main Application

**TODO:** No `package.json` or similar file was found, so the standard commands for building, running, and testing the application are not yet documented. Please add them here.

```bash
# Example commands:
# npm run dev
# npm run build
# npm test
```

## Development Conventions

The `.cursor/rules/globals.mdc` file outlines a strict set of development conventions that must be followed.

### Core Principles

*   **Analyze and Plan:** Before writing any code, thoroughly analyze the user's request, identify requirements and constraints, and create a detailed, step-by-step execution plan.
*   **Avoid Duplication (DRY):** Proactively check for existing features, components, or functions to prevent redundant implementations.
*   **Adhere to Structure:** Follow the established directory structure and naming conventions.
*   **Quality Control:** Verify the results of each task. If errors occur, isolate the cause, implement a fix, and verify the solution.
*   **Strict Adherence to Instructions:**
    *   Do not make any changes that are not explicitly instructed.
    *   Obtain approval before making any significant decisions or changes, especially regarding UI/UX or technology versions.
    *   Report any uncertainties or unexpected problems immediately.

### Rule Files

All rules defined in files under `./cursor/rules/dev-rules/*.mdc` must be strictly followed.

## Technology Stack

The technology stack is defined in `.cursor/rules/dev-rules/techstack.mdc`.

### Frontend

*   **Core:**
    *   Next.js (v14.2.25)
    *   React (v18.2.0)
    *   TypeScript (v5.2.2)
*   **UI Components & Styling:**
    *   **Shadcn/ui:** The primary component library.
    *   **Tailwind CSS** (v3.4.1): For utility-first styling.
    *   **Radix UI:** For accessible, headless UI components.
    *   **Lucide React** (v0.446.0): For icons.
*   **Authentication:**
    *   **Clerk** (v6.12.9)

### Backend

*   **Database:**
    *   **Prisma** (v5.11.0): Type-safe ORM.
    *   **Local SQLite:** For development, with plans to migrate to Supabase.

### Form Handling

*   **Server Actions:** Using Next.js Server Actions.
*   **Zod** (^3.x): For schema validation.

### Utilities

*   **date-fns** (v3.6.0): For date manipulation.

### Development Tools

*   **ESLint** (v8.49.0)
*   **Autoprefixer** (v10.4.15)
*   **PostCSS** (v8.4.30)

### Deployment

*   **Vercel:** Recommended deployment platform.
