# Project Context

## Purpose
Fairyflight is an online marketplace that connects aviation operators with business customers looking for discounted empty-leg flights. Operators can sell seats on empty legs that are costly to operate, while customers can find attractive flights at lower prices. The goal is to create value for both sides of the marketplace.

## Tech Stack
- Node.js
- TanStack Start (React framework)
- TanStack DB, using its collection support
- PostgreSQL
- Drizzle ORM for typed schema definitions and database access
- Chakra UI
- `react-icons`
- Docker
- Dokploy for deployment
- Payment integrations are required; provider not yet specified
- Keycloak for authentication and identity management

## Project Conventions

### Code Style
- Use Prettier for formatting.
- Use TSLint for linting.
- Follow clean-code practices.
- Use Husky to run pre-commit checks for linting, formatting, and related tests.
- For frontend code, keep one component per file. Colocate its test and any CSS or images used exclusively by that component.
- Build the UI mobile-first and make it responsive across screen sizes.
- Use Chakra UI for UI components and `react-icons` for icons.

### Architecture Patterns
- Follow Clean Architecture.
- Domain-driven design is not required.
- Prioritize data protection throughout the system.
- Use Drizzle to define the PostgreSQL schema and access the database with typed TypeScript code.
- Use TanStack DB collections where appropriate for client-side data access and synchronization.
- Use Keycloak as the authentication provider. Support single sign-on through identity providers configured in Keycloak, with providers such as Google, Apple, and Microsoft as intended options.

### Testing Strategy
- Use test-driven development: write tests before implementation.
- Run tests in the pull-request pipeline.
- Run end-to-end tests before deploying from the development environment to production.

### Git Workflow
- Use Commitlint with Conventional Commits 1.0.0: https://www.conventionalcommits.org/en/v1.0.0/
- Husky runs the configured lint, formatting, and related-test checks before commits.
- Branching strategy is not yet specified.

## Domain Context
- An empty leg is a flight leg that an aviation operator needs to operate without its usual paying passenger itinerary; Fairyflight lets operators offer seats on such flights.
- Operators supply available flights and sell seats.
- Business customers use the marketplace to find and book lower-cost flights.
- The marketplace needs to support both operator-facing and customer-facing workflows.

## Important Constraints
- Strong data protection is a top-level requirement.
- Payment integrations are required.
- The specific data-protection, regulatory, and payment-provider requirements have not yet been specified.

## External Dependencies
- Keycloak provides authentication and can broker sign-in with configured identity providers, including intended SSO options such as Google, Apple, and Microsoft.
- An external API for aviation operators is required.
- The system may also need to integrate with existing empty-leg services or systems, such as LEON or Avinode. The exact providers and integration approach are not yet specified.
- A payment provider must be selected for payment integrations.
