# Project Planning and Management

| | |
|---|---|
| **Project** | DotTeach - Online Learning Platform |
| **Programme** | DEPI - Digital Egypt Pioneers Initiative |
| **Track** | Full Stack .NET |
| **Group Code** | SWD5_S4 |
| **Team** | Abdelrhman Osama (Team Lead), Abdelrhman Raoof, Omar Mohamed |
| **Version** | 1.0 (initial submission) |
| **Date** | 20 October 2026 |

## Contents

1. [Project Proposal](#project-proposal) - owner: Abdelrhman Osama, reviewer: Omar Mohamed
2. [Project Plan](#project-plan) - owner: Abdelrhman Osama, reviewer: Omar Mohamed
3. [Task Assignment and Roles](#task-assignment-and-roles) - owner: Abdelrhman Osama, reviewer: Abdelrhman Raoof
4. [Risk Assessment and Mitigation Plan](#risk-assessment-and-mitigation-plan) - owner: Abdelrhman Raoof, reviewer: Abdelrhman Osama
5. [Key Performance Indicators (KPIs)](#key-performance-indicators-kpis) - owner: Omar Mohamed, reviewer: Abdelrhman Raoof

---

## Project Proposal

**Document owner:** Abdelrhman Osama | **Reviewer:** Omar Mohamed

### 1. Executive Summary

**DotTeach** is a web-based online learning platform. Instructors build and publish video courses organised into sections and lessons. Students browse the catalogue, enroll in free or paid courses, learn at their own pace, take quizzes, track their progress, and earn verifiable PDF certificates when they finish a course. Administrators keep the platform healthy by managing users, approving courses and monitoring sales and engagement.

The project is the graduation project of the DEPI **Full Stack .NET** track. It is based on the *EduHub - Online Learning Platform* proposal in the programme's project booklet and is built with **ASP.NET Core MVC** using an **N-Tier architecture** and the **Repository**, **Unit of Work**, **Strategy**, **Observer** and **Dependency Injection** patterns.

### 2. Background and Problem Statement

Online learning is now a normal way to gain skills, but the experience for the two main groups of users is still uneven:

- **Instructors and small training providers** need a simple way to turn their material into a structured, professional course, to protect their videos from uncontrolled sharing, to charge for their work, and to see how learners are doing.
- **Learners** need one place where they can find relevant courses, pay securely, continue exactly where they stopped, check their understanding through quizzes, and receive proof of completion that others can verify.
- **Platform administrators** need control over quality (what gets published) and visibility into usage and revenue.

DotTeach addresses these needs in a single, maintainable web application whose architecture cleanly separates the user interface, business rules and data access, so that it can grow after the programme ends.

### 3. Project Objectives

| # | Objective | How it will be measured |
|---|---|---|
| O1 | Deliver a working multi-role platform (Student, Instructor, Admin) with secure authentication and role-based access control. | All "Must" authentication and authorisation requirements pass testing. |
| O2 | Let instructors create, organise and publish video courses with secure streaming. | An instructor can create a course with sections, lessons and videos, submit it for approval and publish it end to end. |
| O3 | Give students a complete learning journey: enroll, pay (free and paid courses), watch, track progress, take quizzes, receive a certificate. | The full journey is demonstrated without manual intervention. |
| O4 | Provide administrators with user management, a course approval workflow, and sales and engagement analytics. | Admin features pass testing and charts display live data. |
| O5 | Apply the N-Tier, Repository, Unit of Work and Dependency Injection patterns consistently, with documented, tested, version-controlled code. | Code review checklist and test results (see KPI document). |
| O6 | Deploy the system to a live environment and deliver the complete documentation set required by DEPI. | Public deployment link and all DEPI deliverables available in the GitHub repository. |

### 4. Scope

Priorities follow the MoSCoW method (**M**ust, **S**hould, **C**ould). The detailed list with identifiers is in the *Requirements Gathering* folder.

#### 4.1 In scope

**Must have (core, committed)**
- Registration, login and logout; roles: Student, Instructor, Admin
- Course catalogue with search, category and level filters, and course details page
- Instructor dashboard: create/edit/delete courses, sections and lessons, video upload and secure streaming
- Enrollment in free courses and payment for paid courses (Stripe in **test mode**)
- Student learning page: video player, lesson completion, progress per course, "My Courses" page
- Quiz system with minimum passing score
- PDF certificate with a unique verification code
- Admin: user management, course approval workflow, category management

**Should have (planned, delivered if time allows after the Must items)**
- Shopping cart for several courses, coupon codes and discounts (Strategy pattern)
- Course ratings and written reviews
- Purchase history and receipts
- Public certificate verification page
- Analytics dashboards (Chart.js): best-selling courses, completion rates, instructor earnings, revenue trend
- Password reset by e-mail

**Could have (stretch)**
- Drag-and-drop course builder, bulk upload, Q&A and announcements
- Notes and bookmarks while watching, resume from last position
- In-app notifications using the Observer pattern
- LinkedIn sharing for certificates, Arabic localisation

#### 4.2 Out of scope
- Native mobile applications
- Live (real-time) classes and video conferencing
- Real-money payment processing in production (payments are demonstrated in test mode only)
- AI-based recommendations or automated content moderation
- Multi-tenant or white-label deployment

### 5. Target Users

| User | Description |
|---|---|
| **Student** | Learner who browses, enrolls in, and completes courses. |
| **Instructor** | Subject expert who creates, publishes and manages courses and quizzes. |
| **Administrator** | Platform operator who manages users, approves courses and reviews analytics. |

### 6. Proposed Solution and Technical Approach

| Layer / Concern | Approach |
|---|---|
| Architecture | N-Tier: `DotTeach.Web` (presentation), `DotTeach.Services` (business logic), `DotTeach.Data` (data access) |
| Web framework | ASP.NET Core MVC with Razor views |
| Data access | Entity Framework Core, Repository pattern, Unit of Work pattern; SQL Server |
| Authentication | ASP.NET Core Identity with roles (Student, Instructor, Admin) |
| Design patterns | Repository, Unit of Work, Dependency Injection, Strategy (pricing and discounts), Observer (progress tracking and notifications) |
| Media storage | Azure Blob Storage for videos, delivered through time-limited signed URLs |
| Payments | Stripe (test mode) |
| Certificates | PDF generation with iTextSharp |
| Front end | Bootstrap 5, jQuery, Video.js, Progress.js, Chart.js |
| Deployment | Microsoft Azure (App Service, Blob Storage); final hosting choice confirmed during the design phase |
| Collaboration | GitHub organisation, feature branches, pull requests, GitHub Projects board |

The technologies above follow the EduHub proposal in the project booklet and will be finalised in the *Software Architecture* and *Technology Stack* sections of the System Analysis and Design deliverable.

### 7. Expected Deliverables

Following the DEPI Project Documentation Guidelines:

1. **Project Planning and Management** - proposal, project plan, task assignment and roles, risk assessment, KPIs
2. **Literature Review** - review of existing platforms, feedback and evaluation, suggested improvements, grading criteria
3. **Requirements Gathering** - stakeholder analysis, user stories and use cases, functional and non-functional requirements
4. **System Analysis and Design** - problem statement, use case, ER, DFD, sequence, activity, state, class, deployment and component diagrams, wireframes, technology stack
5. **Implementation** - source code, README, branching strategy, commit history, deployed application link
6. **Testing and Quality Assurance** - test plan and cases, automated tests, bug reports
7. **Final Presentation and Reports** - user manual, technical documentation, presentation, project infographic, optional demo video

### 8. Key Dates (DEPI schedule)

| Deliverable | Due date |
|---|---|
| Project Planning and Management, Literature Review, Requirements Gathering | 16 Oct 2026 (extended to 20 Oct 2026 by the instructor) |
| System Analysis and Design | 6 Nov 2026 |
| Implementation (source code and execution) | 30 Nov 2026 |
| Final Presentation, Testing and Reports | 4 Dec 2026 |

### 9. Assumptions and Constraints

**Assumptions**
- Each team member can dedicate regular weekly time to the project alongside other commitments.
- Free tiers or student credits are sufficient for cloud services during development and evaluation.
- Stripe test mode is acceptable for demonstrating payments.

**Constraints**
- Fixed DEPI deadlines (see section 8) that cannot move.
- A team of three members, so scope is prioritised with MoSCoW and the Must items are protected first.
- Only technologies and skills that the team can learn and apply within the project period.

### 10. Team

| Member | Role |
|---|---|
| Abdelrhman Osama | Team Lead and Project Manager |
| Abdelrhman Raoof | Team Member |
| Omar Mohamed | Team Member |

Detailed responsibilities are defined in the *Task Assignment and Roles* document.

---

## Project Plan

**Document owner:** Abdelrhman Osama | **Reviewer:** Omar Mohamed

### 1. Approach

The project runs from **20 October to 4 December 2026**, aligned with the DEPI deadlines. Work is organised into five phases. The implementation phase is split into one-week sprints so that progress is visible, reviewable and measurable every week, matching the instructor's weekly individual evaluation.

Planning rules:
- Every deliverable has one owner and one reviewer.
- Work is tracked on a GitHub Projects board in the team organisation; each task links to an issue.
- Scope is protected by priority: all **Must** requirements are finished before any **Should** or **Could** requirement is started.
- The system is deployed early (skeleton in the first sprints) so that deployment problems are found long before the deadline.

### 2. Timeline (Gantt Chart)

```mermaid
gantt
    title DotTeach Project Timeline - 20 Oct to 4 Dec 2026
    dateFormat YYYY-MM-DD
    axisFormat %d %b

    section 1 Planning and Requirements
    Project Planning and Management        :p1, 2026-10-20, 1d
    Literature Review                      :p2, 2026-10-20, 1d
    Requirements Gathering                 :p3, 2026-10-20, 1d
    Planning docs delivered                :milestone, m1, 2026-10-20, 0d

    section 2 System Analysis and Design
    Problem statement and use case diagram :d1, 2026-10-21, 5d
    Software architecture                  :d2, 2026-10-23, 4d
    ER diagram and database schema         :d3, 2026-10-24, 7d
    DFD, sequence, activity, state, class  :d4, 2026-10-28, 8d
    Wireframes and UI/UX guidelines        :d5, 2026-10-30, 7d
    Tech stack, deployment, component      :d6, 2026-11-02, 5d
    Design delivered                       :milestone, m2, 2026-11-06, 0d

    section 3 Implementation
    Sprint 0 - Solution skeleton and Identity :i0, 2026-11-01, 6d
    Sprint 1 - Catalogue and instructor dashboard :i1, 2026-11-07, 7d
    Sprint 2 - Video, enrollment, learning, admin approval :i2, 2026-11-14, 7d
    Sprint 3 - Payments, quizzes, certificates, reviews :i3, 2026-11-21, 7d
    Stabilisation and deployment           :i4, 2026-11-28, 3d
    Implementation delivered               :milestone, m3, 2026-11-30, 0d

    section 4 Testing and QA
    Test plan and test cases               :t1, 2026-11-07, 7d
    Continuous testing and bug fixing      :t2, 2026-11-14, 17d
    Final regression testing               :t3, 2026-11-28, 5d

    section 5 Final Presentation and Reports
    User manual and technical documentation :r1, 2026-11-24, 8d
    Presentation, infographic, demo video   :r2, 2026-11-28, 6d
    Final delivery                          :milestone, m4, 2026-12-04, 0d
```

### 3. Phases and Milestones

| Phase | Period | Milestone | DEPI due date |
|---|---|---|---|
| 1. Planning and Requirements | 20 Oct | **M1** - Planning and Management, Literature Review and Requirements Gathering published in GitHub | 16 Oct (extended to 20 Oct) |
| 2. System Analysis and Design | 21 Oct - 6 Nov | **M2** - All analysis and design documents and wireframes published | 6 Nov |
| 3. Implementation | 1 Nov - 30 Nov | **M3** - Source code, README and deployed application | 30 Nov |
| 4. Testing and QA | 7 Nov - 2 Dec | Test plan, test cases, bug reports, automated tests | part of 4 Dec |
| 5. Final Presentation and Reports | 24 Nov - 4 Dec | **M4** - User manual, technical documentation, presentation, infographic | 4 Dec |

### 4. Implementation Sprints

| Sprint | Dates | Planned outcome |
|---|---|---|
| **Sprint 0** | 1 - 6 Nov | N-Tier solution skeleton (`Web`, `Services`, `Data`), entities and migrations from the ER diagram, generic repository and Unit of Work, ASP.NET Identity with the three roles, CI build on GitHub |
| **Sprint 1** | 7 - 13 Nov | Course catalogue with search and filters, course details page, instructor dashboard, course/section/lesson CRUD |
| **Sprint 2** | 14 - 20 Nov | Video upload and secure streaming, free-course enrollment, student learning page with progress tracking, "My Courses", admin course-approval workflow and category management |
| **Sprint 3** | 21 - 27 Nov | Stripe payment (test mode), quiz system, certificate generation with verification code, reviews and ratings, admin user management, analytics (as time allows), UI polish |
| **Stabilisation** | 28 - 30 Nov | Bug fixing, performance check, code freeze, production deployment, README finalised |

A sprint is "done" only when its features are merged to `main` through reviewed pull requests, tested, and deployed to the staging environment.

### 5. Deliverables

| Phase | Deliverables |
|---|---|
| Planning and Requirements | Proposal, plan, task assignment, risk assessment, KPIs; literature review; stakeholder analysis, user stories and use cases, functional and non-functional requirements |
| Design | Problem statement, use case diagram and descriptions, software architecture, ER diagram, logical and physical schema, DFD, sequence, activity, state and class diagrams, wireframes and mockups, UI/UX guidelines, technology stack, deployment and component diagrams, API documentation (if APIs are exposed) |
| Implementation | Well-commented source code, coding standards, GitHub repository with branching strategy and meaningful commit history, README (installation, system requirements, configuration, execution guide), deployed web application |
| Testing | Test plan and test cases, automated tests, bug reports |
| Final | User manual, technical documentation, project presentation (PPT/PDF), project infographic, optional video demonstration |

### 6. Resource Allocation

#### 6.1 People

| Member | Primary responsibility | Approximate share of effort |
|---|---|---|
| Abdelrhman Osama | Project management, architecture, data layer, identity, instructor and video modules, deployment | one third |
| Abdelrhman Raoof | Catalogue, student learning experience, enrollment and payments, quizzes | one third |
| Omar Mohamed | UI/UX, reviews, certificates, admin panel, analytics | one third |

Effort is shared equally across the team; individual module ownership is listed in the *Task Assignment and Roles* document.

#### 6.2 Tools and services

| Purpose | Tool / Service |
|---|---|
| Source control and collaboration | GitHub organisation, repository, Issues, Projects board, Pull Requests |
| Development | Visual Studio / Visual Studio Code, .NET SDK, SQL Server and SSMS |
| Cloud | Microsoft Azure (App Service, Blob Storage) using free tier or student credits |
| Payments | Stripe test account |
| Diagrams and design | Mermaid (rendered by GitHub), draw.io, a wireframing tool chosen in the design phase |
| Communication | Team group chat and a fixed weekly meeting |

#### 6.3 Budget

The project is planned at **zero cost**, relying on free tiers, student credits, open-source libraries and Stripe test mode.

### 7. Monitoring and Communication

- **Weekly team meeting** (30-45 minutes): progress against the sprint plan, blockers, next week's tasks.
- **GitHub Projects board**: columns *Backlog, In Progress, In Review, Done*; every pull request needs one review from another member.
- **Weekly instructor evaluation**: each member prepares a short update of their own completed work.
- **Progress measured with the KPIs** defined in the *KPIs* document, reviewed at each sprint end.

### 8. Dependencies

| Dependency | Needed by |
|---|---|
| Approved ER diagram and schema | Sprint 0 |
| Wireframes approved by the team | Sprint 1 |
| Azure subscription and Blob Storage account | Sprint 2 |
| Stripe test account and keys | Sprint 3 |
| Instructor's grading criteria and feedback | Literature Review and final reports |

---

## Task Assignment and Roles

**Document owner:** Abdelrhman Osama | **Reviewer:** Abdelrhman Raoof

### 1. Team and Roles

| Member | Role | Main areas |
|---|---|---|
| **Abdelrhman Osama** | Team Lead and Project Manager; Backend and Architecture | Planning, architecture, data layer, identity, instructor and video modules, deployment, repository administration |
| **Abdelrhman Raoof** | Full Stack Developer; Requirements and Student Experience | Requirements analysis, catalogue, learning experience, enrollment and payments, quizzes |
| **Omar Mohamed** | Full Stack Developer; UI/UX and Admin | Literature review, UI/UX, reviews, certificates, admin panel, analytics, quality of non-functional requirements |

The team lead is accountable for delivery and for communication with the instructor. All members are responsible for the quality of what they own, for reviewing a colleague's work, and for presenting their own contribution in the final presentation.

### 2. Documentation Tasks (current phase)

| # | Deliverable | Owner | Reviewer | Due |
|---|---|---|---|---|
| 1 | Project Proposal | Abdelrhman Osama | Omar Mohamed | 20 Oct 2026 |
| 2 | Project Plan (Gantt, milestones, resources) | Abdelrhman Osama | Omar Mohamed | 20 Oct 2026 |
| 3 | Task Assignment and Roles | Abdelrhman Osama | Omar Mohamed | 20 Oct 2026 |
| 4 | Risk Assessment and Mitigation Plan | Abdelrhman Raoof | Abdelrhman Osama | 20 Oct 2026 |
| 5 | Stakeholder Analysis | Abdelrhman Raoof | Abdelrhman Osama | 20 Oct 2026 |
| 6 | User Stories and Use Cases | Abdelrhman Raoof | Abdelrhman Osama | 20 Oct 2026 |
| 7 | KPIs | Omar Mohamed | Abdelrhman Raoof | 20 Oct 2026 |
| 8 | Literature Review | Omar Mohamed | Abdelrhman Raoof | 20 Oct 2026 |
| 9 | Functional Requirements | Omar Mohamed | Abdelrhman Raoof | 20 Oct 2026 |
| 10 | Non-functional Requirements | Omar Mohamed | Abdelrhman Raoof | 20 Oct 2026 |

Review is cyclic: Osama's documents are reviewed by Omar, Omar's by Raoof, Raoof's by Osama.

### 3. System Analysis and Design Tasks (due 6 Nov 2026)

| Task | Owner | Support |
|---|---|---|
| Problem statement and objectives | Abdelrhman Osama | - |
| Use case diagram and descriptions | Abdelrhman Raoof | Abdelrhman Osama |
| Software architecture (N-Tier) and technology stack | Abdelrhman Osama | - |
| ER diagram, logical and physical schema | Abdelrhman Osama | Abdelrhman Raoof |
| DFD (context level and detailed) | Abdelrhman Raoof | - |
| Sequence and activity diagrams | Abdelrhman Raoof | Omar Mohamed |
| State and class diagrams | Abdelrhman Osama | Omar Mohamed |
| Wireframes, mockups, UI/UX guidelines | Omar Mohamed | Abdelrhman Raoof |
| Deployment and component diagrams | Abdelrhman Osama | - |

### 4. Implementation Module Ownership (initial assignment)

The ownership below is the starting point and will be confirmed at the end of the design phase.

| Module | Owner | Planned sprint |
|---|---|---|
| M1 N-Tier skeleton, EF Core entities, Repository and Unit of Work | Abdelrhman Osama | 0 |
| M2 Identity, roles and role-based access control | Abdelrhman Osama | 0 |
| M3 Course catalogue, search, filters, course details | Abdelrhman Raoof | 1 |
| M4 Instructor dashboard, course / section / lesson management | Abdelrhman Osama | 1 |
| M5 Video upload and secure streaming (Azure Blob Storage) | Abdelrhman Osama | 2 |
| M6 Student learning page, progress tracking, My Courses | Abdelrhman Raoof | 2 |
| M7 Enrollment, cart, Stripe payments, coupons (Strategy pattern) | Abdelrhman Raoof | 2-3 |
| M8 Quiz system | Abdelrhman Raoof | 3 |
| M9 Reviews and ratings | Omar Mohamed | 3 |
| M10 Certificate generation and verification | Omar Mohamed | 3 |
| M11 Admin panel: users, course approval, categories | Omar Mohamed | 2-3 |
| M12 Analytics dashboards (Chart.js) | Omar Mohamed | 3 |
| M13 Deployment and CI | Abdelrhman Osama | 0 and final |
| UI/UX implementation, shared layout and theme | Omar Mohamed | 0-3 |
| Testing: test plan, automated tests, bug reports | All members, for their own modules | 1-3 |
| Final reports: user manual, technical documentation, presentation, infographic | All members, coordinated by Abdelrhman Osama | final |

### 5. Working Agreements

**Version control**
- Repository hosted in the team GitHub organisation; `main` always contains working, reviewed code.
- Feature branching: `feature/<module>-<short-description>`, e.g. `feature/m3-course-search`; documentation branches `docs/<topic>`.
- Every change reaches `main` through a pull request with a clear description and at least one review by another member.
- Commit messages are meaningful and written in the imperative, e.g. `Add course search filter by category`.

**Quality**
- Definition of done: code compiles, follows the coding standards, handles errors and validates input, is tested, is reviewed and is merged.
- Code follows C# naming conventions, uses dependency injection and keeps business rules in the Services layer.

**Communication**
- Weekly meeting at a fixed time; urgent issues are raised in the team chat.
- Blockers are reported within 24 hours so the team lead can re-plan.
- Each member keeps a short record of their completed tasks for the weekly instructor evaluation.

**Change control**
- Changes to scope or ownership are agreed by the team and recorded in the GitHub Projects board.

---

## Risk Assessment and Mitigation Plan

**Document owner:** Abdelrhman Raoof | **Reviewer:** Abdelrhman Osama

### 1. Method

Each risk is rated for **likelihood (L)** and **impact (I)** on a scale of 1 (low) to 3 (high). The **score** is L x I:

| Score | Level | Action |
|---|---|---|
| 7 - 9 | **High** | Mitigation starts immediately; reviewed weekly by the team lead |
| 4 - 6 | **Medium** | Mitigation planned and monitored at each sprint end |
| 1 - 3 | **Low** | Accepted and watched |

The register is reviewed at every weekly meeting and updated by the document owner.

### 2. Risk Register

| ID | Risk | Category | L | I | Score | Mitigation (prevent) | Contingency (if it happens) | Owner |
|---|---|---|---|---|---|---|---|---|
| R1 | Small team (three members) and limited weekly capacity, below the 4-6 members recommended by DEPI | Resources | 3 | 3 | **9 High** | Confirm the team size with the instructor; prioritise with MoSCoW; protect Must items first; split ownership by module | Drop Could items, then Should items, in a pre-agreed order; reduce depth of analytics | Abdelrhman Osama |
| R2 | Schedule slip because the first documentation deadline was missed and later deadlines are close (6 Nov, 30 Nov, 4 Dec) | Schedule | 3 | 3 | **9 High** | Weekly plan with owners; documentation tasks scheduled inside each sprint; start coding foundation (Sprint 0) while design finishes | Re-plan the sprint, cut scope, ask the instructor early for guidance | Abdelrhman Osama |
| R3 | Learning curve of ASP.NET Core MVC, Entity Framework Core and the design patterns | Technical | 3 | 2 | **6 Medium** | Build the skeleton first with a shared reference implementation; pair on the first module of each pattern; short internal knowledge-sharing sessions | Simplify the implementation (e.g. fewer custom repositories), seek help from the instructor | Abdelrhman Raoof |
| R4 | Scope creep from adding features beyond the agreed list | Scope | 2 | 3 | **6 Medium** | Requirements baselined with IDs and priorities; change control through the project board | Reject or postpone the new item; record it in "future improvements" | Abdelrhman Osama |
| R5 | Video upload, storage and streaming are more complex than expected (Azure Blob Storage, large files, signed URLs) | Technical | 2 | 3 | **6 Medium** | Prototype video upload in Sprint 2 week one; keep the first version simple (direct upload, signed URL streaming, manual thumbnail) | Fall back to hosted video links or local storage for the demonstration | Abdelrhman Osama |
| R6 | Stripe integration issues, or live payments not possible | Technical | 2 | 2 | **4 Medium** | Use Stripe test mode only; integrate early in Sprint 3; keep payment behind an interface (Strategy/DI) | Use a simulated payment provider that follows the same interface | Abdelrhman Raoof |
| R7 | Cloud cost or free-tier limits exceeded (Azure) | Cost | 2 | 2 | **4 Medium** | Use free tiers and student credits; set spending alerts; keep test videos small | Move the demonstration to a cheaper host or run locally for the presentation | Abdelrhman Osama |
| R8 | A team member becomes unavailable (exams, illness, other commitments) | Resources | 2 | 3 | **6 Medium** | Every module documented and reviewed by a second member; avoid single-person knowledge; shared repository | Redistribute modules by priority; the team lead takes over critical-path items | Abdelrhman Osama |
| R9 | Merge conflicts and broken `main` branch | Technical | 2 | 2 | **4 Medium** | Feature branches, small pull requests, mandatory review, build check on every pull request | Revert the faulty commit; fix on a branch | Abdelrhman Osama |
| R10 | Security weaknesses (unauthorised access to paid videos, insecure authentication, exposed secrets) | Security | 2 | 3 | **6 Medium** | Identity with roles, authorisation attributes, anti-forgery tokens, signed time-limited video URLs, no secrets in the repository, no card data stored | Security review before deployment; rotate any exposed key at once | Abdelrhman Raoof |
| R11 | Deployment problems discovered too late | Technical | 2 | 3 | **6 Medium** | Deploy the empty skeleton in Sprint 0; deploy at the end of every sprint | Use the previous working deployment; keep a local demo ready | Abdelrhman Osama |
| R12 | Unclear grading criteria or expectations for deliverables (for example, the Literature Review contents) | Requirements | 2 | 2 | **4 Medium** | Ask the instructor to confirm expectations and record the answer; keep templates ready to adapt | Adapt documents quickly using the instructor's feedback | Abdelrhman Osama |
| R13 | Documentation falls behind the code | Quality | 2 | 2 | **4 Medium** | Documentation tasks included in every sprint; README and technical documentation updated with each module | Dedicated documentation days before each deadline | Omar Mohamed |
| R14 | Loss of work or data (accidental deletion, laptop failure) | Technical | 1 | 3 | **3 Low** | All work pushed to GitHub daily; database creation and seed scripts kept in the repository | Restore from the repository | All members |
| R15 | Poor performance with many users or large videos | Technical | 1 | 2 | **2 Low** | Pagination, caching of catalogue queries, CDN for video delivery if available | Reduce page size; optimise queries | Omar Mohamed |

### 3. Risk Matrix

| Likelihood \ Impact | 1 Low | 2 Medium | 3 High |
|---|---|---|---|
| **3 High** | | R3 | **R1, R2** |
| **2 Medium** | | R6, R7, R9, R12, R13 | R4, R5, R8, R10, R11 |
| **1 Low** | | R15 | R14 |

### 4. Top Risks and Immediate Actions

1. **R1 and R2 (team size and schedule)** - Agree the Must / Should / Could list now and confirm the team size with the instructor. Start Sprint 0 while the design phase is finishing.
2. **R5 (video)** - Prototype Azure Blob upload and signed-URL streaming at the start of Sprint 2.
3. **R8 (member availability)** - Every module has a primary owner and a second person who has reviewed it.

### 5. Review Schedule

| When | Activity |
|---|---|
| Weekly meeting | Review risk status and add new risks |
| End of each sprint | Re-score risks and close those that no longer apply |
| Before each DEPI deadline | Full review of schedule and quality risks |

---

## Key Performance Indicators (KPIs)

**Document owner:** Omar Mohamed | **Reviewer:** Abdelrhman Raoof

### 1. Purpose

These KPIs define what "success" means for DotTeach and how the team will measure it. They are grouped into **product KPIs** (is the system good?) and **project KPIs** (is the project well run?). Targets are the team's agreed goals for the final evaluation and will be reviewed at the end of each sprint.

### 2. Product KPIs

| ID | KPI | Target | How it is measured | When |
|---|---|---|---|---|
| P1 | **Response time** of main pages (catalogue, course details, My Courses) | 95% of requests in 3 seconds or less under normal use | Browser developer tools and a simple load test on the deployed site | Each sprint end |
| P2 | **Video start time** | 5 seconds or less on a normal connection | Manual timing in the deployed system | Sprint 2 and final |
| P3 | **System uptime** during the evaluation period | 99% or higher | Deployment platform monitoring or an uptime check | Final month |
| P4 | **Core journey success** (register, enroll, learn, finish, receive certificate) | Works end to end with no manual fix | Scripted walkthrough on the deployed system | Each sprint end after Sprint 2 |
| P5 | **Payment success in test mode** | 100% of test cases pass (successful, failed, cancelled) | Stripe test cards | Sprint 3 |
| P6 | **Requirement coverage** | 100% of Must and at least 80% of Should requirements implemented | Requirements traceability table | Sprint 3 and final |
| P7 | **Test pass rate** | At least 90% of planned test cases pass; **0 open critical or high bugs** at delivery | Test plan and bug reports | Final |
| P8 | **Usability** | System Usability Scale (SUS) score of 68 or higher from at least 10 test users | Short SUS questionnaire after a guided task | Stabilisation |
| P9 | **User adoption** (pilot) | At least 10 pilot users register and at least 5 complete one course lesson set | Platform data from the pilot | Stabilisation |
| P10 | **Security checks** | 0 known authorisation bypasses; paid video not reachable without enrollment | Manual security checklist | Before deployment |

### 3. Project KPIs

| ID | KPI | Target | How it is measured | When |
|---|---|---|---|---|
| M1 | **On-time delivery of DEPI milestones** | 100% of milestones from now on delivered by the due date | Plan versus submission dates | Each deadline |
| M2 | **Sprint plan completion** | At least 85% of planned tasks completed per sprint | GitHub Projects board | Each sprint end |
| M3 | **Review coverage** | 100% of merged pull requests reviewed by another member | GitHub pull request history | Weekly |
| M4 | **Individual contribution visibility** | Every member merges at least 3 meaningful pull requests per sprint | GitHub insights | Each sprint end |
| M5 | **Meeting attendance** | 100% attendance at the weekly meeting (or written update if absent) | Meeting notes | Weekly |
| M6 | **Documentation completeness** | 100% of items in the DEPI Project Documentation Guidelines present in the repository | Checklist against the guidelines | Each deadline |
| M7 | **Code quality** | Build passes on every pull request; coding standards respected; no secrets in the repository | Build status and review checklist | Continuous |
| M8 | **Risk management** | No High risk open for more than one week without a mitigation action | Risk register | Weekly |

### 4. Reporting

- The KPI table is updated at the end of each sprint and discussed in the weekly meeting.
- Results are included in the final technical documentation and the final presentation.
- A KPI that is missed twice in a row triggers an action in the risk register.

### 5. Dashboard Template

| KPI | Target | Sprint 1 | Sprint 2 | Sprint 3 | Final |
|---|---|---|---|---|---|
| P1 Response time | 95% within 3 s | | | | |
| P4 Core journey | Pass | | | | |
| P6 Requirement coverage | 100% Must | | | | |
| P7 Test pass rate | 90% or higher | | | | |
| M2 Sprint completion | 85% or higher | | | | |
| M3 Review coverage | 100% | | | | |
