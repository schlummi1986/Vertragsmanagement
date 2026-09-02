# CLAUDE.md - Project Guidelines for Enterprise Contract Management System

## Project Overview
This repository contains the architecture, documentation, data models, and codebase for an Enterprise Contract Management System ("Vertragsmanagement 2.0"). The project aims to centralize contract lifecycle management, automated metadata extraction (OCR/AI), deadline tracking, and compliance enforcement.

---

## Language & Communication
- **Primary Documentation & UI Language:** German (Deutsch). All user-facing text, comments, and architectural documentations should be written in clean, clear German unless technical standards dictate English (e.g., code, API schemas, commit messages).
- **Tone:** Professional, structured, enterprise-grade (McKinsey/Gartner level analysis).

---

## Technical Standards & Stack Guidelines

### Code & Architecture
- **Coding Style:** Clean Architecture, SOLID principles, highly modular and readable code.
- **Languages / Frameworks:**
  - Frontend: TypeScript, Next.js (React), Tailwind CSS
  - Backend / APIs: Node.js / TypeScript or Python (FastAPI/Supabase)
  - Database: PostgreSQL (with Prisma/Drizzle ORM) or Supabase
  - Low-Code / Microsoft Stack (Alternative/Integration): Power Platform, SharePoint REST API, Microsoft Graph API
- **Document Processing & AI:** Integration via OpenAI/Claude API or Tesseract OCR for PDF metadata extraction (dates, parties, contract value, termination clauses).

### Data & Security Standards
- **GDPR / DSGVO & eIDAS:** Strict data protection compliance, role-based access control (RBAC), and full audit trail logging for all contract access and modifications.
- **Data Validation:** Strict schema validation (e.g., Zod, Pydantic) for all contract inputs, metadata fields, and API payloads.

---

## Repository Structure & Conventions

```
├── docs/                      # Architectural decisions, RFCs, and user guides
│   ├── 00_requirements_and_context.md
│   ├── architecture-comparison.md
│   ├── data-model.md
│   └── security_and_compliance.md
├── src/                       # Application source code
│   ├── components/            # UI Components
│   ├── lib/                   # Utility functions, OCR/AI parsers
│   ├── server/                # API routes & database handlers
│   └── types/                 # TypeScript interfaces and type definitions
├── config/                    # Configuration schemas, Power Platform JSONs
└── tests/                     # Unit and integration tests
```

---

## Git & Workflow Rules

- **Commit Messages:** Follow [Conventional Commits](https://www.conventionalcommits.org/):
  - `feat:` for new features
  - `fix:` for bug fixes
  - `docs:` for documentation updates
  - `refactor:` for code restructuring
  - `chore:` for build/maintenance tasks
- **Branching Strategy:** Use feature branches (`feature/<feature-name>`, `docs/<doc-topic>`).
- **Safety First:**
  - Never commit credentials, API keys, or `.env` files.
  - Always respect `.gitignore`.
  - Avoid breaking schema changes without migration scripts.

---

## Instructions for Claude Code

When working in this repository, always:
1. **Analyze First:** Check existing documentation in `docs/` before implementing new features or making structural recommendations.
2. **Modular Code:** Keep functions small, well-typed, and documented.
3. **Draft Documentation:** Ensure any architectural decisions or database schema changes are immediately reflected in the corresponding `docs/` files.
4. **Confirm Destructive Actions:** Ask before deleting or refactoring major components.
