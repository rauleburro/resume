# CLAUDE.md

## Project Overview

This is a resume/CV management project that converts markdown files to PDF using the `md-to-pdf` library. The project maintains multiple resume variants for different roles and languages.

## Tech Stack

- **Runtime**: Node.js
- **Package Manager**: pnpm
- **Core Dependency**: `md-to-pdf` (v5.2.1) — uses Puppeteer/Chromium under the hood for PDF rendering
- **Config Format**: TypeScript (`config.ts`)

## Project Structure

```
resume/
├── resume.md            # Main resume (English, Senior Software Engineer)
├── resume-sre.md        # SRE/DevOps-focused resume (English)
├── resume-sre-es.md     # SRE/DevOps-focused resume (Spanish)
├── resume.pdf           # Compiled PDF output (tracked in git)
├── config.ts            # md-to-pdf config (Legal page format)
├── package.json         # Scripts and dependencies
├── pnpm-workspace.yaml  # Allows Puppeteer as built dependency
├── pnpm-lock.yaml       # Dependency lock file
├── Readme.md            # Minimal project description
└── .gitignore           # Excludes node_modules
```

## Commands

```bash
# Install dependencies
pnpm install

# Generate main resume PDF (uses Legal page format via config.ts)
pnpm run resume

# Generate Spanish SRE resume PDF (uses default page format)
pnpm run resume-sre-es
```

There is no script for `resume-sre.md` — it would need to be run manually:
```bash
npx md-to-pdf resume-sre.md
```

## PDF Configuration

`config.ts` exports a single config object setting the PDF page format to "Legal" (8.5" x 14"). This config is only used by the `resume` script (for `resume.md`). Other resume variants use the default md-to-pdf settings (Letter format).

## Resume File Conventions

- **Filename pattern**: `resume.md` for the main version, `resume-{variant}.md` for specialized versions, `resume-{variant}-{lang}.md` for non-English versions
- **Content structure**: Each resume follows this section order:
  1. Name heading (`# Name`)
  2. Contact info (email, phone, nationality)
  3. Profile summary
  4. Technologies list
  5. Skills
  6. Experience (reverse chronological, with company/dates/bullets)
  7. Languages
  8. Education (in some variants)
- **Markdown style**: Standard GitHub-flavored markdown with `###` for job titles and `####` for company/date lines

## Development Notes

- No test suite, linter, or CI/CD pipeline is configured
- PDF output files are committed to the repository
- Puppeteer requires system-level Chromium dependencies to run; `pnpm-workspace.yaml` allows Puppeteer's postinstall to build
- The main resume (`resume.md`) is the most current and comprehensive version; other variants may be older
