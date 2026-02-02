# PDF to Markdown Converter

A Python script that converts PDF documents into clean, well-formatted Markdown files with intelligent structure detection.

## What It Does

This script takes any PDF document and converts it to Markdown format while:

- **Automatically detecting headers** (H1, H2, H3) based on font size and styling
- **Preserving document structure** including bullets, numbered lists, and paragraphs
- **Removing page headers/footers** that repeat throughout the document
- **Fixing line breaks** by joining wrapped text and de-hyphenating split words
- **Formatting table of contents** with page numbers moved to the front
- **Converting Unicode to ASCII** including smart quotes, em dashes, and special symbols
- **Removing emojis** and non-standard characters

The result is a clean, readable Markdown file that's easy to edit, search, and process.

## Use Cases

### For Accessibility
- **Screen reader compatibility** - Markdown is much easier for blind/visually impaired users to navigate with screen readers than PDFs
- **Text-to-speech** - Clean text format works better with TTS engines
- **Braille displays** - Markdown converts more reliably to Braille than complex PDF layouts

### For AI & Machine Learning
- **Training data preparation** - Convert PDF documents into clean text for LLM training
- **RAG systems** - Prepare documents for Retrieval-Augmented Generation pipelines
- **Knowledge base creation** - Build searchable, parseable documentation from PDFs
- **AI assistant skills** - Create custom Claude/ChatGPT skills from PDF manuals and guides

### General Benefits
- **Massive file size reduction** - A 5MB PDF becomes a 100KB Markdown file
- **Version control friendly** - Track changes in Git with readable diffs
- **Easy editing** - Modify content without PDF editing software
- **Universal compatibility** - Markdown works everywhere (GitHub, documentation sites, note apps)
- **Search and grep** - Find text instantly without PDF viewer limitations

## Installation

Always use a venv.
```bash
git clone https://github.com/rubysash/pdf2md.git
python -m venv pdf2md
cd pdf2md
scripts\activate
```
Install the modules
```bash
python -m pip install pypdf
```


## Usage

```bash
python main.py input.pdf output.md
```

### Examples

Convert multiple PDFs in windows:
```bash
(pdf2md) D:\pdf2md>for %F in (*.pdf) do python main.py "%F" "%~nF.md"
```

## What Gets Converted

✅ **Preserves:**
- Document hierarchy (chapters, sections, subsections)
- Bullet points and numbered lists
- Paragraph structure
- Table of contents (reformatted for readability)

✅ **Cleans:**
- Repeating page headers and footers
- Hyphenated words split across lines
- Smart quotes → regular quotes
- Em/en dashes → standard dashes
- Emojis and special Unicode characters

✅ **Formats:**
- Headers as proper Markdown (`#`, `##`, `###`)
- Lists as Markdown bullets (`-`) or numbers (`1.`)
- Wrapped text joined into complete paragraphs

❌ **Does not preserve:**
- Images (not extracted)
- Tables (converted to plain text)
- Colors, fonts, styling
- Page numbers
- Multi-column layouts

## Example Output

**Before (PDF):**
```
CHAPTER ONE
Introduction to Pro-
gramming
This book will teach you...
```

**After (Markdown):**
```markdown
## CHAPTER ONE

### Introduction to Programming

This book will teach you...
```

## Requirements

- Python 3.7+
- pypdf library

## Why This Exists

PDFs are great for printing but terrible for:
- Editing
- Searching
- Accessibility
- Version control
- AI processing

Markdown solves all of these problems while maintaining readability and structure.

