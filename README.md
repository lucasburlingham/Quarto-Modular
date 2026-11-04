# 2005 Honda CRV Oil Change Documentation

A modular Quarto project for creating professional documentation about changing oil on a 2005 Honda CRV.

## Project Structure

```
Quarto/
├── _quarto.yml                 # Main Quarto project configuration
├── assets/
│   ├── project-config.yml      # Project components metadata
│   └── people.yaml              # Shared people/signatory data
├── styles.css                  # Custom CSS styling
├── documents/
│   ├── index.qmd              # Master document that imports templates
│   └── TestDocument.qmd       # Additional master document example
├── templates/
│   ├── 01-cover-sheet.qmd     # Cover sheet
│   ├── 02-toc.qmd             # Table of contents
│   ├── 03-signature-document.qmd # Approval and signature page
│   ├── 04-oil-change-guide.qmd # Main content - oil change instructions
│   ├── appendix-a.qmd         # Appendix A - Parts and tools checklist
│   ├── appendix-b.qmd         # Appendix B - Maintenance schedule
│   └── signature-template.qmd # Reusable signature markup template
├── README.md                  # This file
└── _output/                   # Rendered output files
```

## File Descriptions

### Configuration Files
- **_quarto.yml** - The primary Quarto project configuration. Controls output formats, styling, and document behavior
- **assets/project-config.yml** - YAML metadata file documenting the project structure and components
- **assets/people.yaml** - Shared people and selected signatory database
- **styles.css** - Custom CSS styling for professional appearance

### Document Components
1. **01-cover-sheet.qmd** - Title page with document metadata
2. **02-toc.qmd** - Table of contents page
3. **03-signature-document.qmd** - Approval signatures and authorization checklist
4. **04-oil-change-guide.qmd** - Complete step-by-step oil change instructions with:
   - Safety precautions
   - Tools and materials list
   - Detailed step-by-step procedure
   - Troubleshooting guide
   - Maintenance records table
5. **appendix-a.qmd** - Parts and tools checklist with supplier information
6. **appendix-b.qmd** - Complete maintenance schedule and recommended services

### Main Document
- **documents/index.qmd** - Master document that imports all template components using Quarto's `{{< include >}}` directive
- **documents/TestDocument.qmd** - Secondary master document example using the same template library

## Building the Document

### Prerequisites
- Quarto installed (visit https://quarto.org/docs/get-started/)
- Optional: Pandoc for PDF output

### Build Commands

**Render to HTML:**
```bash
quarto render documents/index.qmd --to html
```

**Render to PDF:**
```bash
quarto render documents/index.qmd --to pdf
```

**Render to all formats:**
```bash
quarto render documents/index.qmd
```

**Preview in browser (live reload):**
```bash
quarto preview documents/index.qmd
```

**Render entire project:**
```bash
quarto render
```

## Output

After rendering, output files will be generated in the `_output/` directory:
- `index.html` - HTML version (recommended for web viewing)
- `index.pdf` - PDF version (recommended for printing)

## Customization Guide

### Modifying Content

1. **Edit individual sections:**
   - Open the respective template `.qmd` file in the `templates/` folder (e.g., `templates/04-oil-change-guide.qmd`)
   - Make your changes
   - Save the file

2. **Add new sections:**
   - Create a new `.qmd` file in `templates/`
   - Add content in Quarto markdown format
   - Include it in `documents/index.qmd` using: `{{< include ../templates/your-file.qmd >}}`

3. **Reorder sections:**
   - Edit `documents/index.qmd` and rearrange the `{{< include >}}` directives

### Styling Customization

Edit `styles.css` to customize:
- Colors
- Fonts
- Spacing
- Table appearance
- Links and other elements

Modify `_quarto.yml` to adjust:
- Theme (change `cosmo` to other Quarto themes: `default`, `journal`, `lux`, `darkly`, etc.)
- Table of contents position
- Number formatting
- Margins and layout

### Update Author Information

Edit `_quarto.yml`:
```yaml
metadata:
  author: "Lucas Burlingham"
  date-modified: today
```

Or in `documents/index.qmd` YAML header:
```yaml
author: "Lucas Burlingham"
date: today
```

## Using YAML Configuration

This project demonstrates two ways to manage configuration:

### Method 1: _quarto.yml (Recommended)
The `_quarto.yml` file is the primary configuration for the entire project. It includes:
- Project metadata
- Output format settings
- Build options
- CSS theme selection

### Method 2: assets/project-config.yml
The `assets/project-config.yml` file provides an alternative way to document the project structure and components in a human-readable format.

## Output Formats

### HTML
- Professional appearance with navigation
- Suitable for web publishing
- Self-contained (all resources embedded)
- Responsive design

### PDF
- Suitable for printing
- Professional formatting with proper margins
- Page numbers and table of contents
- Bookmarks for navigation

## Tips and Best Practices

1. **Work Modularly**: Keep each section in its own file for easy editing
2. **Version Control**: Use Git to track changes to all `.qmd` files
3. **Testing**: Render frequently during editing to catch formatting issues
4. **Images**: Store images in a `figures/` or `images/` directory
5. **Links**: Use relative paths for linking between files
6. **Comments**: Use HTML comments `<!-- comment -->` in QMD files for notes

## Quarto Markdown Features

This project uses standard Quarto markdown, which supports:
- **Formatted text**: *italic*, **bold**, ***bold italic***
- **Headers**: # H1, ## H2, ### H3, etc.
- **Lists**: Unordered and ordered lists
- **Tables**: Markdown tables with alignment
- **Code**: Inline `code` and code blocks with syntax highlighting
- **Links**: [Text](url)
- **Images**: ![Alt text](path/to/image.png)
- **Dividers**: Use `---` for page breaks or `\pagebreak` for PDF

## Troubleshooting

### Issue: Changes not appearing
- Clear the `_output/` directory: `rm -r _output/`
- Render again: `quarto render`

### Issue: PDF rendering fails
- Ensure Pandoc is installed
- Check for special characters in content
- Try HTML output first to identify markup issues

### Issue: Styling not applied
- Check that `styles.css` path is correct in `_quarto.yml`
- Clear browser cache when viewing HTML
- Verify CSS syntax

## Additional Resources

- [Quarto Documentation](https://quarto.org/docs/guide/)
- [Quarto Markdown Reference](https://quarto.org/docs/authoring/markdown-basics.html)
- [Quarto Websites and Books](https://quarto.org/docs/publishing/create-website.html)
- [Quarto Output Formats](https://quarto.org/docs/output-formats/all-formats.html)

## License and Usage

This template is provided as-is for creating technical documentation. Feel free to customize for your needs.

---

**Last Updated**: November 4, 2026
**Version**: 1.0
