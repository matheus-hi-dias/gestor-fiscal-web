# Gestor Fiscal - Frontend Instructions

This file is the master instruction set for the Gestor Fiscal frontend. The project follows Open Spec, so always consult the relevant specification files before making UI or HTTP client decisions.

## Mission

Act as a Staff/Principal Frontend Engineer. Develop a high-performance, ergonomic, and accessible SaaS interface for accounting professionals. The UI must be highly responsive, resilient, and strictly aligned with the backend API contracts.

## Architecture

- Frontend stack: React, Vite, TypeScript, Tailwind CSS v4, React Hook Form, Zod.
- Data fetching and HTTP clients must be generated via OpenSpec. Do not write manual API call boilerplate unless strictly necessary.
- Separate business logic (custom hooks, services) from presentation components.
- State management should be localized when possible. Use Zustand or Context API only for global states (auth, theme, tenant context).

## Security and Compliance

- Store JWT tokens securely. Prevent XSS vulnerabilities by sanitizing any HTML input/output.
- The UI must clearly indicate the current Tenant (Escritório) context to prevent user confusion.
- Handle file uploads securely, validating MIME types on the frontend before sending to the S3 bucket via backend APIs.

## Theme, Styling and i18n

- Use Tailwind CSS v4 exclusively for styling.
- **Color Palette (Emerald & Slate):** The app uses a semantic color system that adapts to the OS native theme.
  - Light Mode: Background (`#f8fafc`), Surfaces (`#ffffff`), Text (`#0f172a`), Primary Brand (`#0d9488`).
  - Dark Mode: Background (`#0f172a`), Surfaces (`#1e293b`), Text (`#f8fafc`), Primary Brand (`#2dd4bf`).
- Do not hardcode Tailwind color classes like `bg-slate-50` or `text-slate-900` in components. Always use the semantic custom variables defined in `index.css` (e.g., `bg-background`, `bg-surface`, `text-body`, `bg-brand`).
- **Internationalization (i18n):** All hardcoded texts must be avoided. Use `react-i18next` for all strings to prepare the SaaS for multiple regions.

## Domain Rules

- Legal Compliance in UI: Forms handling Document Types must strictly enforce a minimum retention time of 5 years.
- Use Zod schemas to block submissions with `tempoArmazenamento < 5`.
- Form inputs must use `min={5}` and provide clear UI tooltips explaining the legal requirement.

## Quality Standards

- Strict TypeScript: Do not use `any`, `@ts-ignore`, or type suppression unless unavoidable and documented with a reason.
- No `//` explanatory comments in code outputs. Code must be self-documenting. Provide only the requested code.
- Components must be functional. Use hooks responsibly with exhaustive dependencies.
- Build for performance: avoid unnecessary re-renders in data-heavy tables (use memoization where appropriate).

## Workflow

When creating a feature:

1. Re-generate API clients via OpenSpec if the contract changed.
2. Define Zod schemas for form validations based on domain rules.
3. Build or compose standard UI components.
4. Implement the feature component and integrate with custom hooks.
5. Update `README.md` if new environment variables or setup steps are introduced.

## Agent-Friendly Execution

- Prefer small, verifiable changes over broad rewrites.
- Keep a short plan and update progress as you go.
- Inspect relevant files before editing.
- If instructions conflict, follow the most specific file.
- Validate exact files changed and summarize the outcome.

## Documentation

- Use Open Spec as the source of truth for API integration.
- Keep README focused on local execution (`npm run dev`), environment variables, and build scripts.
- Use Context7 MCP when consulting technical docs for React, Tailwind v4, Vite, or Zod.

## Review Stance

- If a change bypasses Zod validations for the 5-year rule, introduces `any` types, or uses outdated Tailwind v3 patterns, flag it as a blocker.
