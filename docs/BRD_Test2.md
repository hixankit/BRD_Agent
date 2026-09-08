# Business Requirements Document — Test2 Project (College Library Book Issuing System)

| Field | Value |
| --- | --- |
| Project Name | Test2 |
| Project Code | To be defined |
| Document Version | 0.1 (Draft) |
| Date | To be defined |
| Document Owner | To be defined |
| Document Status | Draft for review |

## Revision History

| Version No. | Date | Prepared by / Modified by | Significant Changes |
| --- | --- | --- | --- |
| 0.1 | To be defined | BRD Agent | Initial draft for review |

## Glossary

| Abbreviation | Description |
| --- | --- |
| BRD | Business Requirements Document |
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |
| PASS/FAIL | Acceptance criterion outcome for a requirement |
| To be defined | Information not yet provided; to be supplied by a human stakeholder |

## Table of Contents

1. Introduction
   - 1.1 Purpose
   - 1.2 Scope
   - 1.3 Audience
   - 1.4 References
   - 1.5 Acronyms, Terms and Definitions
2. Project Drivers
   - 2.1 The purpose of the application
   - 2.2 Client, Customer and other Stakeholders
   - 2.3 Users of the Application
   - 2.4 Key success factors
3. Constraints
   - 3.1 Constraints
   - 3.2 Assumptions and Dependencies
4. Current State
   - 4.1 Stakeholder Problem and Desired State Capture
   - 4.2 Overview of current business environment
   - 4.3 Stakeholder Profiles
5. Functional Requirements
   - 5.1 Scope of work
   - 5.2 Scope of the Application
   - 5.3 Functional and Data Requirements
   - 5.4 Requirements summary
   - 5.5 How these requirements are organised
   - 5.6 Requirement priorities
   - 5.7 Functional Requirements (Core Functions)
6. Non-Functional Requirements
7. Business Implementation Requirements
   - 7.1 Issues
   - 7.2 Management Issues
   - 7.3 Open Questions
8. Annexures
   - Annexure 1: Requirements Shell for Reference
   - Annexure 2: Use Case Template
   - Annexure 3: Activity Diagram

---

# 1. Introduction

## 1.1 Purpose

The purpose of this Business Requirements Document is to define the business and system
requirements for the **Test2 Project** — a simple library book issuing system for a college.
The system will allow librarians to issue and return books to and from students and to
track due dates for borrowed books.

This document is the basis for solution design, development and system acceptance testing.
It captures the functional scope from the perspective of the business (a college library)
and the users (students and librarians) and should be used as the reference for all
subsequent project phases.

## 1.2 Scope

The scope of this document covers the requirements analysis for a single application: an
automated library book issuing system for a college. The system covers the core lending
operations of issuing and returning books and tracking due dates, along with the supporting
data required to perform those operations (books, students, librarians, loans).

Information outside the scope of this BRD includes the full library management lifecycle
(e.g. acquisitions, cataloguing standards, inter-library loans, online reservation and
self-service kiosks), which are instead listed as deferred or to-be-defined items unless
explicitly agreed by the business.

The system is scoped to a single college campus. Institutional-level or multi-campus
arrangements are out of scope unless confirmed.

## 1.3 Audience

This document is intended for:

- College/Library business stakeholders and decision makers
- The library manager and library staff (librarians)
- Student representatives
- Project sponsor, project manager, business analyst
- Solution architect and development team
- Quality assurance and user acceptance test teams
- Any external implementation vendor engaged for the project

## 1.4 References

| Reference | Description |
| --- | --- |
| `templates/Business_Requirement_Document_Template_FONT_BRD_v1_0.doc` | Standard Business Requirements Document template used as the basis for this document |
| Test2 Project Issue Description (AGEN-7) | Source material: "A simple library book issuing system for a college. Users: students, librarians. Core function: issue/return books, track due dates." |

## 1.5 Acronyms, Terms and Definitions

| Term / Acronym | Definition |
| --- | --- |
| Book | A library item available to be borrowed by a student |
| Loan | The association of a book with a student for a defined period, created at issue and closed at return |
| Issue | The action of a librarian recording that a book is lent to a student |
| Return | The action of a librarian recording that a borrowed book has been handed back |
| Due Date | The date by which a borrowed book must be returned |
| Student | A library user who borrows books |
| Librarian | A library staff member authorised to issue and return books and manage loans |
| FR | Functional Requirement |
| NFR | Non-Functional Requirement |

---

# 2. Project Drivers

## 2.1 The purpose of the application

The purpose of the application is to provide a simple, reliable way for a college library to:

- Record the issue of books to students
- Record the return of books by students
- Track due dates so that overdue books can be identified and followed up

## 2.2 Client, Customer and other Stakeholders

| Stakeholder Group | Role / Interest |
| --- | --- |
| College Library / Library Manager | Primary client; owns the lending service and is accountable for the availability and return of the library collection |
| Librarians | Operational users who will issue and return books daily |
| Students | Library users who borrow books; affected by how easily and correctly loans are recorded |
| College Administration / IT | May host, support and maintain the system; provides network and infrastructure |
| Project Sponsor / Management | Approves scope, budget and schedule; resolves priority conflicts |

Note: Named representatives for each stakeholder are **To be defined** — see Open Questions.

## 2.3 Users of the Application

| User Group | Description | Interface Expected |
| --- | --- | --- |
| Librarians | Library staff who process issues and returns and monitor due dates | System users with full lending-function access |
| Students | Borrowers of books; may look up their own loans and due dates | System users with limited, self-service (view-only) access |

## 2.4 Key success factors

The following are considered key to the success of the system:

| Success Factor | Measurement |
| --- | --- |
| Accurate loan record-keeping | Every issue and return is recorded correctly and traceable |
| Correct due-date calculation and tracking | Due dates are calculated on issue and visible on all loan records |
| Ease of use for librarians | Core operations (issue/return) can be completed quickly with minimal training |
| Reliability of the lending operation | The system is available during library opening hours and does not lose loan data |
| User adoption | Librarians and students use the system for all transactions rather than informal registers |

---

# 3. Constraints

## 3.1 Constraints

- **Scope of the business description:** The source information provided is minimal. Non-core library functions are out of scope for this release.
- **Budget and delivery timeframes:** To be defined by the project sponsor.
- **Technology platform:** To be defined.
- **Regulatory and institutional policy:** The system must comply with the college's library policy (which is to be confirmed) and any applicable data protection obligations related to student personal data.

## 3.2 Assumptions and Dependencies

Assumptions:

- A student is uniquely identifiable within the college (e.g. by student ID).
- A book copy is uniquely identifiable within the library (e.g. by accession/barcode number).
- The library collection and borrower base already exist; a backlog of existing loans, if any, will be migrated or recorded at cutover.
- Only issued books can be returned; only available book copies can be issued.
- A single book copy can be on loan to only one student at a time.

Dependencies:

- Confirmation of the college library lending rules (loan period, renewals, fines) — **To be defined**.
- Availability of student identity data or a mechanism to register students — **To be defined**.
- Confirmation of hosting and support arrangements — **To be defined**.

---

# 4. Current State

## 4.1 Stakeholder Problem and Desired State Capture

**Problem:** The college needs a simple system to manage book lending. Currently the details
of the existing process (manual registers, spreadsheets, or no system at all) are **To be
defined**. What is known is that the library must record which student has which book and
when it is due back.

**Desired State:** A simple application where:

- A librarian can issue a book to a student and the system records the loan and due date.
- A librarian can record the return of a book and the system closes the loan.
- The due date of any active loan can be tracked, allowing the library to identify overdue books.

## 4.2 Overview of current business environment

- **Existing business environment:** To be defined. The current means by which books are
  issued and returned is not documented in the available material.
- **Existing application environment:** To be defined. Any existing library or student
  information systems, and the extent to which this application must integrate with them,
  have not been stated.

## 4.3 Stakeholder Profiles

### 4.3.1 Librarians

| Attribute | Detail |
| --- | --- |
| Representative | To be defined |
| Description | Library staff who operate the lending desk |
| Stakeholder's title | Librarian |
| Involvement | Perform issue and return transactions; monitor and act on overdue loans; provide day-to-day feedback |
| Success Criteria | Issue and return operations are quick and accurate; loan records (with due dates) are always correct and viewable |
| Deliverables | Participation in requirements review, user acceptance testing and training |
| Comments and Issues | To be defined |

### 4.3.2 Students

| Attribute | Detail |
| --- | --- |
| Representative | To be defined |
| Description | College students who borrow books |
| Stakeholder's title | Student |
| Involvement | Borrow books; view their own loan and due-date information |
| Success Criteria | Loans are recorded correctly so students are not held accountable for returns they have made; due dates are visible |
| Deliverables | Feedback on usability of the student view |
| Comments and Issues | To be defined |

### 4.3.3 College Library Management

| Attribute | Detail |
| --- | --- |
| Representative | To be defined |
| Description | Management accountable for the library collection and lending service |
| Stakeholder's title | Library Manager |
| Involvement | Defines lending policy, approves scope, signs off the BRD |
| Success Criteria | The system reduces misplacement/loss of books through reliable tracking and provides a view of outstanding loans |
| Deliverables | Lending-policy rules, sign-off, resources for testing and training |
| Comments and Issues | To be defined |

---

# 5. Functional Requirements

## 5.1 Scope of work

The requirement study covers the complete lending operation of the college library in its
intended environment: the records and business events needed to support the issue and
return of books and the tracking of due dates. The boundaries of this study are:

| In Scope | Out of Scope (for this release) |
| --- | --- |
| Issuing books to students | Acquisitions and book procurement |
| Returning books / closing loans | Full cataloguing and shelf management standards |
| Tracking due dates and identifying overdue loans | Self-service kiosks and online booking/reservations |
| Recording books, students and loans as system data | Inter-library loans |
| Student and librarian identity sufficient to record loans | Fines/payments processing (may be a future enhancement) |
| Viewing a student's own loans and due dates | Multi-campus / institutional federations |

The project will not deliver functions that a reader might otherwise assume — e.g. online
browsing, reservations, or notifications — unless explicitly agreed later (refer also to
Section 7.1, Deferred Requirements).

## 5.2 Scope of the Application

The application boundary is the library lending desk and the student self-service view.
The primary actors, represented by use cases, are:

- **Librarian:** issues a book to a student; records a book return.
- **Student:** examines an active loan and its due date.

Use case diagrams and descriptions will be produced during design, one per functional
requirement end-to-end, with fit criteria as defined in Section 5.7.

## 5.3 Functional and Data Requirements

The core business objects for this system are:

| Business Object | Statement of Purpose | Key Attributes (initial) |
| --- | --- | --- |
| Student | Identifies the borrower | Student ID, name, department, contact details |
| Book | Identifies a borrowable library item (copy) | Accession/barcode number, title, author, availability status |
| Loan | Records that a book is issued to a student with a due date | Loan ID, student, book copy, issue date, due date, return date |

The relationship between the objects: a **Student** may hold many **Loans**; a **Book**
(copy) is held by at most one **Loan** at a time; a **Loan** refers to exactly one
**Student** and one **Book**. A data model will be confirmed during design.

## 5.4 Requirements summary

The system will support the core lending business of the college library. A librarian will
issue a book to a student, which creates a loan with a calculated due date. A librarian will
record a return, which closes the loan with the actual return date. The system will track
all active loans and their due dates so that overdue items can be identified. Students will
be able to view their own active loans and due dates.

## 5.5 How these requirements are organised

Each requirement is a single, testable statement with a unique number to enable traceability
from this analysis through to User Acceptance Test development. Requirements are grouped by
business function and each is presented as a numbered list with a unique ID prefixed `FR-`
followed by a sequence number. These requirements will form the basis of system acceptance.
Each item can be tested to give a PASS/FAIL result. Detailed supporting information is
provided in the annexures to this document.

## 5.6 Requirement priorities

The priority of each requirement is listed against the requirement statement:

| Priority | Meaning |
| --- | --- |
| Must Have | Fundamental to the project's success |
| Should Have | Important, but project success does not rely on it |
| Could Have | Can easily be left out without impacting the project |
| Future | Will not be met in the short term |
| Business Process | Met with a business process rather than a system process |

## 5.7 Functional Requirements (Core Functions)

### 5.7.1 Core Function — Issue a Book

Rationale: the primary purpose of the system is to record that a book is lent to a student,
together with the date it must be returned.

| ID | Detailed Requirement | Priority |
| --- | --- | --- |
| FR-001 | The system shall allow a librarian to issue a book to a student by selecting a student and a book copy. | Must Have |
| FR-002 | The system shall create a loan record on issue, capturing the student, book copy, issue date and calculated due date. | Must Have |
| FR-003 | The system shall prevent issuing a book copy that is already on loan to another student, or otherwise unavailable. | Must Have |
| FR-004 | The system shall calculate and record the due date on issue, based on the configured loan period. | Must Have |
| FR-005 | The system shall provide confirmation of the completed issue, including the student, book and due date. | Should Have |

Acceptance criteria (testable PASS/FAIL):

- **FR-001 — PASS** if a librarian can complete an issue transaction by selecting any registered student and any available book copy; **FAIL** otherwise.
- **FR-002 — PASS** if, after a successful issue, a loan record exists containing the student ID, book copy ID, issue date (today) and a due date; **FAIL** otherwise.
- **FR-003 — PASS** if the system rejects an issue attempt where the chosen book copy is already on an active loan and provides a clear message; **FAIL** otherwise.
- **FR-004 — PASS** if the due date equals the issue date plus the configured loan period and is stored on the loan; **FAIL** otherwise.
- **FR-005 — PASS** if the UI displays a confirmation with the student, book and due date after each issue; **FAIL** otherwise.

### 5.7.2 Core Function — Return a Book

Rationale: closing a loan correctly is what keeps the lending records accurate and prevents
students being held accountable for books they have returned.

| ID | Detailed Requirement | Priority |
| --- | --- | --- |
| FR-006 | The system shall allow a librarian to record the return of an issued book. | Must Have |
| FR-007 | The system shall close the associated loan on return, recording the actual return date. | Must Have |
| FR-008 | The system shall set the book copy back to available status once its loan is closed. | Must Have |
| FR-009 | The system shall clearly indicate when a returned book was overdue (return date later than due date). | Should Have |

Acceptance criteria (testable PASS/FAIL):

- **FR-006 — PASS** if a librarian can complete a return transaction for any loan that is currently active; **FAIL** otherwise.
- **FR-007 — PASS** if, after a return, the loan shows the actual return date and is no longer active; **FAIL** otherwise.
- **FR-008 — PASS** if the book copy can immediately be issued again after return; **FAIL** otherwise.
- **FR-009 — PASS** if the system flags or indicates overdue status for a returned loan whose return date is later than its due date; **FAIL** otherwise.

### 5.7.3 Core Function — Track Due Dates / Overdue Loans

Rationale: tracking due dates is what enables the library to follow up on books not returned
on time, protecting the collection.

| ID | Detailed Requirement | Priority |
| --- | --- | --- |
| FR-010 | The system shall store and display the due date for every active loan. | Must Have |
| FR-011 | The system shall provide a view/report of all active loans, including their due dates. | Must Have |
| FR-012 | The system shall identify and list overdue loans (due date earlier than today and loan still active). | Must Have |
| FR-013 | The system shall allow a student to view their own active loans and their due dates. | Should Have |

Acceptance criteria (testable PASS/FAIL):

- **FR-010 — PASS** if the due date shown on each active loan matches the date calculated at issue; **FAIL** otherwise.
- **FR-011 — PASS** if a librarian can retrieve a list of all active loans with due dates from the system; **FAIL** otherwise.
- **FR-012 — PASS** if a librarian can retrieve a list containing exactly the active loans whose due date is earlier than today; **FAIL** otherwise.
- **FR-013 — PASS** if a student is able to view only their own active loans and due dates, and cannot see other students' loans; **FAIL** otherwise.

### 5.7.4 Core Function — Maintain Master Data

Rationale: issue and return operations depend on reliable records of students and books.

| ID | Detailed Requirement | Priority |
| --- | --- | --- |
| FR-014 | The system shall allow registered students to be added, updated and identified for lending. | Must Have |
| FR-015 | The system shall allow book copies to be added, updated and identified for lending. | Must Have |
| FR-016 | The system shall allow the loan period (used for due-date calculation) to be configured by an authorised administrator. | Should Have |

Acceptance criteria (testable PASS/FAIL):

- **FR-014 — PASS** if a student record can be created/updated and is then selectable in an issue transaction; **FAIL** otherwise.
- **FR-015 — PASS** if a book copy record can be created/updated and is then selectable in an issue transaction; **FAIL** otherwise.
- **FR-016 — PASS** if changing the configured loan period changes the due date calculated for subsequent issues; **FAIL** otherwise.

---

# 6. Non-Functional Requirements

Non-functional requirements define how well, or to what level, each facility should be
provided. Each is presented as numbered, testable requirements.

## 6.1 Audit

- **NFR-001** The system shall record, for each issue and return, who performed the action and when. Priority: Must Have.
- **NFR-002** The system shall record changes to student and book master data (who and when). Priority: Should Have.

Acceptance: **PASS** if each issue/return and master-data change is traceable to a
user ID and timestamp; otherwise **FAIL**.

## 6.2 Security

- **NFR-003** Access to issue and return functions shall be restricted to authorised librarian accounts. Priority: Must Have.
- **NFR-004** Student access shall be limited to viewing their own loans. Priority: Must Have.

Acceptance: **PASS** if an unauthorised account cannot perform librarian functions and a
student cannot view another student's loans; otherwise **FAIL**.

## 6.3 Privacy and Confidentiality

- **NFR-005** Student personal data shall be handled in line with applicable data-protection requirements and college policy. Priority: Must Have.

Acceptance: **PASS** if the handling of student data complies with the confirmed college
data-protection policy; otherwise **FAIL**.

## 6.4 User Access

- **NFR-006** Librarians shall access the system through a defined interface (web/desktop — To be defined). Priority: Must Have.
- **NFR-007** Students shall have a self-service view covering only their own loans and due dates. Priority: Should Have.

Acceptance: **PASS** if each user group can reach exactly the functions assigned to it via
the agreed interface; otherwise **FAIL**.

## 6.5 Usability

- **NFR-008** The core issue and return operations shall be completable in no more than a defined number of steps (target to be confirmed). Priority: Should Have.
- **NFR-009** The system shall display clear messages for validation failures (e.g. book already on loan). Priority: Should Have.

Acceptance: **PASS** if usability is confirmed in user acceptance testing against the agreed
criteria; otherwise **FAIL**.

## 6.6 Health and Safety, Ergonomics

- **NFR-010** No specific requirement identified. (Standard office ergonomics apply; no additional statutory health-and-safety obligations identified beyond those that apply to routine administrative work.)

## 6.7 Internationalisation

- **NFR-011** No specific requirement identified. The system's language, currency, date formats and time zones are single-locale (college environment) unless the business states otherwise.

## 6.8 Integration

- **NFR-012** To be defined. Any integration with the college's student records, identity or other systems has not yet been stated by the business.

## 6.9 Performance

- **NFR-013** The expected number of concurrent users and acceptable response times are To be defined. Target indicative requirement: routine issue/return transactions shall complete without perceptible delay on the operational network.

Acceptance: **PASS** if response times are within the limits confirmed by the business;
otherwise **FAIL**.

## 6.10 Availability, Reliability, Backup and Recovery

- **NFR-014** The system shall be available during library opening hours. Exact hours and uptime target: To be defined. Priority: Must Have.
- **NFR-015** Loan data shall be backed up and recoverable so that no completed issue or return is lost following a failure. Priority: Must Have.

Acceptance: **PASS** if the system is available for the agreed opening hours and a
recovered backup retains all completed transactions; otherwise **FAIL**.

## 6.11 Supportability

- **NFR-016** User and technical documentation for the system shall be provided. Priority: Should Have.

Acceptance: **PASS** if operating and user guides are delivered and accepted; otherwise **FAIL**.

## 6.12 Volumes

- **NFR-017** The expected numbers of books, students, loans and transactions are To be defined and must be confirmed by the library.

Acceptance: **PASS** if the system performs within agreed response times at the confirmed
volumes; otherwise **FAIL**.

---

# 7. Business Implementation Requirements

This section advises the business of the scope and depth of the implementation, focusing on
user involvement in training, testing and any migration.

## 7.1 Issues

### 7.1.1 Open Issues

| Issue | Impact | Action |
| --- | --- | --- |
| Lending policy (loan period, renewals, fines) not defined | Due-date calculation and overdue handling depend on it | Library management to confirm |
| Student identity source (student ID from where?) not defined | Registration of students for lending | College IT / administration to confirm |
| Existing loan backlog, if any, to be migrated or re-recorded | Accuracy of due-date tracking at go-live | Library to confirm |
| Hosting and support arrangements not defined | Availability and supportability targets | Project sponsor / IT to confirm |

### 7.1.2 New Problems

- Possible pitfalls during implementation include: incorrect due-date calculation if the
  loan period is misconfigured; data-entry errors if book/student identifiers are not
  easily scannable or searchable; and a manual return being performed twice or against the
  wrong loan. These will be mitigated through validation rules (e.g. FR-003) and
  confirmation steps (e.g. FR-005).

### 7.1.3 Deferred Requirements

- Notifications/reminders of due dates (e.g. email) — candidate for a future release.
- Fines and payment processing for overdue books — candidate for a future release.
- Online catalogue browsing, reservations and self-service checkout — candidates for a future release.

### 7.1.4 Ideas for Solutions

- Use book barcodes/student ID cards to speed up issue/return data entry.
- Provide a simple overdue-loans list printed/exported for the library to follow up.
- Keep the student view minimal and read-only to avoid complexity in the first release.

## 7.2 Management Issues

### 7.2.1 Impact on existing units

The expected effects on the library lending desk and on any existing manual/automated
processes are **To be defined**. Staffing and workflow-boundary impacts will be confirmed
once the current state is documented (Section 4.2).

### 7.2.2 Data ownership

Ownership of the loan data and of the student master data used by the system is **To be
defined**. The library should be accountable for loan data; responsibility for archiving
and retention will be confirmed with the college.

### 7.2.3 User Training

- **NFR-018** Librarians shall receive training covering issue, return and overdue tracking. Priority: Must Have.
- **NFR-019** Students shall receive brief guidance on viewing their own loans and due dates. Priority: Should Have.

Acceptance: **PASS** if all librarians complete training before go-live and are able to
execute the core functions unaided; otherwise **FAIL**.

The training approach (courses, user guides, involvement in testing) is **To be defined**,
as is the responsible owner. Training costings are out of scope of this document.

### 7.2.4 Requirement priorities

The implementation priority of the components, if the project is phased, is **To be
defined**. A single-phase delivery of Sections 5.7.1–5.7.3 is the recommended baseline.

### 7.2.5 Data conversion

Any conversion of existing loan records into the new system, and the procedure for doing so,
is **To be defined**. Where the library currently uses manual registers, a baseline of
currently-outstanding loans should be recorded at cutover if required.

### 7.2.6 Delivery issues

Delivery considerations such as source-code retention, escrow and warranty periods are
**To be defined** by the project sponsor and any vendor.

### 7.2.7 Migration and cutover

Migration requirements, requirement for parallel running during cutover, and how the system
handles the transition from any existing process are **To be defined**.

## 7.3 Open Questions

The following items need human input to complete this BRD:

1. College library lending policy — loan period, renewals, fines for overdue books.
2. Source of student identity data and how students are registered in the system.
3. Whether there is an existing loan backlog that must be recorded/migrated at go-live.
4. Hosting, infrastructure and support arrangements.
5. Technology platform and preferred user interfaces (web/desktop/mobile) for librarians and students.
6. Expected system volumes (number of books, students, loans per day) and performance targets.
7. Budget and delivery timeframes.
8. Integration requirements with other college systems (student records, e-mail, etc.).
9. Access channels (portal, intranet) and authentication mechanism.
10. Document owner, date, and named stakeholder representatives for the Profiles in Section 4.3.

---

# 8. Annexures

## Annexure 1: Requirements Shell for Reference

Requirements are defined in this document using the requirement-shell style (as per the
`Requirements Shell.xls` referenced by the standard template): each requirement has a unique
ID, a single testable statement, a priority and a PASS/FAIL acceptance criterion as shown in
Section 5.7.

## Annexure 2: Use Case Template

Requirements may be elaborated using the following use-case representation during design
(for guidance only):

| Element | Description |
| --- | --- |
| Title | Use-case name indicating the goal of the use-case |
| Actors | Name of the actors invoking the use-case, and whether initiating or participating |
| Status | Open, Closed, On-hold, Suspended, Cancelled |
| Description | Textual description of the use-case |
| Flow of Events | Numbered/bulleted steps of the primary flow |
| Sub-flow / Alternate Flows | Alternative paths to the primary flow |
| Special Requirements | Performance and UI-specific concerns |
| Assumptions / Pre-conditions | Conditions that must exist before the use-case runs |
| Post-conditions | The state of the system after the use-case runs |
| User Interface | Reference to UI prototype or screen |
| Business Rules | Domain rules, algorithms and validations (e.g. due-date calculation) |
| Entities / Business Concepts | E.g. Student, Book, Loan |
| Related Use Cases | Use cases that include, extend or specialise this one |
| Issues | Clarifications required from the user |
| Reference | Requirement #, documents, persons, authors |
| Risk Assessment | Risk factor, probability, impact, mitigation strategy |
| Data Requirements | Entity, information element, source, retention, audit/tracking requirements |
| Revision Log | Modified by, date, version, description |

## Annexure 3: Activity Diagram

Business processes and workflow can be described using activity diagrams expressed in the
Unified Modeling Language (UML). For this project, activity diagrams will be produced during
design to model the issue and return workflows (including overdue identification). These
diagrams show the sequential and parallel activities of the lending business process and
support the analysis of the use cases defined under Section 5.7.