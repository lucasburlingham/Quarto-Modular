# Quick Start Guide

## Getting Started in 3 Steps

### Step 1: Verify Quarto Installation
```bash
quarto --version
```

If Quarto is not installed, download from https://quarto.org/docs/get-started/

### Step 2: Render Your Document
Navigate to the project directory and run:

```bash
# Render to HTML
quarto render documents/index.qmd --to html

# Or render to PDF
quarto render documents/index.qmd --to pdf

# Or render to both formats
quarto render documents/index.qmd
```

### Step 3: Open Your Output
- **HTML**: Open `_output/index.html` in your web browser
- **PDF**: Open `_output/index.pdf` with your PDF viewer

---

## What You Get

Your rendered document includes:

### Structure
1. ✓ **Cover Sheet** - Professional title page
2. ✓ **Table of Contents** - Auto-generated navigation
3. ✓ **Signature Document** - Authorization and approval forms
4. ✓ **Complete Oil Change Guide** - Detailed step-by-step instructions
5. ✓ **Appendix A** - Parts and tools checklist
6. ✓ **Appendix B** - Maintenance schedule

### Features
- Professional styling with custom CSS
- Fully navigable table of contents
- Page breaks between sections
- Responsive design for web and print
- Mobile-friendly HTML output
- Print-optimized PDF output

---

## Editing the Document

### To Update Existing Sections
Edit the corresponding template file in `templates/`:
- `templates/01-cover-sheet.qmd` - Change title/cover info
- `templates/03-signature-document.qmd` - Modify approval form
- `templates/04-oil-change-guide.qmd` - Update procedures
- `templates/appendix-a.qmd` - Modify parts/tools list
- `templates/appendix-b.qmd` - Update maintenance schedule

### To Customize Styling
Edit `styles.css` to change:
- Colors
- Fonts
- Table appearance
- Link colors

### To Change Configuration
Edit `_quarto.yml` to modify:
- Theme
- Table of contents position
- Output margins
- Font size

---

## Live Preview

For real-time preview while editing:

```bash
quarto preview index.qmd
```

This will open a preview in your browser and automatically refresh when you save changes.

To preview the main document, run:
```bash
quarto preview documents/index.qmd
```

---

## File Organization

```
├── assets/
│   ├── people.yaml             ← Shared people data
│   └── project-config.yml      ← Project metadata YAML
├── documents/
│   ├── index.qmd              ← Main master document
│   └── TestDocument.qmd       ← Secondary master document
├── templates/
│   ├── 01-cover-sheet.qmd     ← Edit cover page
│   ├── 02-toc.qmd             ← Table of contents
│   ├── 03-signature-document.qmd ← Edit signatures/approvals
│   ├── 04-oil-change-guide.qmd ← Edit main guide
│   ├── appendix-a.qmd         ← Edit parts/tools list
│   ├── appendix-b.qmd         ← Edit maintenance schedule
│   └── signature-template.qmd ← Reusable signature template
├── _quarto.yml                ← Project configuration
├── styles.css                 ← Styling configuration
└── _output/                   ← Generated output (after render)
    ├── index.html
    └── index.pdf
```

---

## Common Tasks

### Change Author Name
Edit `_quarto.yml`:
```yaml
metadata:
  author: "Lucas Burlingham"
```

### Change Document Title
Edit `documents/index.qmd`:
```yaml
title: "Your New Title"
```

### Add a New Section
1. Create new file in `templates/` such as `05-new-section.qmd`
2. Add to `documents/index.qmd`:
   ```
   {{< include ../templates/05-new-section.qmd >}}
   ```
3. Render document

### Change Colors
Edit `styles.css` and update colors:
- Change `#3498db` to your preferred color
- Affects headings, tables, links, etc.

---

## Troubleshooting

**Q: I get a "quarto not found" error**
- A: Install Quarto from https://quarto.org/docs/get-started/

**Q: HTML renders but styling looks wrong**
- A: Clear browser cache (Ctrl+Shift+Delete) and refresh

**Q: PDF generation fails**
- A: Try HTML first. If that works, check for special characters in content.

**Q: Changes don't appear in output**
- A: Run `quarto render` instead of just opening the `.qmd` file

---

## Next Steps

1. ✓ Render the document successfully
2. Edit sections with your specific information
3. Update signature fields with actual approval process
4. Customize colors/styling to match your branding
5. Share the final PDF or HTML with stakeholders

---

**For detailed documentation, see README.md**
