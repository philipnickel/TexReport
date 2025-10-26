# LaTeX Report Template


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

