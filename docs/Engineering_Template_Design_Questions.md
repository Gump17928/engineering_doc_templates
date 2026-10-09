# Engineering Template Design Questions

Companion to [Engineering Project Intake Plan](Engineering_Project_Intake_Plan.md).

## Purpose and How to Respond

These questions are for our company to answer before building the templates; they are **not** the questionnaire we will send to clients. They identify missing business requirements and the decisions that affect reuse, modularity, and future expansion.

Answer each numbered question beneath its **Answer** line. "Undecided" is acceptable; suggested defaults below are recommendations, not confirmed requirements. Answer Section A first. Sections B and C can then refine the design without delaying an initial content draft.

**Status:** Sections A, B, and C are all answered and confirmed as the working direction for the first release. Specifics flagged in earlier drafts (e.g., exact standards per discipline, actual retention policy, real pilot project) can still be corrected retroactively as they become known - this file remains the record of those decisions and should be updated when they change.

## A. Decisions Needed Before Building the First Templates

### A1. Audience and business scope

Are these documents exclusively for prospective clients requesting engineering services, or must they also support subcontractor qualification, vendor onboarding, or internal project requests?

**Why it matters:** different audiences need different content and approval workflows; sharing appearance does not mean sharing all questions.

**Answer:** The majority of these would operate in the sense of there being a 'small' business operating within a larger military business that is used to 'help' those in other departments of this large business and supply expertise where needed. 

### A2. Engineering services and first use case

Which engineering disciplines and services do we provide, and which representative project should the first templates support? Include typical project size, industry, and whether work concerns new designs, modifications, assessments, or troubleshooting.

**Why it matters:** establishes the common discovery core and the first discipline-specific modules.

**Answer:** The center is a multidisciplinary engineer team, with mechanical, electrical, structural, systems, and environmental engineers. 

### A3. Initial document set

Should the first release contain only inquiry, discovery, and scope definition, or are any of the other planned documents required immediately? Are there existing client forms, proposal/SOW templates, or examples we must align with?

**Why it matters:** defines the first release and avoids recreating established terminology.

**Answer:** The first piece that we should define is to gain more understanding of what is required for the future, this I think would be the document that would need to be used after someone else comes to us, or we hear via word of mouth that is some work that our center would be well equipped to perform, and to make sure that we are not setting ourselves up for failure due to expanded scopes prior to the start of a project for our center. 

### A4. Completion and distribution method

Will clients complete PDFs digitally, print and scan them, provide answers during a meeting, or use a web form? Which PDF viewers/devices must work, and how will completed forms and attachments be returned?

**Why it matters:** determines interactive field requirements, answer-space layout, and submission instructions.

**Answer:** Digitally ideally, i.e. we send them a project folder or something else via a secrure method that they are able to fill out prior to having our first or several conversations prior to getting any charge codes for the projects that we would/they want work for. 

### A5. Reuse of project information

Do we need blank reusable forms only, forms prefilled from shared project information, or a system that also imports completed client answers into later documents? Who maintains the authoritative project information?

**Why it matters:** these are three different levels of automation. Shared LaTeX inputs can prefill documents, but importing returned PDF answers requires a separate, tested workflow.

**Answer:** Reusable blank forms that have some explanations within the fillable pieces that can be replaced. 

### A6. Individual documents versus combined packages

Must each document be issued independently, combined into one project package, or both? Who selects the included sections: our staff before generating the PDF, or the client while completing it?

**Why it matters:** affects document assembly, numbering, cross-references, and interactive field names. Conditional PDF behavior should not be assumed.

**Answer:** These would need to be sent out individually, assume that no-one except for the main programmer or person that sets up the templates for the documents has access to the .tex file. If there was a method that we would be able to figure out how to compile or pull information from the prevoiusly filled out documents to fill out the rest that wouldn't be a bad idea. (Not sure how complicated this would be, but copying all of the .tex files into a new repo when we have to share them to help us automatically prefill any forms with what they've given us).

### A7. Branding and page standards

What company name, logo, contact details, colors, paper size, language, and date/unit conventions should we use? Is there an existing document standard, or can we propose one?

**Why it matters:** these settings belong in a shared style rather than being copied into each template.

**Answer:** Assume that there will need to be a header and footer for sensitive information and a picture of the company.

### A8. Ownership and approvals

Who sends, completes, reviews, and approves each document? Who decides that a project is ready for estimating/SOW preparation, and what missing information prevents that decision?

**Why it matters:** defines actionable workflow gates rather than a collection of unrelated forms.

**Answer:** Allow for a place that have the revisions and the versions of the document at the top so that people can fill out their names, dates, and what the 'new' version of hte document should be (the rest of the document should fill out with the 'newest' revisions of the document as needed to allow for this)

### A9. Confidentiality and sensitive information

What information may we request before an NDA, what should never be placed in a form, and which storage/submission channels are approved? Which information must remain internal?

**Why it matters:** determines client/internal separation and safe attachment instructions.

**Answer:** Hmm, assume that everyone is under an NDA prior to starting, or that all information contained within these docs is confidential.

### A10. Maintenance and build environment

Who will maintain the templates, how comfortable are they with LaTeX, and where must PDF generation run: local Windows machines, Overleaf, or an automated system? Are there existing LaTeX tools or approved dependency restrictions?

**Why it matters:** keeps the implementation maintainable and avoids choosing an unsupported build workflow.

**Answer:** Engineer shall maintain records, or a technical writer at some point.

## B. Decisions That Define the Modular Design

For each topic, record the desired behavior and any example. These answers can be refined while drafting the first three documents.

| ID | Question / missing detail | Design consequence |
|---|---|---|
| B1 | Which fields appear on every document: project ID, client, site, contact, preparer, status, revision, confidentiality? Which are maintained once versus confirmed by each respondent? | Defines shared metadata and prevents conflicting copies. |
| B2 | Which sections recur unchanged, and which only share a visual layout? For example, contacts may be identical, but inquiry and discovery ask different scope questions. | Separates reusable content modules from reusable field/layout components. |
| B3 | What triggers an optional module: discipline, industry, service, site work, regulated work, or project complexity? Can projects require several modules at once? | Defines simple selection rules without excessive variants. |
| B4 | What may vary by document: instructions, field labels, answer space, required status, or approval blocks? What may vary by client? | Establishes controlled overrides and prevents client-specific template copies. |
| B5 | Which answers are required at each workflow stage? When are Unknown, Not applicable, or To be confirmed permitted, and who follows up? | Defines stage-specific completion rules and an open-item record. |
| B6 | Which items can repeat without a known limit: sites, stakeholders, equipment, requirements, deliverables, or attachments? Are continuation sheets acceptable? | Determines repeatable tables and overflow handling; fixed PDF fields do not expand indefinitely. |
| B7 | How should projects, documents, requirements, deliverables, and attachments be identified? Must identifiers remain stable through revisions and into the SOW? | Defines identifiers and cross-document references separately from page numbering. |
| B8 | How are answers corrected, reviewed, and frozen? Must draft/reviewed/confirmed status, author, date, and change history be recorded? | Defines revision control and the approved baseline. |
| B9 | If prefilled data is needed, where does it originate: manual entry, a shared data file, spreadsheet, CRM, or another system? Which export formats are already available? | Determines the simplest input interface; does not presume a new integration. |
| B10 | What accessibility, language, or client procurement requirements apply to the PDFs? Is an alternative completion format required? | May require an accessible web/office format alongside LaTeX PDFs. |
| B11 | How much automation is required now: one-command builds, batch generation, package selection, or naming/output-folder conventions? | Limits initial tooling to real needs. |
| B12 | Who can add or change a module, who approves it, and how will older project records remain reproducible when templates change? | Establishes template versions, ownership, and controlled expansion. |

**Answers (confirmed direction - adjust retroactively if specifics change):**

- **B1:** Every document carries: document ID/name, template version, intake reference number (independent of charge code), requesting org/sponsor, technical contact, preparer name, current-record revision number/date, and page X of Y. Document ID and template version are maintainer-controlled and should not change per use; intake reference, contacts, and revision/date are confirmed or updated by whoever is completing that particular record. A marking/confidentiality band is reserved on every page but its actual text is pending organizational confirmation (see A9/Remaining Decisions).
- **B2:** Recur unchanged: the document-control/revision block, the requesting-organization/contact block, attachment-reference instructions, and the closing acknowledgement block style. Share layout only (content differs by document): the scope/requirements questions themselves, discipline-specific technical prompts, and acceptance-criteria wording - these look the same visually but ask different things on the Intake Form versus the Scope Definition Worksheet.
- **B3:** Primary trigger is **discipline** (mechanical, electrical, structural, systems, environmental); a secondary trigger is **activity type** (e.g., site visit/data collection needed, existing-asset assessment versus new design). A single request can require more than one discipline module at once (e.g., a retrofit needing both mechanical and electrical input), so selection should allow multiple simultaneous modules rather than a single pick.
- **B4:** Per document: instructions, field labels, required-field set, and the acknowledgement/approval block wording vary (e.g., intake form acknowledgement says "not a commitment"; scope confirmation acknowledgement says "ready for SOW preparation"). Per requester: nothing should vary structurally, since all requesters are internal departments under the same organization - avoid building client-specific template variants; only the entered content (names, project details) differs.
- **B5:** At intake (Document 1): contact info, problem statement, requested assistance/discipline, and desired timing are required; everything else may be marked Unknown/To be confirmed with a named follow-up owner and date. At scope definition (Document 4): inclusions, exclusions, deliverables, and acceptance criteria become required before the record can move to "Confirmed" status; remaining assumptions still carry forward as tracked open items rather than blocking progress indefinitely.
- **B6:** Can repeat without a fixed limit: contacts/stakeholders, requested disciplines, attachments/references, requirements rows, deliverables rows, and open assumptions/issues. Provide a small fixed number of inline rows (around 5) on the base form plus an explicit continuation-sheet reference for anything beyond that, since PDF form fields do not expand automatically.
- **B7:** Assign an **Intake Reference Number** at first contact (e.g., `ENG-2026-014`), independent of any later charge code, and carry it unchanged through every later document (Scope Definition Worksheet, eventual SOW). Requirements and deliverables get sub-identifiers under that same reference (e.g., `ENG-2026-014-R01`) so they remain traceable across revisions.
- **B8:** Each record carries a status (Draft / Under Review / Confirmed), author, and date, plus a revision-history table (revision, author, date, change summary). "Confirmed" is the frozen baseline used to prepare the SOW; prior revisions are retained as records rather than overwritten, so the history of what changed and when stays visible.
- **B9:** No prefilling for the first release - matches the A5/A6 answers of reusable blank forms only. If prefilling is evaluated later, the source should be a previously completed and reviewed PDF from the same project, not an external CRM or spreadsheet, since no such system has been identified yet.
- **B10:** No external client-accessibility or procurement-driven format requirements are expected, since these are internal departments rather than outside commercial clients. Plain, large-enough fonts and a clean print fallback should suffice. Flag for confirmation: whether an internal accessibility policy (e.g., Section 508-style requirement) applies to internal forms at this organization.
- **B11:** One build command per document (`.tex` -> `.pdf`) using the shared style file, so a branding change is made once and applies everywhere. No batch/package assembly needed yet, since documents are issued individually (per A6). Suggested output naming: `<IntakeReference>_<DocumentName>_v<#>.pdf`.
- **B12:** Only the maintaining engineer (later, possibly a technical writer) edits the shared template source. Each template release gets a version tag/date in the shared style. Previously issued, completed PDFs are static snapshots tied to the template version active when they were generated, so later template edits do not alter already-completed records.

## C. Business Content and Pilot Details

| ID | Question / missing detail | Used to refine |
|---|---|---|
| C1 | What information has been missing in past inquiries, causing estimate revisions, delays, or scope disputes? Provide anonymized examples where possible. | Question priorities and scope boundaries. |
| C2 | What deliverables do we commonly provide, in which formats, and who accepts them using what criteria? | Deliverable register and acceptance worksheet. |
| C3 | Which client inputs and responsibilities commonly affect our work: drawings, calculations, access, surveys, outages, approvals, or third-party coordination? | Dependencies and responsibility sections. |
| C4 | Which jurisdictions, codes, permitting authorities, or industry standards commonly apply, and who determines applicability? | Compliance modules and specialist review routing. |
| C5 | What schedule, budget, procurement, and contract information is appropriate to collect before a proposal? Is paid discovery an option when scope is too uncertain? | Qualification and pre-SOW readiness. |
| C6 | What approved acknowledgement language or signature process is required? Who reviews language to ensure intake confirmation is not authorization to start work? | Confirmation blocks and contractual boundaries. |
| C7 | What is an acceptable client completion time and document length at each stage? | Usability targets and placement of detail in addenda. |
| C8 | Which representative project and reviewers will pilot the package, and what outcomes will count as success? | Real-world acceptance of the workflow. |
| C9 | Which future document types are likely: proposal, SOW, site report, design review, change request, or closeout? Which shared elements should carry forward? | Expansion priorities without building them prematurely. |
| C10 | What retention period, access controls, and archive format apply to completed forms, attachments, and template versions? | Project-record handling. |

**Answers (confirmed direction - adjust retroactively if specifics change):**

- **C1:** Recurring gaps: the needed discipline isn't clear until after work starts, a deadline gets set before the effort is actually scoped, or a "quick look" turns into sustained work without a charge code being authorized first. The Intake Form's requested-assistance, timing, and acknowledgement sections are designed to surface these before they cause rework.
- **C2:** Common deliverables: engineering analyses/calculations, drawings or models, technical memos/reports, assessment or inspection findings, and recommendations. Acceptance is by the requesting sponsor or technical lead rather than a formal commercial customer sign-off.
- **C3:** Common requester inputs/responsibilities: existing drawings/specs, equipment data or manuals, site/facility access (possibly with escort or badging requirements given the larger organization), a responsive technical point of contact, and any prior studies. Site-access/security specifics are captured as attachment references and open items rather than hardcoded fields, since they vary by location.
- **C4:** Applicable standards: discipline-specific codes (e.g., electrical code, mechanical/structural design standards) plus any internal engineering standards or program-specific requirements. The form records applicability and the responsible reviewer rather than asserting compliance; exact standard names per discipline are filled in at the discipline-addendum level as they come up, rather than blocking the first release.
- **C5:** Since this is intra-company support rather than external sales, "budget" means **labor/resource availability and charge-code/funding authorization** rather than a commercial price quote. Informal discussion time is treated as overhead (unfunded); sustained investigation requires an authorized charge code - consistent with not implying unlimited unfunded support.
- **C6:** Acknowledgement wording: a statement that the completed intake form reflects current understanding only, does not commit the center's resources, and that the scope may change following further review. Route through center leadership for review/approval before first use rather than issuing it unreviewed.
- **C7:** Target: the Intake Form completable in roughly 15-30 minutes without requiring the requester to gather extensive materials first; later documents (scope definition, requirements) may reasonably take longer and span more than one review session.
- **C8:** Pilot with the **next real incoming request**, rather than a retrospective/hypothetical one, so lessons are captured from an actual case. Reviewers: the center lead plus one engineer from the relevant discipline.
- **C9:** Likely future documents, in rough order: the already-planned Scope Definition Worksheet, then an eventual SOW, a progress/status report, a change-request form, and a closeout/lessons-learned report. Shared elements to carry forward: the document-control block, the intake reference number, and the requesting-organization/contact section.
- **C10:** Retain completed intake and scope documents with the project record for the life of the engagement plus a standard retention period, with access limited to center staff and the requesting department, archived as PDF alongside the project folder.

## Proposed Default Architecture - Pending Answers

Use four layers, keeping content reuse separate from visual consistency:

1. **Shared style:** branding, page layout, headings, metadata display, and reusable text fields, selections, tables, and acknowledgement blocks.
2. **Shared content modules:** genuinely repeated sections such as contacts or attachment instructions, plus optional discipline/service addenda.
3. **Document entry points:** one small LaTeX entry file per document, selecting modules and supplying document-specific instructions and content. Keep unique sections here until reuse is demonstrated.
4. **Project data, if required:** one authoritative source for prefilled project metadata, separate from templates and from blank-form defaults. Do not embed client information in shared template files.

Start with explicit module selection and a single supported build method. Avoid a custom framework, extensive configuration, automated answer extraction, or many client variants until answers establish a need. A combined package can be added with document-qualified PDF field identifiers so similarly named fields do not unintentionally share values.

## Checks Before Calling the Template System Ready

- Each core document builds independently with the same shared style.
- If combined packages are required, selected documents assemble correctly without field-name collisions.
- A branding change updates all documents without editing each document separately.
- A representative optional module can be reused without copying its source; a unique question can be changed without affecting unrelated documents.
- If prefilling is required, updating shared project metadata updates the intended documents consistently.
- Digital answers survive save/reopen in the supported viewers; printing remains usable.
- Long answers and repeated items have a clear continuation method.
- Client outputs do not contain internal qualification or commercial assessments.
- The pilot meets agreed completion-time and scoping-readiness targets.

## Recommended Next Step

All sections are answered, and all 7 documents in the family are now built using the confirmed B1-B12 design rules and the C1-C10 content direction -- see [README.md](../README.md) for the current document list and [Engineering_Project_Intake_Plan.md](Engineering_Project_Intake_Plan.md) for implementation status. Update this file retroactively if real-world use (a pilot, a discipline lead's standards review, an actual retention policy) surfaces a different answer than assumed here.
