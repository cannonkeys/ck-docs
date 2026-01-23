# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the CannonKeys documentation site, built with MkDocs using the Material theme. The site contains build guides, flashing instructions, and user documentation for CannonKeys mechanical keyboard products.

## Common Commands

```bash
# Install dependencies
pip install -r requirements.txt

# Run local development server (serves at http://127.0.0.1:8000)
mkdocs serve

# Build static site (outputs to site/ directory)
mkdocs build
```

## Repository Structure

- `docs/` - All markdown documentation files and assets
  - `images/` - Image assets organized by topic
  - `assets/` - Binary files like firmware .bin files
- `mkdocs.yml` - Site configuration and navigation structure
- `requirements.txt` - Python dependencies

## Adding/Editing Documentation

1. All documentation pages are markdown files in the `docs/` directory
2. Navigation structure is defined in `mkdocs.yml` under the `nav:` section
3. Images should be placed in `docs/images/` in an appropriate subdirectory
4. The site uses the `admonition` markdown extension for callout boxes

## Content Guidelines

- Documentation covers keyboard build guides, PCB flashing, firmware, and troubleshooting
- Target audience is keyboard enthusiasts building/modifying CannonKeys products
- Follow existing markdown formatting conventions in similar pages
