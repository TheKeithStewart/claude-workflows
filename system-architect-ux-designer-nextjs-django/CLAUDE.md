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

This project uses a comprehensive agent-based development workflow that covers the entire product lifecycle from requirements analysis to feature delivery.

### File Organization

```
/
├── .claude/                 # Claude Code workflow system
│   ├── agents/             # Agent persona definitions
│   │   ├── product-manager.md
│   │   ├── system-architect.md
│   │   ├── ux-designer.md
│   │   ├── staff-ux-designer.md
│   │   ├── ui-ux-prototyping-specialist.md
│   │   ├── senior-software-engineer.md
│   │   ├── qa-automation-engineer.md
│   │   └── engineering-manager.md
│   └── commands/           # Workflow command scripts
│       ├── backlog-planning.md
│       ├── design-phase.md
│       ├── prototype-creation.md
│       ├── implementation-phase.md
│       ├── delivery-phase.md
│       ├── workflow-status.md
│       └── workflow-utils.md
├── templates/               # Document templates
│   ├── technical-plan-template.md
│   ├── design-document-template.md
│   ├── implementation-log-template.md
│   └── review-feedback-template.md
├── plans/                  # Issue-specific planning documents
│   ├── issue-{number}-{description}/
│   │   ├── technical-plan.md
│   │   ├── designs.md
│   │   ├── implementation-log.md
│   │   ├── review-feedback.md
│   │   └── assets/
│   │       ├── mockups/
│   │       ├── wireframes/
│   │       └── prototypes/
├── frontend/               # Next.js application
└── backend/                # Django application
```

### Quality Standards

- **Code Quality**: ESLint/Prettier (frontend), Black/flake8 (backend), TypeScript strict mode
- **Testing**: 90%+ test coverage with unit, integration, and E2E tests
- **Accessibility**: WCAG 2.1 AA compliance for all UI components
- **Performance**: Core Web Vitals optimization and API response benchmarks
- **Security**: OWASP compliance with comprehensive input validation

## Claude Code Workflow System

This project includes a comprehensive `.claude/` directory structure that defines the development workflow system:

### Agent System
- **Specialized Agents**: 8 persona-based agents with specific roles and capabilities
- **Agent Configuration**: Detailed agent definitions in `.claude/agents/` directory
- **Slash Commands for Workflow**: Commands that kick off the different phases of the implementation workflow

### Workflow Commands
- **backlog-planning**: Analyze requirements and create structured GitHub Issues with epics and user stories
- **design-phase**: Execute UI/UX design creation and review process
- **prototype-creation**: Create high-fidelity mockups and interactive prototypes
- **implementation-phase**: Manage TDD implementation with quality assurance
- **delivery-phase**: Handle PR creation, CI resolution, and final review

### Agent Capabilities
- **Product Manager**: User story creation, backlog management, requirements analysis, stakeholder coordination
- **System Architect**: Technical planning, architecture decisions, risk assessment
- **Senior UX Designer**: User experience design, prototyping, accessibility compliance
- **Staff UX Designer**: Design review, quality assurance, standards enforcement
- **UI/UX Prototyping Specialist**: High-fidelity mockups, interactive prototypes, pixel-perfect design specifications
- **Senior Software Engineer**: Full-stack implementation (Next.js/React frontend, Django/Python backend), testing, performance optimization
- **QA Automation Engineer**: Playwright E2E testing, test automation strategy, accessibility and performance validation
- **Engineering Manager**: Code review, quality standards, technical leadership

### Document Organization

All planning documents are organized by GitHub issue in the `plans/` directory:
- Each issue gets its own subdirectory: `issue-{number}-{description}/`
- Core documents: `technical-plan.md`, `designs.md`, `implementation-log.md`, `review-feedback.md`
- Design assets organized in `assets/` subdirectory with `mockups/`, `wireframes/`, and `prototypes/` folders

The workflow system coordinates these agents to ensure comprehensive planning, design, implementation, and delivery with consistent quality standards.