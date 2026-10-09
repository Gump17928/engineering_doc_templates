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

## Building the forms (maintainers / contributors)

Requires a LaTeX distribution with `pdflatex` and the packages used below
(all included in a standard MiKTeX or TeX Live install): `hyperref`,
`fancyhdr`, `geometry`, `graphicx`, `etoolbox`, `booktabs`, `longtable`,
`lastpage`.

From inside a document's folder, build with:

```
pdflatex -interaction=nonstopmode <document-name>.tex
```

Run it twice if you see a `Rerun to get the references right` warning (this
resolves the "Page X of Y" footer via the `lastpage` package).

## Repository structure

```
engineering-intake-templates/
├── shared/
│   ├── intake-style.sty       # Branding, page layout, headers/footers, markings band
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

## Adding a new document

1. Create `documents/<NN-short-name>/<short-name>.tex`.
2. `\usepackage{../../shared/intake-style}` and
   `\usepackage{../../shared/form-components}`.
3. Call `\SetDocIdentity{Title}{Doc ID}{Template Version}` and
   `\SetFieldPrefix{uniqueprefix}` (keeps PDF field names from colliding with
   other documents).
4. Reuse `\TitleBlock`, `\DocumentControlBlock`, `\RequestingOrgBlock`,
   `\OpenItemsTable`, and `\AcknowledgementBlock` where they fit; keep
   genuinely new questions in the new document's own `.tex` file until the
   same content is needed a second time.
5. Build and check the PDF (field entry, save/reopen, printing) before
   distributing it.

## Status

First release: the Intake Form and Scope Definition Worksheet are drafted and
build cleanly. Several fields use placeholder text pending organizational
confirmation (branding, markings, named approvers, retention policy) -- see
the "Remaining Organization-Specific Decisions" section of the intake plan.
