# Copilot Instructions for proteus-question-development Repository

## Repository Overview

**Project**: Developing Interactive Reading Questions for Calculus  
**Type**: Calculus textbook checkpoint question project  
**Format**: PreTeXt XML (.ptx files) compiled to HTML and PDF  
**Size**: Small (~11MB, 18 .ptx source files, ~8,300 lines of content)  
**Primary Language**: PreTeXt XML
**Target Audience**: Undergraduate College Students taking Calculus

This repository contains an interactive reading questions for Calculus.

## Project Structure

### Root Files
- `project.ptx` - Main PreTeXt project manifest defining build targets (web, dev, pdf, runestone)
- `requirements.txt` - Python dependencies (pretext==2.36.0)
- `README.md` - Basic PreTeXt project documentation
- `codechat_config.yaml` - CodeChat previewer configuration (auto-generated)
- `.gitignore` - Excludes output/, published/, generated-assets/, node_modules/, logs/, .cache/, and most `.github/` files, while explicitly including `.github/copilot-instructions.md`.

### Relevant Source Structure (`source/`)
- `main.ptx` - Primary book source (full version)
- `chpt*-questions.ptx` - Questions for Calculus sections for a specific chapter
- `apex-sections/` - Contains the section of the Calculus book that need reading questions

### Configuration Files
- `publication/publication.ptx` - Publication settings for web/pdf output
- `publication/runestone.ptx` - Runestone platform-specific settings

### Assets
- `assets/figures/` - Images and GIFs for MATLAB desktop, UI elements (14 files, ~5.4MB total)
- `generated-assets/dynamic_subs/` - Auto-generated exercise substitutions

## Build Targets (from project.ptx)

Four targets defined:
1. **web** - HTML format, publication.ptx, output to `output/web/`, deploy to `interactive/`
2. **pdf** - PDF format using pdflatex, output to `output/print/debookrs.pdf`, deploy to `pdf/`
