# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Overview

This is a collection of specialized AI agent workflows designed for different project types and architectures. It provides tailored agent personas and command sets that leverage Claude's capabilities for various development scenarios.

**Purpose**: Curated sets of specialized agents, custom command workflows, and architecture-specific configurations for different tech stacks (Next.js + Django, React + Node.js, etc.).

## Repository Structure

```
/
├── README.md                    # Repository overview and purpose
├── {workflow-name}/             # Individual workflow directories
│   ├── CLAUDE.md               # Workflow-specific Claude guidance
│   ├── scratchpads/            # Working documents during development
│   │   ├── README.md           # File naming conventions and lifecycle
│   │   ├── {issue-number}-technical-plan.md
│   │   ├── {issue-number}-designs.md
│   │   ├── {issue-number}-implementation-log.md
│   │   └── {issue-number}-review-feedback.md
│   └── templates/              # Document templates for workflow phases
│       ├── technical-plan-template.md
│       ├── design-document-template.md
│       ├── implementation-log-template.md
│       └── review-feedback-template.md
└── CLAUDE.md                   # This file - repository-level guidance
```

## Available Workflows

### system-architect-ux-designer-nextjs-django/
A comprehensive full-stack development workflow combining Next.js frontend with Django backend, featuring:
- **Multi-phase Development Process**: Backlog planning → Design → Prototyping → Implementation → Delivery
- **Agent-based System**: 8 specialized personas (Product Manager, System Architect, UX Designer, etc.)
- **Quality Standards**: 90%+ test coverage, WCAG 2.1 AA compliance, OWASP security standards
- **Document Templates**: Structured templates for technical plans, design documents, implementation logs

## Workflow Architecture Pattern

Each workflow follows a consistent pattern:

### Agent System
- **Specialized Personas**: Role-based agents with specific capabilities and responsibilities
- **Agent Configuration**: Detailed agent definitions with expertise areas
- **Coordinated Workflow**: Agents work together through defined phases

### Document Management
- **Template System**: Standardized templates for each phase of development
- **Scratchpad Pattern**: Working documents that evolve through the development lifecycle
- **File Naming Convention**: `{issue-number}-{document-type}.md` for traceability

### Quality Assurance
- **Multi-role Review**: Different personas review from their expertise perspective  
- **Standards Enforcement**: Consistent quality criteria across all workflows
- **Documentation Trail**: Full audit trail of decisions and changes

## Working with Workflows

1. **Choose Appropriate Workflow**: Select based on project architecture and requirements
2. **Follow Established Patterns**: Use existing templates and naming conventions
3. **Respect Agent Roles**: Each persona has specific responsibilities and expertise areas
4. **Maintain Documentation**: Keep scratchpad documents updated throughout development
5. **Quality Standards**: Adhere to the quality benchmarks defined in each workflow

## Development Commands

No universal build/test commands as this is a documentation repository. Each workflow may contain specific application commands in their respective CLAUDE.md files.

## File Lifecycle Management

### Scratchpad Documents
- **Active Issues**: Maintained in workflow's `scratchpads/` directory
- **File Ownership**: Each document is owned by the creating persona
- **Review Process**: Other personas provide feedback but don't directly modify
- **Archival**: Completed issues moved to timestamped subdirectories

### Templates
- **Standardization**: Consistent structure across all workflow types
- **Evolution**: Templates updated based on lessons learned from implementations
- **Reusability**: Designed for adaptation to different project types