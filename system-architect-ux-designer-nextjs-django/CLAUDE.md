# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a full-stack web application combining Next.js frontend with Django backend, designed with system architecture and UX principles in mind.

**Architecture:**
- **Frontend**: Next.js (React with TypeScript)
- **Backend**: Django (Python) with Django REST Framework
- **Database**: PostgreSQL (production), SQLite (development)
- **Deployment**: Docker containers for both frontend and backend

## Project Structure

```
/
├── frontend/          # Next.js application
│   ├── src/
│   │   ├── app/       # Next.js app router pages
│   │   ├── components/# React components
│   │   ├── lib/       # Utilities and API clients
│   │   └── types/     # TypeScript type definitions
│   ├── public/        # Static assets
│   └── package.json
├── backend/           # Django application
│   ├── config/        # Django settings
│   ├── apps/          # Django applications
│   ├── requirements.txt
│   └── manage.py
└── docker-compose.yml # Multi-container setup
```

## Development Commands

### Frontend (Next.js)
```bash
cd frontend
npm install                 # Install dependencies
npm run dev                 # Start development server (port 3000)
npm run build              # Build for production
npm run start              # Start production server
npm run lint               # Run ESLint
npm run type-check         # Run TypeScript compiler
npm test                   # Run tests
```

### Backend (Django)
```bash
cd backend
pip install -r requirements.txt    # Install dependencies
python manage.py runserver         # Start development server (port 8000)
python manage.py migrate          # Apply database migrations
python manage.py makemigrations   # Create new migrations
python manage.py test             # Run tests
python manage.py collectstatic    # Collect static files
python manage.py createsuperuser  # Create admin user
```

### Full Stack Development
```bash
docker-compose up              # Start both frontend and backend
docker-compose up --build     # Rebuild and start containers
docker-compose down           # Stop all services
```

## API Integration

- Frontend communicates with backend via REST API at `http://localhost:8000/api/`
- Authentication handled via JWT tokens
- API client utilities located in `frontend/src/lib/api.ts`

## Database

- Development: SQLite database at `backend/db.sqlite3`
- Production: PostgreSQL (configured via environment variables)
- Run `python manage.py migrate` after pulling changes that include new migrations

## Environment Variables

### Frontend (.env.local)
```
NEXT_PUBLIC_API_URL=http://localhost:8000/api
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

### Backend (.env)
```
DEBUG=True
SECRET_KEY=your-secret-key
DATABASE_URL=sqlite:///db.sqlite3
CORS_ALLOWED_ORIGINS=http://localhost:3000
```

## Testing

- Frontend tests: Jest + React Testing Library
- Backend tests: Django's built-in testing framework
- E2E tests: Playwright (when implemented)

## Code Quality

- Frontend: ESLint + Prettier + TypeScript
- Backend: Black + isort + flake8
- Pre-commit hooks ensure code quality

## Development Workflow

This project follows a structured 19-step development workflow involving multiple specialized personas. The workflow ensures comprehensive planning, design, implementation, and review for all features.

### Workflow Overview

The development process follows these phases:
1. **Planning & Analysis** (Steps 1-5): Issue analysis, technical planning, plan review and iteration
2. **Design** (Steps 6-10): UI design, design review, stakeholder approval
3. **Implementation** (Steps 11-16): TDD implementation, quality assurance, code review
4. **Delivery** (Steps 17-19): PR creation, CI resolution, final review

### Key Documents

- **WORKFLOW.md**: Complete 19-step process documentation
- **PERSONAS.md**: Detailed agent personas and their responsibilities
- **Templates**: Document templates in `/templates/` directory
- **Scratchpads**: Working documents in `/scratchpads/` directory

### Personas Involved

- **System Architect**: Technical planning and architecture decisions
- **Senior UX Designer**: User experience design and prototyping
- **Staff UX Designer**: Design review and quality assurance
- **Senior Software Engineers**: Frontend and backend implementation
- **Engineering Manager**: Code review and engineering standards

### Starting a New Feature

To begin work on a GitHub issue using this workflow:

1. **Issue Analysis**: Read and understand the GitHub issue requirements
2. **Create Technical Plan**: System Architect creates plan in `/scratchpads/{issue-number}-technical-plan.md`
3. **Plan Review**: Get technical plan reviewed and approved
4. **Design (if UI changes)**: Create design options in `/scratchpads/{issue-number}-designs.md`
5. **Implementation**: Follow TDD approach with comprehensive testing
6. **Quality Assurance**: Ensure all tests pass, no lint issues, proper documentation
7. **Review & PR**: Code review, PR creation, and final approval

### File Organization

```
/
├── .claude/                 # Claude Code workflow system
│   ├── agents/             # Agent persona definitions
│   │   ├── product-manager.md
│   │   ├── system-architect.md
│   │   ├── ux-designer.md
│   │   ├── staff-ux-designer.md
│   │   ├── senior-software-engineer.md
│   │   ├── qa-automation-engineer.md
│   │   └── engineering-manager.md
│   └── commands/           # Workflow command scripts
│       ├── backlog-planning.md
│       ├── design-phase.md
│       ├── implementation-phase.md
│       ├── delivery-phase.md
│       ├── workflow-status.md
│       └── workflow-utils.md
├── WORKFLOW.md              # Complete workflow documentation
├── PERSONAS.md              # Agent personas and responsibilities
├── templates/               # Document templates
│   ├── technical-plan-template.md
│   ├── design-document-template.md
│   ├── implementation-log-template.md
│   └── review-feedback-template.md
├── scratchpads/            # Working documents for active issues
│   ├── {issue-number}-technical-plan.md
│   ├── {issue-number}-designs.md
│   ├── {issue-number}-implementation-log.md
│   └── {issue-number}-review-feedback.md
├── frontend/               # Next.js application
└── backend/                # Django application
```

### Quality Gates

Every deliverable must pass domain-specific quality gates:
- **Technical Plans**: Architecture soundness, security, performance, feasibility
- **Designs**: Usability, accessibility (WCAG 2.1 AA), design system compliance
- **Implementation**: 90%+ test coverage, lint-free, security compliant, performance optimized

### Commands for Quality Assurance

Before any PR creation, run these commands to ensure quality:

```bash
# Frontend quality checks
cd frontend
npm run lint                # ESLint checking
npm run type-check         # TypeScript type checking  
npm test                   # Unit tests
npm run build             # Production build test

# Backend quality checks
cd backend
python -m flake8          # Code linting
python -m black --check . # Code formatting check
python manage.py test     # Unit tests
python manage.py check    # Django system checks

# E2E tests (when implemented)
npx playwright test       # End-to-end tests
```

All quality checks must pass before requesting final PR review.

## Claude Code Workflow System

This project includes a comprehensive `.claude/` directory structure that defines the development workflow system:

### Agent System
- **Specialized Agents**: 7 persona-based agents with specific roles and capabilities
- **Agent Configuration**: Detailed agent definitions in `.claude/agents/` directory
- **Workflow Orchestration**: Intelligent agent coordination for complex development tasks

### Workflow Commands
- **backlog-planning**: Analyze requirements and create structured GitHub Issues with epics and user stories
- **design-phase**: Execute UI/UX design creation and review process
- **implementation-phase**: Manage TDD implementation with quality assurance
- **delivery-phase**: Handle PR creation, CI resolution, and final review
- **workflow-status**: Monitor active workflows and provide progress reports
- **workflow-utils**: Utility functions for workflow management and maintenance

### Getting Started with Workflow

**For Backlog Planning:**
Create structured user stories and GitHub Issues from requirements:
```
"Please analyze and create a backlog for: user dashboard with analytics and reporting"
```

**For Feature Development:**
Start the development workflow for existing GitHub issues:
```
"Start the development workflow for GitHub issue #123"
```
or
```
"I have this feature requirement: [description]. Please start the development workflow."
```

### Agent Capabilities
- **Product Manager**: User story creation, backlog management, requirements analysis, stakeholder coordination
- **System Architect**: Technical planning, architecture decisions, risk assessment
- **Senior UX Designer**: User experience design, prototyping, accessibility compliance
- **Staff UX Designer**: Design review, quality assurance, standards enforcement
- **Senior Software Engineer**: Full-stack implementation (Next.js/React frontend, Django/Python backend), testing, performance optimization
- **QA Automation Engineer**: Playwright E2E testing, test automation strategy, accessibility and performance validation
- **Engineering Manager**: Code review, quality standards, technical leadership

The workflow system automatically coordinates these agents through the 19-step process, ensuring comprehensive planning, design, implementation, and delivery with consistent quality standards.