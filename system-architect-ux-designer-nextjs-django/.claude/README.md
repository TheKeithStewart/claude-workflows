# Claude Code Workflow System

This directory contains a comprehensive development workflow system designed for Next.js/Django applications, implementing an agent-based development process that covers the entire product lifecycle from requirements analysis to feature delivery.

## Directory Structure

```
.claude/
├── agents/                         # Specialized agent persona definitions
│   ├── product-manager.md              # User story creation, backlog management
│   ├── system-architect.md             # Technical planning and architecture
│   ├── ux-designer.md                  # User experience design and strategy
│   ├── staff-ux-designer.md            # Design review and quality assurance
│   ├── ui-ux-prototyping-specialist.md # High-fidelity mockups and prototypes
│   ├── senior-software-engineer.md     # Full-stack implementation
│   ├── qa-automation-engineer.md       # Playwright testing and automation
│   └── engineering-manager.md          # Code review and technical leadership
└── commands/                      # Workflow command scripts
    ├── backlog-planning.md             # Requirements → GitHub Issues
    ├── design-phase.md                 # Technical planning → UX design
    ├── prototype-creation.md           # High-fidelity mockups → prototypes
    ├── implementation-phase.md         # TDD implementation → code review
    ├── delivery-phase.md               # PR creation → merge → cleanup
    ├── workflow-status.md              # Progress monitoring and reporting
    └── workflow-utils.md               # Maintenance and utility functions
```

## Workflow Overview

The system provides **flexible workflow paths** depending on your needs:

### 1. Backlog Planning Workflow
**Purpose**: Convert requirements into structured GitHub Issues
- **Product Manager** analyzes requirements and asks clarifying questions
- Creates epics and user stories with comprehensive acceptance criteria
- Applies MoSCoW prioritization and dependency mapping
- Generates GitHub Issues with proper labels and organization

### 2. Design & Planning Workflow
**Purpose**: Technical planning and UX design for existing issues
- **System Architect** creates technical plan with architecture decisions
- **Engineering Manager** reviews technical approach for approval
- **UX Designer** creates wireframes and user experience strategy
- **Staff UX Designer** reviews designs for quality and compliance

### 3. High-Fidelity Prototype Workflow
**Purpose**: Create pixel-perfect mockups and interactive prototypes
- **UX Designer** establishes design strategy and user experience goals
- **UI/UX Prototyping Specialist** creates detailed mockups and prototypes
- **Staff UX Designer** validates design quality and accessibility compliance
- Delivers production-ready specifications for development handoff

### 4. Implementation Workflow
**Purpose**: Full-stack development with comprehensive quality assurance
- **Senior Software Engineer** implements features using TDD approach
- **QA Automation Engineer** creates comprehensive Playwright test coverage
- **Engineering Manager** conducts thorough code review
- Ensures 90%+ test coverage and accessibility compliance

### 5. Delivery Workflow
**Purpose**: PR management, CI resolution, and production deployment
- Creates comprehensive pull requests with documentation
- Monitors CI pipeline and resolves any issues
- Coordinates stakeholder review and merge process
- **Product Manager** identifies follow-up work for future backlog

## Agent Personas

### Product Manager
- **Role**: User story creation, backlog management, requirements analysis
- **Expertise**: Stakeholder coordination, epic breakdown, MoSCoW prioritization, GitHub Issues
- **Deliverables**: Structured epics and user stories with comprehensive acceptance criteria
- **Quality Focus**: Business value alignment, user need validation, backlog organization

### System Architect
- **Role**: Technical planning and architecture decisions
- **Expertise**: Full-stack architecture, database design, API design, security, performance analysis
- **Deliverables**: Comprehensive technical plans with implementation guidance and risk assessment
- **Quality Focus**: Scalability, maintainability, security compliance, technical feasibility

### UX Designer
- **Role**: User experience design and strategy
- **Expertise**: UX research, wireframing, user flows, accessibility (WCAG 2.1 AA), design systems
- **Deliverables**: User experience strategy, wireframes, and conceptual design solutions
- **Quality Focus**: User needs, accessibility compliance, design system consistency

### Staff UX Designer
- **Role**: Design review and quality assurance
- **Expertise**: Advanced UX strategy, design governance, accessibility auditing, quality standards
- **Deliverables**: Comprehensive design review feedback and approval decisions
- **Quality Focus**: Design standards enforcement, accessibility compliance, cross-platform consistency

### UI/UX Prototyping Specialist
- **Role**: High-fidelity mockups and interactive prototypes
- **Expertise**: Pixel-perfect design, interactive prototyping, design system implementation, developer handoff
- **Deliverables**: Production-ready mockups, clickable prototypes, comprehensive design specifications
- **Quality Focus**: Visual accuracy, interaction design, accessibility implementation, developer clarity

### Senior Software Engineer
- **Role**: Full-stack implementation (Next.js frontend + Django backend)
- **Expertise**: React/TypeScript, Django/Python, TDD, performance optimization, security implementation
- **Deliverables**: Production-ready full-stack code with comprehensive test coverage
- **Quality Focus**: Code quality, performance optimization, security compliance, maintainability

### QA Automation Engineer
- **Role**: Playwright E2E testing and test automation strategy
- **Expertise**: Playwright automation, cross-browser testing, accessibility testing, performance validation
- **Deliverables**: Comprehensive E2E test suites with accessibility and performance validation
- **Quality Focus**: Test coverage, cross-browser compatibility, accessibility compliance, automation reliability

### Engineering Manager
- **Role**: Code review and engineering standards enforcement
- **Expertise**: Code quality assessment, technical leadership, risk evaluation, team coordination
- **Deliverables**: Comprehensive code review feedback and technical approval decisions
- **Quality Focus**: Engineering standards, technical debt management, security compliance, maintainability

## Quality Standards

**Code Quality Requirements:**
- ESLint/Prettier compliance (frontend), Black/flake8 compliance (backend)
- TypeScript strict mode with comprehensive type definitions
- 90%+ test coverage with unit, integration, and E2E tests
- Cross-browser compatibility verification across supported platforms
- Performance optimization with Core Web Vitals compliance

**Accessibility Requirements:**
- WCAG 2.1 AA compliance for all UI components and interactions
- Keyboard navigation support with proper focus management
- Screen reader compatibility with semantic HTML and ARIA labels
- Color contrast compliance with alternative visual indicators
- Touch target sizing appropriate for mobile device interaction

**Security Requirements:**
- OWASP compliance with comprehensive input validation and output sanitization
- Authentication and authorization implementation across full stack
- SQL injection prevention through proper ORM usage and parameterized queries
- XSS and CSRF protection with appropriate middleware and security headers
- Sensitive data encryption and secure storage practices

## Usage Instructions

### Workflow Command Usage

**For Backlog Planning:**
```
"Please analyze and create a backlog for: user dashboard with analytics and reporting"
```

**For Technical Planning and UX Design:**
```
"Please analyze and fix the GitHub issue: #123"
```

**For High-Fidelity Prototypes:**
```
"Create high-fidelity mockups and interactive prototypes for: GitHub issue #123"
```

**For Feature Implementation:**
```
"Please analyze the implementation plan and implement the feature for GitHub issue: #123"
```

**For Delivery Management:**
```
"Review changes on the given PR and prepare it for merging"
```

**For Workflow Monitoring:**
```
"Show the current status of all active workflows"
```

### Agent Coordination Features
- **Automatic Context Sharing**: Agents receive comprehensive context from previous workflow phases
- **Quality Gate Enforcement**: Each phase must meet quality standards before proceeding to the next
- **Iterative Refinement**: Built-in feedback loops ensure deliverables meet approval criteria
- **Cross-Agent Communication**: Seamless handoffs between specialized agents throughout the workflow
- **Stakeholder Integration**: Clear communication and approval checkpoints with project stakeholders

## Project Integration

### Technology Stack Support
- **Next.js Frontend**: React component development, TypeScript implementation, performance optimization
- **Django Backend**: REST API development, database design, security implementation, background job processing
- **Testing Frameworks**: Jest + React Testing Library (frontend), Django TestCase (backend), Playwright (E2E)
- **Code Quality**: ESLint/Prettier (frontend), Black/flake8/isort (backend), pre-commit hooks
- **GitHub Integration**: Issue tracking, PR management, CI/CD pipeline integration

### Document Organization
**Template Files** (`/templates/` directory):
- `technical-plan-template.md` - Architecture planning and implementation guidance
- `design-document-template.md` - Multi-option design documentation with specifications
- `implementation-log-template.md` - Development progress and decision tracking
- `review-feedback-template.md` - Structured feedback and iteration management

**Working Documents** (`/plans/issue-{number}-{description}/` directories):
- `technical-plan.md` - Technical architecture and implementation strategy
- `designs.md` - Design options, specifications, and stakeholder selections
- `implementation-log.md` - Development progress, decisions, and technical notes
- `review-feedback.md` - Review cycles, feedback resolution, and approval tracking
- `assets/` - Design assets organized by type (mockups, wireframes, prototypes)

## Key Benefits

### Development Efficiency
- **Structured Process**: Clear workflow paths from requirements to delivery
- **Agent Specialization**: Domain experts handle their areas of expertise
- **Quality Automation**: Built-in quality gates prevent issues from propagating
- **Context Preservation**: Comprehensive documentation maintains project knowledge

### Quality Assurance
- **Comprehensive Testing**: Unit, integration, and E2E test coverage with accessibility validation
- **Code Standards**: Automated linting, formatting, and type checking across the stack
- **Security Focus**: Built-in security reviews and OWASP compliance verification
- **Performance Monitoring**: Core Web Vitals tracking and optimization requirements

### Stakeholder Value
- **Clear Communication**: Regular updates and approval checkpoints throughout development
- **Predictable Outcomes**: Quality gates ensure consistent deliverable standards
- **Risk Mitigation**: Early identification and resolution of technical and design issues
- **Documentation Excellence**: Comprehensive project knowledge for future maintenance and enhancement

This comprehensive workflow system transforms development from ad-hoc processes into a systematic, quality-focused approach that delivers consistent results while maintaining efficiency and stakeholder satisfaction.