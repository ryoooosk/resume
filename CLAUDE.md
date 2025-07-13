# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Japanese resume management system built with Markdown, Jekyll, and Node.js.
The project maintains a professional resume in Markdown format, publishes it via GitHub Pages, and provides PDF export functionality with comprehensive Japanese text quality checking.

## Core Commands

### Development Commands

```bash
npm install          # Install dependencies
npm run lint         # Run textlint + markdownlint for document quality
npm run build:pdf    # Generate PDF from docs/README.md
```

### File Structure

- `index.md` - Main resume content (Japanese)
- `README.md` - Project documentation
- `_config.yml` - Jekyll configuration (minima theme)
- `pdf-configs/` - PDF generation configuration and styling
- `.textlintrc.json` - Japanese text linting rules (67+ rules)
- `.markdownlintrc.json` - Markdown formatting rules

## Architecture

### Document Processing Pipeline

1. **Source**: Markdown files (primarily `index.md`)
2. **Quality Control**: textlint (Japanese grammar) + markdownlint (formatting)
3. **Web Output**: Jekyll with minima theme → GitHub Pages
4. **PDF Output**: md-to-pdf with custom CSS styling

### Japanese Text Quality System

The project uses 67+ textlint rules specifically for Japanese writing:

- Grammar correction (助詞の重複, い抜き言葉, etc.)
- Spacing rules (半角/全角間のスペース)
- Punctuation consistency (句読点の統一)
- Professional writing standards
- Sentence length limits (max 150 characters)

### CI/CD Automation

- **Lint Workflow**: Automatic text quality checking on PRs
- **PDF Release**: Auto-generate PDF and create GitHub releases
- **GitHub Pages**: Automatic website deployment

## Development Guidelines

### Text Editing

- Always run `npm run lint` before committing changes
- Follow the extensive Japanese writing rules in `.textlintrc.json`
- Maintain consistency in Markdown formatting

### PDF Generation

- Uses A4 format with 30mm/20mm margins
- Custom CSS in `pdf-configs/style.css` for Japanese font optimization
- Page numbering in footer template

### Jekyll Configuration

- Uses minima theme for clean, professional appearance
- Minimal configuration in `_config.yml`
- GitHub Pages compatible

## Maintenance Notes

- The main content file is `index.md` (not `README.md`)
- PDF output is generated from `docs/README.md`
- Text quality rules are quite strict - expect multiple iterations for new content
- CI/CD workflows require Node.js 18 and Ubuntu environment
- **When modifying project structure or package.json**: Always update README.md to reflect changes in dependencies, scripts, or file organization
