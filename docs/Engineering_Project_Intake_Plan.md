# Engineering Project Intake and Scoping Plan

## Purpose

Create a reusable document family for a multidisciplinary engineering center serving other departments within a larger military/defense business. Turn informal requests and word-of-mouth opportunities into a documented, bounded scope before project charge codes, commitments, or a Statement of Work (SOW) are established.

The primary goal is to prevent unrecognized scope growth and commitments that exceed the center's capacity or expertise.

## Design Basis from Section A

Based on the answers in [Engineering Template Design Questions](Engineering_Template_Design_Questions.md):

- **Audience:** internal requesting departments and sponsors, rather than primarily external commercial clients.
- **Disciplines:** mechanical, electrical, structural, systems, and environmental engineering.
- **First priority:** one pre-project intake/discovery document that clarifies the request before initial or follow-up discussions.
- **Completion:** digitally completed, reusable blank PDFs, issued individually through an organization-approved secure channel. Requesters do not need LaTeX source or compilation access.
- **Guidance:** short explanations and examples alongside fillable fields; users can replace any editable example text.
- **Appearance:** a company image/logo and sensitive-information headers and footers.
- **Revision tracking:** a top-of-document block for names, dates, and document revisions, with consistent current-revision information throughout.
- **Maintenance:** an engineer initially, with possible transfer to a technical writer.
- **Later enhancement:** reuse answers from completed documents to prefill subsequent forms, only after the blank-form workflow works.

Treat completed project documents as confidential by default, subject to the organization's actual handling rules. An NDA or a generic "Confidential" label does not authorize classified, controlled, export-restricted, or other sensitive data in an unapproved environment. Actual markings, authorized content, recipients, and storage/transfer methods must be confirmed before operational use.

## Recommended Documents

| Document | Completed by | Purpose and key contents |
|---|---|---|
| **1. Pre-Project Intake and Discovery Form - first release** | Requester, then reviewed with center lead | Capture the business need, requested assistance, preliminary scope boundaries, desired outputs, timing, available inputs, constraints, and unknowns before committing resources. Combines short inquiry and initial discovery to avoid two overlapping forms. |
| **2. Technical Discovery Addenda - later** | Requesting technical lead and relevant center engineers | Deeper discipline-specific requirements, existing assets/data, interfaces, operating conditions, and site/access needs. Issue only applicable addenda, each usable independently. |
| **3. Requirements and Acceptance Worksheet - later** | Requesting technical lead and center engineering lead | Numbered requirements, priorities, owners, measurable acceptance criteria, verification methods, and unresolved decisions. |
| **4. Scope Definition Worksheet - next core document** | Center lead, reviewed by requester/sponsor | Work packages, deliverables, inclusions, exclusions, interface boundaries, requester inputs, assumptions, dependencies, responsibilities, and scope-change handling. Main input to an estimate and SOW. |
| **5. Constraints, Risks, and Compliance Checklist - later** | Requesting operations/safety/IT representatives and center lead | Outages, permits, standards, environmental and safety constraints, data restrictions, risk owners, and specialist reviews. Records applicability; does not certify compliance. |
| **6. Pre-SOW Scope Confirmation - later** | Requesting sponsor and center lead | Reviewed scope baseline, open issues, preliminary schedule/resource/funding assumptions, reviewers, and readiness for SOW preparation. Not permission to start engineering work or charge time. |
| **7. Center Qualification and Handoff Checklist - internal-only** | Center leadership and engineering team | Expertise, capacity, missing information, estimate confidence, funding/charge-code route, risks, and proceed/clarify/decline decision. Do not distribute internal assessments with requester forms. |

## First Document: Required Content

Design the Pre-Project Intake and Discovery Form as a short core form, provisionally **3-4 pages**, with continuation sheets for detail. Confirm the page count during the pilot rather than shrinking answer space to meet an arbitrary limit.

| Section | Information to collect |
|---|---|
| **Document control** | Form ID, template version, intake reference independent of a charge code, completed-record revision/date, preparer, and revision history. |
| **Requesting organization and contacts** | Department/program, sponsor, technical contact, and people who can decide requirements or approve scope. |
| **Problem and intended outcome** | Current condition, reason assistance is needed, desired outcome, and consequence of doing nothing. |
| **Requested engineering assistance** | Applicable disciplines, requested activities, existing work, and interfaces with other teams. Allow uncertainty about which discipline is needed. |
| **Preliminary scope boundaries** | Explicitly included work, explicitly excluded work, assets/sites/systems involved, and responsibility boundaries. These are proposed boundaries, not an approved SOW. |
| **Outputs and success criteria** | Expected deliverables/formats, intended use, reviewer/acceptance owner, and how success could be measured. |
| **Timing and resources** | Desired dates, hard deadlines and their reasons, access/outage windows, funding contact/status, and charge-code status if known. A code must not be required for initial intake. |
| **Inputs and constraints** | Available drawings/data, attachment references and revisions, requester-provided resources, known standards, safety/environmental constraints, and approved information-handling requirements. |
| **Assumptions and open questions** | Unknowns, dependencies, needed decisions, and follow-up owner/date. Permit Unknown and Not applicable where appropriate. |
| **Discussion and acknowledgement** | Center reviewer, discussion date, clarified boundaries, next action, and acknowledgement that intake is not authorization or a delivery commitment. |

Use plain-language prompts and brief examples. Distinguish requester answers from center review notes. Initial mandatory fields should be limited to contact, problem, intended outcome, requested assistance, and timing; confirm the final required-field rules with the process owner.

### Optional Attachments

Add these only when relevant, rather than making every requester complete every form:

- **Site survey / existing-condition record:** equipment inventory, photographs, drawings, measurements, and data gaps.
- **Discipline-specific discovery addenda:** mechanical, electrical, structural, systems, and environmental. Add other specialties only when the center's services require them.
- **Stakeholder and interface register:** cross-department approvals, external parties, system interfaces, and responsibility boundaries.
- **Deliverable and input register:** required source files, revision/status, document owner, due date, and reference location.

## Workflow and Decision Gates

1. **Capture an opportunity:** a direct request or referral triggers Document 1. Assign an intake reference; send only the blank PDF and approved submission instructions.
2. **Pre-meeting review:** requester returns the form through the approved channel. Center lead checks expertise, capacity, key unknowns, and proposed boundaries. Decide whether to discuss, redirect, clarify, or decline.
3. **Guided discovery:** review answers together, record corrections and assumptions, and issue Document 2 addenda only as needed. Confirm the center's permitted pre-charge-code discovery effort; do not imply unlimited unfunded support.
4. **Scope definition:** develop Document 4 and supporting Documents 3/5 as appropriate. Record requester obligations, exclusions, acceptance criteria, dependencies, and open-item owners.
5. **Readiness and funding review:** use Document 6 and the internal checklist to confirm the scope baseline, responsible reviewers, resource availability, and funding/charge-code authorization route.
6. **SOW and authorized handoff:** prepare the estimate/SOW from the reviewed record. Begin execution only through the organization's required authorization process; retain the agreed revision.

**Readiness rule:** do not treat a package as ready merely because every field is filled in. Important unknowns must be resolved or explicitly addressed in the proposed scope, resource estimate, and funding assumptions.

**Scope-growth rule:** before authorization, record new requests as proposed changes with schedule/resource impacts and obtain renewed scope agreement. After authorization, use the applicable change-control process. Never silently turn a revised intake answer into additional committed work.

## Modular LaTeX and PDF Design

### Shared source, individual outputs

- **Shared style:** company image, typography, page geometry, approved marking bands, headers/footers, and page numbering.
- **Reusable components:** text fields, multiline answers, checkboxes, guidance, tables, attachment references, and document-control/revision blocks.
- **Shared content modules:** reuse identical content such as contact and attachment sections. Keep unique questions in the individual document until reuse is demonstrated.
- **Document entry points:** one LaTeX entry file per document, selecting components/modules and setting its title, ID, and template version.
- **Assets and instructions:** approved company image and a short maintainer guide covering builds, revisions, module additions, and PDF validation.

Maintain one controlled source collection, not copied template repositories per project. Store blank generated PDFs separately from completed project records. Requesters receive PDFs and approved attachments only, never source files or internal review documents.

### Fillable behavior and guidance

- Produce genuine interactive PDF fields with a print-friendly layout. Start with blank reusable forms, not project-specific compilation.
- Prefer persistent guidance outside fields so instructions remain after an answer is entered. If editable examples are used, label them clearly and exclude untouched example values from completeness checks.
- Use stable, document-qualified field identifiers to support later extraction and prevent accidental coupling between unrelated answers.
- Provide continuation sheets and attachment references for long answers and repeated items; fixed PDF fields do not automatically expand with content.
- Do not depend on PDF JavaScript, automatic placeholder clearing, or viewer-enforced required fields. Review completeness explicitly.

### Document control and revision propagation

- Separate the **template version** (maintainer-controlled design/content release) from the **completed-record revision** (changes to a particular request).
- Put the editable current-record revision, revision date, and preparer at the top, followed by a history table with revision, author, date, and change summary.
- Repeat current-record revision/date using linked PDF field widgets, if supported by the chosen tooling and viewers. Editing a PDF does not rerun LaTeX, so ordinary typeset footer text cannot update from an edited top field.
- Prototype save/reopen and print behavior before promising automatic propagation. If linked widgets are unreliable, display editable revision information only in the control block; repeat static document ID/template version elsewhere. Do not distribute inconsistent revision copies.
- Preserve prior reviewed records rather than overwriting them; explicitly identify the current baseline. Exact naming, numbering, and approval owners remain to be agreed.

### Security and information handling

Reserve header/footer space for approved markings on every page and continuation sheet. Do not invent defense-specific markings or assume NDA coverage determines classification. Confirm approved content and environment with the responsible organizational authority.

Keep project records and future answer processing inside the approved environment. Do not use external compilation/upload services for sensitive content without authorization. Define folder access, transfer instructions, retention, and archive handling before rollout.

### Optional later prefilling

After the blank-form pilot, evaluate local extraction of returned PDF fields into a structured project record. An engineer must review the extracted answers before they populate subsequent documents; imports must not overwrite reviewed scope silently.

Use stable field mappings and explicit handling of missing fields, revisions, and untouched examples. Do not treat extraction as part of the first release or require copying LaTeX files into project folders.

## Confirmed Design Decisions (from Sections A, B, and C)

These are now settled well enough to start building; adjust retroactively in [Engineering_Template_Design_Questions.md](Engineering_Template_Design_Questions.md) if real use proves one wrong:

- **Identifiers:** every request gets an **Intake Reference Number** at first contact, independent of any charge code, format `ENG-YYYY-###` (e.g., `ENG-2026-014`). It carries unchanged through every later document; requirements/deliverables get sub-IDs under it (e.g., `ENG-2026-014-R01`).
- **Status and revisions:** each completed record carries a status of **Draft / Under Review / Confirmed**, an author, a date, and a revision-history table. "Confirmed" is the frozen baseline used to prepare an estimate/SOW; prior revisions are kept, not overwritten.
- **Disciplines:** mechanical, electrical, structural, systems, and environmental, selectable as **multiple simultaneous checkboxes** rather than a single pick, since one request can span several disciplines.
- **Required fields:** at intake, only contact info, problem statement, requested assistance, and desired timing are mandatory; everything else may be marked Unknown/To be confirmed with a named follow-up owner and date. Inclusions, exclusions, deliverables, and acceptance criteria become mandatory before a record can move to Confirmed status.
- **Repeating items:** a fixed ~5 inline rows on the base form for contacts, attachments, requirements, deliverables, and open issues, with an explicit continuation-sheet reference for overflow.
- **Acknowledgement language (first draft, pending center-leadership review):** "This form reflects current understanding only. It does not commit [Center Name]'s resources, and the proposed scope may change following further review." Use this consistently on the Intake Form and adapt its wording for the Scope Definition Worksheet's readiness acknowledgement.
- **Usability target:** the Intake Form should be completable in roughly 15-30 minutes without requiring the requester to gather extensive materials first.
- **Pilot approach:** use the next real incoming request (not a hypothetical one) as the pilot, reviewed by the center lead plus one engineer from the relevant discipline.
- **Build tooling:** pdfLaTeX with the `hyperref` package's form-field commands (`\TextField`, `\CheckBox`, `\ChoiceMenu`, etc.) to produce genuine fillable PDF fields from plain `.tex` source, one build command per document, output named `<IntakeReference-or-draft>_<DocumentName>_v<#>.pdf`.
- **No prefilling in the first release:** forms are reusable blanks only; later prefilling, if pursued, pulls from a previously completed and reviewed PDF of the same project, not an external system.

## Remaining Organization-Specific Decisions

These still depend on information only your organization holds, and the templates use clearly marked placeholders until they're supplied:

- Actual company name, logo image file, and color/paper-size conventions.
- Actual approved marking/confidentiality text for headers and footers (placeholder text is used until confirmed).
- Supported PDF viewers and the approved secure channel for sending/receiving completed forms.
- Named individuals for center lead, discipline reviewers, and funding/charge-code authorization.
- Applicable codes/standards per discipline (to be added to discipline addenda as confirmed by each discipline lead).
- Actual records-retention period and archive location policy.

## Implementation Sequence

1. **Draft the first form:** finalize the sections above using non-sensitive sample content and placeholders for unconfirmed branding/markings. **(Status: in progress - see repository structure below.)**
2. **Build the shared foundation and first template:** implement reusable layout/field components, document control, guidance, and continuation sheets using pdfLaTeX + `hyperref` forms.
3. **Validate the actual PDF:** check field entry, multiline answers, tab order, save/reopen, printing, overflow instructions, marking coverage, and revision consistency in supported viewers.
4. **Pilot with a requesting department:** verify that the form exposes boundaries, exclusions, missing inputs, and next actions before a project commitment. Revise based on completion effort and discussion quality.
5. **Prove reuse with the Scope Definition Worksheet:** use the same style/components without copying their implementation; keep document-specific questions separate.
6. **Expand selectively:** add discipline addenda, acceptance/risk/confirmation documents, and the internal checklist. Evaluate answer extraction/prefilling only after the core workflow is stable.

## Repository Structure

The templates live in a version-controlled folder tree so the shared style/components are edited once and every document picks them up. Planned layout:

```
engineering-intake-templates/
├── README.md                    # What this is, how to build, how to contribute
├── LICENSE
├── shared/
│   ├── intake-style.sty         # Branding, page geometry, headers/footers, markings band
│   ├── form-components.sty      # Reusable hyperref field macros (text, multiline, checkbox, table rows)
│   └── logo-placeholder.png     # Swap with the real company logo
├── documents/
│   ├── 01-intake-form/
│   │   └── intake-form.tex      # Document entry point (Document 1)
│   ├── 02-discipline-addenda/
│   │   ├── addendum-mechanical.tex
│   │   ├── addendum-electrical.tex
│   │   ├── addendum-structural.tex
│   │   ├── addendum-systems.tex
│   │   └── addendum-environmental.tex
│   └── 04-scope-definition/
│       └── scope-definition.tex # Document entry point (Document 4)
├── build/                       # Generated PDFs (gitignored, or committed per team preference)
└── docs/
    ├── Engineering_Project_Intake_Plan.md
    └── Engineering_Template_Design_Questions.md
```

Documents 2 (addenda), 3, 5, 6, and 7 are added as their own folders under `documents/` following the same pattern once the first two are piloted. Each document folder stays small and self-contained; all shared look-and-feel lives in `shared/`.

## Acceptance Checks

- Requesters can complete, save, and return each PDF without LaTeX access.
- Shared branding/layout changes apply to both core templates without separate edits.
- Template version and completed-record revision are distinct; displayed current-revision values remain consistent after editing and printing.
- Guidance is clear, long answers have a continuation method, and unknowns have follow-up owners.
- Every page carries approved markings; requester outputs contain no internal assessments.
- The pilot produces explicit scope boundaries and an authorization path, not an implied promise to perform work.
- Supported tools/viewers and the tested build process are documented for the engineer or technical writer.

## Best Approach

Start with **one well-designed Pre-Project Intake and Discovery Form**, backed by shared LaTeX components. Follow it with a Scope Definition Worksheet to establish a repeatable path from informal request to agreed scope. Keep secure, individually issued PDFs as the requester interface and template maintenance centralized. Add specialized modules and reviewed prefilling only when needed, rather than building a large automation framework first.
