# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

A markdown-based resume management utility that converts resume markdown files to PDF using the `md-to-pdf` library. Maintains bilingual resumes (English and Spanish).

## Commands

```bash
# Install dependencies (uses pnpm, not npm)
pnpm install

# Generate English resume PDF
pnpm resume

# Generate Spanish resume PDF
pnpm resume-es
```

## Architecture

```
resume.md / resume-es.md  →  md-to-pdf + config.ts  →  resume.pdf / resume-es.pdf
```

- **resume.md** - English resume source
- **resume-es.md** - Spanish resume source
- **config.ts** - PDF generation options (Legal paper format)
- Uses Puppeteer (headless Chromium) for PDF rendering

## Workflow

1. Edit the markdown files (`resume.md` or `resume-es.md`)
2. Run the corresponding script to regenerate the PDF
3. Both markdown and PDF files should be committed together
