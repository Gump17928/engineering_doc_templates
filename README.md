# Engineering Project Intake Templates

Reusable LaTeX templates that produce fillable PDF intake and scope-definition
forms for engineering support requests, before any project charge code or
Statement of Work (SOW) exists.

See [docs/Engineering_Project_Intake_Plan.md](docs/Engineering_Project_Intake_Plan.md)
for the full workflow these documents support, and
[docs/Engineering_Template_Design_Questions.md](docs/Engineering_Template_Design_Questions.md)
for the design decisions behind the template structure.

## What's here

| Document | Status | Folder |
|---|---|---|
| 1. Pre-Project Intake and Discovery Form | First release | `documents/01-intake-form/` |
| 2. Technical Discovery Addenda (mechanical, electrical, structural, systems, environmental) | Planned | `documents/02-discipline-addenda/` |
| 3. Requirements and Acceptance Worksheet | Planned | - |
| 4. Scope Definition Worksheet | First release | `documents/04-scope-definition/` |
| 5. Constraints, Risks, and Compliance Checklist | Planned | - |
| 6. Pre-SOW Scope Confirmation | Planned | - |
| 7. Center Qualification and Handoff Checklist (internal-only) | Planned | - |

Each document folder contains its `.tex` source and the current built `.pdf`,
so anyone can either download the ready-made PDF or rebuild it from source.

## Getting the forms (no LaTeX required)

Download the `.pdf` file from the relevant `documents/<name>/` folder. Every
form is a genuine fillable PDF (text fields, checkboxes, dropdowns) built with
`hyperref`; open it in a full-featured PDF reader (e.g. Adobe Acrobat Reader)
to fill it in and save your answers. Browser-based PDF viewers vary in how
well they support form fields -- if fields don't appear to save, download the
file and open it in a dedicated reader instead.

Each form opens with a cover page (title and a plain-English explanation of
the document's purpose) followed by an automatically generated table of
contents, then the fillable content itself.

## Building the forms (maintainers / contributors)

Requires **XeLaTeX** (not plain `pdflatex`) because the templates set Times
New Roman via `fontspec`, plus the packages used below (all included in a
standard MiKTeX or TeX Live install): `hyperref`, `fancyhdr`, `geometry`,
`graphicx`, `etoolbox`, `booktabs`, `longtable`, `lastpage`, `tabularx`.

Times New Roman itself must be installed on the build machine (standard on
Windows and on any machine with Microsoft Office installed). If it is not
available -- for example on a bare TeX Live install on Linux -- edit
`\setmainfont{Times New Roman}` in `shared/intake-style.sty` to a metrically
compatible substitute such as `Liberation Serif` or `Tinos`.

From inside a document's folder, build with:

```
xelatex -interaction=nonstopmode <document-name>.tex
```

Run it **twice**: the first pass writes the table-of-contents and page-count
data, and the second pass reads it back in to render the table of contents
correctly and resolve the "Page X of Y" footer (via the `lastpage` package).

## Repository structure

```
engineering-intake-templates/
├── shared/
│   ├── intake-style.sty       # Font, page layout, headers/footers, markings band, cover page
│   └── form-components.sty    # Reusable fillable-field macros and shared content blocks
├── documents/
│   ├── 01-intake-form/
│   │   ├── intake-form.tex
│   │   └── intake-form.pdf
│   ├── 02-discipline-addenda/ # Reserved for future discipline-specific addenda
│   └── 04-scope-definition/
│       ├── scope-definition.tex
│       └── scope-definition.pdf
└── docs/
    ├── Engineering_Project_Intake_Plan.md
    └── Engineering_Template_Design_Questions.md
```

## Editing branding and markings

All branding (company name/logo) and the header/footer marking text are set
in one place: `shared/intake-style.sty`, or overridden per document via
`\SetCompanyName`, `\SetCompanyLogo`, and `\SetMarkingText` near the top of
each document's `.tex` file. Update these once the organization confirms its
actual logo, approved marking text, and handling requirements -- see
"Remaining Organization-Specific Decisions" in the intake plan.

The header shows only the marking banner (one centered zone); the footer
shows the document ID, the marking banner, and the page count in three
fixed-width zones. Each zone wraps its own text internally rather than
overlapping its neighbors, so longer branding/marking text is safe to use --
it will wrap to a second line within its own zone instead of colliding with
adjacent text.

## Adding a new document

1. Create `documents/<NN-short-name>/<short-name>.tex`.
2. `\usepackage{../../shared/intake-style}` and
   `\usepackage{../../shared/form-components}`.
3. Call `\SetDocIdentity{Title}{Doc ID}{Template Version}`,
   `\SetFieldPrefix{uniqueprefix}` (keeps PDF field names from colliding with
   other documents), and `\SetDocPurpose{...}` (a plain-English paragraph
   shown on the cover page explaining what the document is for).
4. Wrap the document body in `\begin{Form} ... \end{Form}` (required by
   `hyperref` for the fillable fields to actually register as a PDF
   AcroForm -- without it, the fields render but are not interactive).
5. Call `\CoverPage` right after `\begin{Form}` to generate the title page
   and table of contents, then reuse `\DocumentControlBlock`,
   `\RequestingOrgBlock`, `\OpenItemsTable`, and `\AcknowledgementBlock`
   where they fit. Keep genuinely new questions in the new document's own
   `.tex` file until the same content is needed a second time.
6. When laying out fillable fields, pass `\linewidth` as the field width
   (inside a `tabularx` cell this is the cell's own width; at the top level
   it is the full `\textwidth`) rather than a hardcoded measurement, so
   fields always use all of their available space.
7. Build and check the PDF (field entry, save/reopen, printing) before
   distributing it. A quick way to confirm the fields actually registered is
   to check that the PDF has an `/AcroForm` entry (e.g. via `pypdf`'s
   `PdfReader(...).get_fields()`), since a missing `\begin{Form}` wrapper
   will otherwise compile silently with no interactive fields at all.

## Status

First release: the Intake Form and Scope Definition Worksheet are drafted,
build cleanly under XeLaTeX, and verified to produce real interactive PDF
form fields (checked programmatically, not just visually). Several fields
use placeholder text pending organizational confirmation (branding,
markings, named approvers, retention policy) -- see the "Remaining
Organization-Specific Decisions" section of the intake plan.
