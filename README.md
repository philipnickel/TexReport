# LaTeX Report Template

A clean, professional LaTeX template for academic reports, technical documentation, and project write-ups. This template is designed to be easily customizable and includes modern formatting with proper document structure.

## Features

- Clean and professional design
- Modular structure for easy customization
- Configured for biblatex with biber backend
- Custom headers and footers
- Code listing support with syntax highlighting
- Support for figures, tables, and mathematical equations
- Subfile support for better organization
- Pre-configured for A4 paper size

## Quick Start

### Prerequisites

You need a LaTeX distribution installed on your system:
- **Windows**: [MiKTeX](https://miktex.org/) or [TeX Live](https://www.tug.org/texlive/)
- **macOS**: [MacTeX](https://www.tug.org/mactex/)
- **Linux**: TeX Live (usually available in package manager)

### Compilation

#### Using Make (Recommended)

```bash
# Compile the document
make

# Clean auxiliary files
make clean

# Clean everything including PDF
make cleanall
```

#### Manual Compilation

```bash
pdflatex main.tex
biber main
pdflatex main.tex
pdflatex main.tex
```

## Customization

### Basic Configuration

Edit `config.tex` to customize your document:

```latex
% Document information
\newcommand{\reportTitle}{Your Report Title}
\newcommand{\reportSubtitle}{Optional Subtitle}
\newcommand{\reportCourse}{Course Name/Number}
...
```

### Title Page

The title page is in `frontmatter/titlepage.tex`. You can:
- Modify the layout
- Add/remove author fields
- Include institutional logos
- Change the styling

### Document Structure

The main document (`main.tex`) includes sections from the `sections/` directory:

```latex
\chapter{Introduction}
\subfile{sections/01_introduction}

\chapter{Methodology}
\subfile{sections/02_methodology}
...
```

Add or remove chapters as needed for your report.

## Directory Structure

```
.
├── README.md                  # This file
├── main.tex                   # Main document file
├── config.tex                 # Configuration and custom commands
├── Makefile                   # Build automation
├── setup/                     # LaTeX setup files
│   ├── packages.tex          # Package imports
│   ├── formatting.tex        # Page layout and formatting
│   ├── commands.tex          # Custom commands
│   └── listings.tex          # Code listing configuration
├── frontmatter/              # Front matter files
│   ├── titlepage.tex         # Title page
│   └── abstract.tex          # Abstract (optional)
├── sections/                 # Content sections
│   ├── 01_introduction.tex
│   ├── 02_methodology.tex
│   ├── 03_results.tex
│   └── 04_conclusion.tex
├── appendices/               # Appendices
│   └── appendix_a.tex
├── figures/                  # Images and figures
│   └── example_figure.pdf
└── references.bib            # Bibliography database
```

## Adding Content

### Sections

Create new `.tex` files in the `sections/` directory and include them in `main.tex`:

```latex
\chapter{Your Chapter Name}
\subfile{sections/your_section}
```

### Figures

Place image files in the `figures/` directory and reference them:

```latex
\begin{figure}[H]
    \centering
    \includegraphics[width=0.8\textwidth]{figures/your_image.pdf}
    \caption{Your caption here}
    \label{fig:your_label}
\end{figure}
```

### References

Add BibTeX entries to `references.bib` and cite them in your document:

```latex
As shown by \textcite{AuthorYear}, ...
```

### Code Listings

Include code with syntax highlighting:

```latex
\begin{lstlisting}[language=Python, caption={Your caption}]
def example_function():
    return "Hello, World!"
\end{lstlisting}
```

## Customization Options

### Fonts

To change the main font, add to `setup/packages.tex`:

```latex
\usepackage{lmodern}  % Latin Modern
% or
\usepackage{times}    % Times
```

### Bibliography Style

Modify in `setup/packages.tex`:

```latex
\usepackage[backend=biber,style=numeric,maxcitenames=2]{biblatex}
```

Popular styles: `numeric`, `authoryear`, `ieee`, `apa`

### Page Margins

Adjust in `setup/formatting.tex`:

```latex
\usepackage[a4paper, left=3cm, right=3cm, top=3cm, bottom=3cm]{geometry}
```

## Troubleshooting

### Bibliography not showing up
- Make sure you run `biber main` after the first `pdflatex` run
- Check that `references.bib` has valid entries
- Ensure you've cited at least one reference with `\cite{...}`

### Missing packages
- Most LaTeX distributions include all required packages
- If a package is missing, use your distribution's package manager to install it

### Compilation errors
- Check the `.log` file for detailed error messages
- Common issues: missing `\end{...}`, unclosed braces, special characters

## License

This template is released into the public domain. Feel free to use, modify, and distribute as needed.

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests to improve this template.

## Acknowledgments

This template uses standard LaTeX packages and follows common academic formatting conventions.
