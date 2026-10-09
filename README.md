# Engineering Project Intake Templates

Reusable LaTeX templates that produce fillable PDF forms for the full
lifecycle of an engineering support request -- from an informal request,
through scope definition, requirements, risk/compliance review, and
pre-SOW confirmation -- before any project charge code or Statement of
Work (SOW) exists.

The goal is to turn an informal "can you help us with..." request into a
documented, bounded scope before the engineering center commits time or
resources, so neither side is surprised later by scope that was never
written down.

See [docs/Engineering_Project_Intake_Plan.md](docs/Engineering_Project_Intake_Plan.md)
for the full workflow and design rationale behind this document family, and
[docs/Engineering_Template_Design_Questions.md](docs/Engineering_Template_Design_Questions.md)
for the underlying design decisions (identifiers, revision rules, required
fields, etc.).

## The Document Family and What Each One Is For

All 7 documents below are built. Each is an independent LaTeX source file
(`.tex`) with a built, fillable PDF (`.pdf`) sitting right next to it in the
same folder.

| # | Document | Folder | Completed by | Used when |
|---|---|---|---|---|
| 1 | **Pre-Project Intake and Discovery Form** | `documents/01-intake-form/` | Requester, then reviewed with the center lead | First point of contact -- before any charge code or commitment exists |
| 2 | **Technical Discovery Addenda** (5 files: mechanical, electrical, structural, systems, environmental) | `documents/02-discipline-addenda/` | Requesting technical lead and relevant center engineers | After Document 1, only for the disciplines actually involved |
| 3 | **Requirements and Acceptance Worksheet** | `documents/03-requirements-worksheet/` | Requesting technical lead and center engineering lead, jointly | Alongside or after Document 4, once scope is taking shape |
| 4 | **Scope Definition Worksheet** | `documents/04-scope-definition/` | Center lead, reviewed by the requester/sponsor | After Document 1 is reviewed; this is the main input to an estimate and SOW |
| 5 | **Constraints, Risks, and Compliance Checklist** | `documents/05-constraints-risks/` | Requesting operations/safety/IT representatives and the center lead | Alongside Document 4, to surface constraints early |
| 6 | **Pre-SOW Scope Confirmation** | `documents/06-presow-confirmation/` | Requesting sponsor and the center lead | Final check before an estimate/SOW is prepared |
| 7 | **Center Qualification and Handoff Checklist** | `documents/07-internal-checklist/` | Center leadership and engineering team | **Internal only -- see warning below** |

### What each document actually asks for

- **1. Pre-Project Intake and Discovery Form.** The starting point for any
  request. Captures the problem, desired outcome, which disciplines might
  be involved, preliminary scope boundaries, desired outputs, timing, and
  known constraints -- in plain language, before any engineering analysis
  has happened. A charge code is explicitly *not* required to submit it.
- **2. Technical Discovery Addenda.** Five short, discipline-specific
  supplements (mechanical, electrical, structural, systems,
  environmental). Issue only the ones relevant to a given request -- e.g.
  a wiring upgrade only needs the electrical addendum, not all five. Each
  asks for the deeper technical detail a center engineer in that
  discipline would actually need (existing equipment/drawings, loads,
  applicable codes, site constraints) that Document 1 intentionally
  doesn't ask for.
- **3. Requirements and Acceptance Worksheet.** Turns the general scope
  into specific, numbered requirements, each marked Mandatory or
  Preferred, with measurable acceptance criteria and a verification
  method. The point is to replace vague expectations ("make it better")
  with something two different people would agree was met or not met.
- **4. Scope Definition Worksheet.** The center's proposed work packages,
  deliverables, explicit inclusions *and* exclusions, interface
  boundaries, required requester inputs, and assumptions. This is the
  document an estimate and SOW actually get built from.
- **5. Constraints, Risks, and Compliance Checklist.** Schedule/outage
  constraints, applicable codes and standards (by discipline), safety and
  environmental constraints, data-handling restrictions, a risk register,
  and any specialist reviews needed. Recording a standard here means it
  was identified as applicable -- it is explicitly **not** a compliance
  certification.
- **6. Pre-SOW Scope Confirmation.** The final sanity check: restates the
  reviewed scope, lists any remaining open issues (visibly, not hidden),
  records preliminary schedule/funding assumptions, and collects reviewer
  sign-offs with a Ready / Not Ready / Conditional recommendation.
  Signing it is not authorization to start work or charge time -- that
  still goes through the organization's normal funding process.
- **7. Center Qualification and Handoff Checklist -- internal only.**
  Center leadership's honest internal assessment: do we have the right
  expertise and capacity, how confident is the estimate, what funding
  route applies, what's the risk, and a Proceed / Clarify Further /
  Decline decision. **This never goes to the requester.**

> **Document 7 is internal-only.** A *blank* copy of this template is in
> this repository like any other, but a *completed* copy must never be
> sent to a requester or included in a requester-facing document package.
> Its header/footer marking text is intentionally different ("INTERNAL
> USE ONLY -- DO NOT DISTRIBUTE TO REQUESTER") so a completed copy is
> unmistakable at a glance, and its cover-page purpose statement repeats
> the same warning.

## How to Use These Documents (Workflow)

1. **A request comes in** (direct ask or word-of-mouth referral). Assign it
   an Intake Reference Number (format `ENG-YYYY-###`) and send the blank
   **Document 1** PDF through your organization's approved channel.
2. **Document 1 comes back.** The center lead reviews it (using the
   internal **Document 7** to judge fit, capacity, and confidence) and
   decides to discuss, clarify, or decline.
3. **Discovery.** If needed, issue only the relevant **Document 2**
   addenda for the disciplines actually involved, and talk through the
   details together.
4. **Define the scope.** The center lead drafts **Document 4** (Scope
   Definition Worksheet); **Document 3** (Requirements) and **Document 5**
   (Constraints/Risks) are typically developed alongside it.
5. **Confirm readiness.** Once scope, requirements, and constraints are
   reviewed, complete **Document 6** (Pre-SOW Scope Confirmation) to mark
   the record as ready for an estimate and SOW -- this is still not
   authorization to start work.
6. **Authorize and proceed.** Once the organization's funding/charge-code
   process authorizes the work, the SOW is prepared from the reviewed
   document set, and the project proceeds under the organization's normal
   project controls (outside the scope of these templates).

Every document after Document 1 carries the same Intake Reference Number
forward (via the shared `\LinkedIntakeBlock`), so the full set of
documents for one request can always be tied back together.

### Filling out a form

Open the `.pdf` in a full-featured PDF reader (e.g. Adobe Acrobat Reader)
-- not every browser-based viewer handles form fields well, so download
the file first if fields don't seem to save. Each form opens with a cover
page (title and a plain-English explanation of what the document is for)
followed by an automatically generated table of contents, then the
fillable content itself. It is fine to leave a field marked Unknown or Not
applicable rather than guess -- most sections include a named follow-up
owner and date for exactly that reason.

## Building on a New Machine

You do not need LaTeX to use a finished PDF -- see "Filling out a form"
above. The steps below are only for rebuilding the `.tex` source (e.g.
after editing branding, or adding a new document).

### 1. Install a LaTeX distribution

- **Windows:** install [MiKTeX](https://miktex.org/download) (recommended)
  or [TeX Live](https://www.tug.org/texlive/).
- **macOS:** install [MacTeX](https://www.tug.org/mactex/).
- **Linux:** install TeX Live via your package manager (e.g.
  `sudo apt install texlive-full`, or a smaller scheme plus the packages
  listed below if you want a lighter install).

These templates specifically require **XeLaTeX**, not plain `pdflatex`,
because they set Times New Roman via `fontspec`. XeLaTeX ships with any of
the distributions above.

### 2. Confirm the required packages are available

The templates use: `hyperref`, `fancyhdr`, `geometry`, `graphicx`,
`etoolbox`, `booktabs`, `longtable`, `lastpage`, `tabularx`, `fontspec`.
All of these are included in a standard MiKTeX or TeX Live install. MiKTeX
in particular will prompt to auto-install any missing package the first
time you build.

### 3. Confirm Times New Roman is available

Times New Roman is standard on Windows and on any machine with Microsoft
Office installed, so most users won't need to do anything. If you're on a
bare TeX Live install (e.g. a fresh Linux box) and don't have it, either
install it (e.g. via `ttf-mscorefonts-installer` on Debian/Ubuntu, where
licensing permits) or edit one line in `shared/intake-style.sty`:

```latex
\setmainfont{Times New Roman}
```

...and replace `Times New Roman` with a metrically compatible free
substitute such as `Liberation Serif` or `Tinos`. This is a single edit in
one shared file -- every document picks it up automatically.

### 4. Get the repository

Either `git clone https://github.com/Gump17928/engineering_doc_templates.git`,
or download the ZIP from GitHub (`Code` -> `Download ZIP`) and extract it
anywhere. The templates only use relative paths internally (e.g.
`\usepackage{../../shared/intake-style}`), so the folder can be extracted
or cloned to any location on any machine without edits -- this has been
tested by building from a freshly extracted copy in an unrelated folder.

### 5. Build a document

From inside that document's folder, run:

```
xelatex -interaction=nonstopmode <document-name>.tex
```

**Run it twice.** The first pass writes the table-of-contents and
page-count data to an auxiliary file; the second pass reads that back in
to render the table of contents correctly and resolve the "Page X of Y"
footer (via the `lastpage` package). For example:

```
cd documents/01-intake-form
xelatex -interaction=nonstopmode intake-form.tex
xelatex -interaction=nonstopmode intake-form.tex
```

This produces `intake-form.pdf` in the same folder. Repeat for any other
document you want to rebuild.

### 6. Verify the build (optional, recommended before distributing)

A clean build should report no `Overfull \hbox` or `Error` lines. You can
also confirm the PDF actually has working interactive fields (not just
fields that look right) with Python's `pypdf`:

```
pip install pypdf
python -c "from pypdf import PdfReader; r = PdfReader('intake-form.pdf'); print('/AcroForm' in r.trailer['/Root'], len(r.get_fields()))"
```

This should print `True` followed by a field count greater than zero. A
missing `\begin{Form} ... \end{Form}` wrapper is the one mistake that
compiles cleanly but silently produces zero working fields -- see "Adding
a new document" below.

## Repository Structure

```
engineering-intake-templates/
├── README.md                      # This file
├── .gitignore
├── shared/
│   ├── intake-style.sty           # Font, page layout, headers/footers, markings band, cover page
│   └── form-components.sty        # Reusable fillable-field macros and shared content blocks
├── documents/
│   ├── 01-intake-form/
│   │   ├── intake-form.tex
│   │   └── intake-form.pdf
│   ├── 02-discipline-addenda/
│   │   ├── addendum-mechanical.tex / .pdf
│   │   ├── addendum-electrical.tex / .pdf
│   │   ├── addendum-structural.tex / .pdf
│   │   ├── addendum-systems.tex / .pdf
│   │   └── addendum-environmental.tex / .pdf
│   ├── 03-requirements-worksheet/
│   │   └── requirements-worksheet.tex / .pdf
│   ├── 04-scope-definition/
│   │   └── scope-definition.tex / .pdf
│   ├── 05-constraints-risks/
│   │   └── constraints-risks-checklist.tex / .pdf
│   ├── 06-presow-confirmation/
│   │   └── presow-confirmation.tex / .pdf
│   └── 07-internal-checklist/     # Internal-only -- see warning above
│       └── qualification-checklist.tex / .pdf
└── docs/
    ├── Engineering_Project_Intake_Plan.md         # Full workflow and design rationale
    └── Engineering_Template_Design_Questions.md   # Underlying design decisions
```

## Shared Components Reference

Both `.sty` files in `shared/` are loaded by every document and are the
reason branding, layout, and common fields only need to be edited once.

**`intake-style.sty`** -- font (Times New Roman via `fontspec`), page
geometry, header/footer (overlap-proof, fixed-width zones), and:
- `\SetCompanyName{...}`, `\SetCompanyLogo{...}`, `\SetMarkingText{...}` --
  branding and marking text, overridable per document.
- `\SetDocIdentity{Title}{Doc ID}{Template Version}` and
  `\SetDocPurpose{...}` -- document identity and cover-page purpose text.
- `\CoverPage` -- generates the title page and table of contents.
- `\IntakeSection{...}` -- a section heading that also adds a
  table-of-contents entry.
- `\Guidance{...}` -- small italic instructional text.
- `\ContinuationNote` -- standard "attach a continuation sheet" note.

**`form-components.sty`** -- the actual fillable-field macros and shared
content blocks:
- `\TextLine{name}{label}{width}` / `\TextArea{name}{label}{width}{height}`
  / `\CheckOption{name}{label}` / `\DropDown{name}{label}{width}{choices}`
  -- the basic fillable-field building blocks. Pass `\linewidth` as the
  width so a field always fills its full available space (the cell width
  inside a `tabularx` table, or the full `\textwidth` at the top level).
- `\DocumentControlBlock` -- document ID, status, revision history.
- `\RequestingOrgBlock` -- department, sponsor, technical contact.
- `\LinkedIntakeBlock` -- one-line reference back to Document 1's Intake
  Reference Number (used by every document after Document 1).
- `\OpenItemsTable{prefix}` -- 3-row open-item / owner / target-date table.
- `\RiskRegisterTable{prefix}` -- 3-row risk / likelihood / impact / owner
  / mitigation table.
- `\StandardsTable{prefix}` -- 3-row applicable-standard / discipline /
  confirmed-by / status table.
- `\RequirementBlock{prefix}{number}` -- one full numbered requirement
  (ID, priority, text, acceptance criteria, verification method).
- `\AcknowledgementBlock{wording}` -- closing acknowledgement/sign-off,
  with document-specific wording passed in.

The `prefix` argument on table/block macros exists so the same macro can
be called more than once in one document (or reused across documents)
without its PDF field names colliding.

## Editing Branding and Markings

All branding (company name/logo) and the header/footer marking text are
set in one place: `shared/intake-style.sty`, or overridden per document
via `\SetCompanyName`, `\SetCompanyLogo`, and `\SetMarkingText` near the
top of each document's `.tex` file. Update these once the organization
confirms its actual logo, approved marking text, and handling requirements
-- see "Remaining Organization-Specific Decisions" in the intake plan.

The header shows only the marking banner (one centered zone); the footer
shows the document ID, the marking banner, and the page count in three
fixed-width zones. Each zone wraps its own text internally rather than
overlapping its neighbors, so longer branding/marking text is safe to use
-- it will wrap to a second line within its own zone instead of colliding
with adjacent text.

## Adding a New Document

1. Create `documents/<NN-short-name>/<short-name>.tex`.
2. `\usepackage{../../shared/intake-style}` and
   `\usepackage{../../shared/form-components}`.
3. Call `\SetDocIdentity{Title}{Doc ID}{Template Version}`,
   `\SetFieldPrefix{uniqueprefix}` (keeps PDF field names from colliding
   with other documents), and `\SetDocPurpose{...}` (a plain-English
   paragraph shown on the cover page explaining what the document is for).
4. Wrap the document body in `\begin{Form} ... \end{Form}` (required by
   `hyperref` for the fillable fields to actually register as a PDF
   AcroForm -- without it, the fields render but are not interactive).
5. Call `\CoverPage` right after `\begin{Form}` to generate the title page
   and table of contents, then reuse the shared components listed above
   where they fit. Keep genuinely new questions in the new document's own
   `.tex` file until the same content is needed a second time.
6. When laying out fillable fields, pass `\linewidth` as the field width
   rather than a hardcoded measurement, so fields always use all of their
   available space.
7. Build and check the PDF (field entry, save/reopen, printing) before
   distributing it -- see "Verify the build" above.

## Status

All 7 planned documents (11 files, since Document 2 is 5 separate
discipline addenda) are built, drafted, and build cleanly under XeLaTeX.
They are verified to produce real interactive PDF form fields (checked
programmatically -- field count and `/AcroForm` presence -- not just
visually), and building from a freshly extracted copy in a different
folder has been tested to confirm a plain ZIP download works correctly.

Several fields use placeholder text pending organizational confirmation
(branding, markings, named approvers, applicable codes/standards per
discipline, retention policy) -- see "Remaining Organization-Specific
Decisions" in the intake plan.

Still outstanding, per the intake plan's implementation sequence:
- Human-viewer validation (tab order, save/reopen, printing) in an actual
  PDF reader -- the automated checks above confirm the fields exist and
  are wired up, not that they behave well in every viewer.
- A pilot with a real incoming request.
- Answer extraction / prefilling between documents (explicitly deferred
  until after the core workflow is proven out).
