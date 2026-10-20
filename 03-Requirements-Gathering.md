# Requirements Gathering

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

1. [Stakeholder Analysis](#stakeholder-analysis) - owner: Abdelrhman Raoof, reviewer: Abdelrhman Osama
2. [User Stories and Use Cases](#user-stories-and-use-cases) - owner: Abdelrhman Raoof, reviewer: Abdelrhman Osama
3. [Functional Requirements](#functional-requirements) - owner: Omar Mohamed, reviewer: Abdelrhman Raoof
4. [Non-functional Requirements](#non-functional-requirements) - owner: Omar Mohamed, reviewer: Abdelrhman Raoof

---

## Stakeholder Analysis

**Document owner:** Abdelrhman Raoof | **Reviewer:** Abdelrhman Osama

### 1. Purpose

This document identifies the people and organisations who use, build, fund, evaluate or are affected by DotTeach, and records what each of them needs. The needs feed directly into the user stories, use cases and requirements.

### 2. Stakeholder Register

| ID | Stakeholder | Type | Role in relation to the system |
|---|---|---|---|
| SH1 | Students (learners) | Primary user | Browse, enroll, pay, learn, take quizzes, receive certificates |
| SH2 | Instructors | Primary user | Create and publish courses, upload videos, build quizzes, monitor learners and earnings |
| SH3 | Administrators | Primary user | Manage users, approve courses, manage categories, view analytics |
| SH4 | Project team (Abdelrhman Osama, Abdelrhman Raoof, Omar Mohamed) | Internal | Plan, design, build, test, deploy and document the system |
| SH5 | DEPI instructor / lecturer and evaluation committee | Sponsor and evaluator | Guides the team, evaluates deliverables and the final presentation |
| SH6 | DEPI initiative (Digital Egypt Pioneers) | Sponsor | Sets the programme requirements, schedule and documentation guidelines |
| SH7 | Payment provider (Stripe) | External service | Processes course payments (test mode) |
| SH8 | Cloud provider (Microsoft Azure) | External service | Hosts the application and stores video files |
| SH9 | Employers and third parties verifying certificates | Indirect user | Check that a certificate is genuine |

### 3. Needs and Expectations

| Stakeholder | Needs and expectations | Main related requirements |
|---|---|---|
| **Students** | Easy search and filtering; clear course information and reviews; secure and simple payment; smooth video playback; resume where they stopped; visible progress; fair quizzes with instant feedback; a certificate they can show to others; data privacy | FR-CAT, FR-ENR, FR-LRN, FR-QZ, FR-CRT, NFR-PERF, NFR-USA |
| **Instructors** | A simple way to organise content into sections and lessons; reliable video upload; control over price and level; protection of videos; statistics on enrollment and earnings; the ability to publish and edit courses | FR-INS, FR-VID, FR-QZ, NFR-SEC |
| **Administrators** | Quality control before publication; control of users and categories; reports on sales and engagement; a secure admin area | FR-ADM, FR-ANL, NFR-SEC |
| **Project team** | Clear scope and priorities; maintainable architecture; a realistic schedule; a clean Git history | Proposal, plan, NFR-MNT |
| **DEPI lecturer and committee** | Complete documentation on GitHub on time; evidence of individual contribution; a working, deployed system; a clear final presentation | All DEPI deliverables, KPIs M1-M6 |
| **DEPI initiative** | Compliance with the programme's guidelines and deadlines | Documentation guidelines |
| **Stripe** | Correct use of the API; no handling of raw card data by DotTeach | FR-ENR, NFR-SEC |
| **Azure** | Correct configuration, storage limits respected, costs controlled | NFR-DEP, risk R7 |
| **Verifiers** | A public page that confirms a certificate using its code | FR-CRT-03 |

### 4. Influence / Interest Grid

| | Low interest | High interest |
|---|---|---|
| **High influence** | DEPI initiative (SH6), Cloud provider (SH8) | DEPI lecturer and committee (SH5), Project team (SH4) |
| **Low influence** | Verifiers (SH9) | Students (SH1), Instructors (SH2), Administrators (SH3), Payment provider (SH7) |

**Engagement strategy**

| Group | Strategy |
|---|---|
| High influence, high interest | Manage closely: weekly progress, early feedback, formal deliverables |
| High influence, low interest | Keep satisfied: follow the programme rules and deadlines |
| Low influence, high interest | Keep informed and involved: pilot testing, usability questionnaire, feedback on wireframes |
| Low influence, low interest | Monitor: design the verification page so it needs no account |

### 5. Requirements Elicitation Methods

| Method | Use in this project |
|---|---|
| Document analysis | Project booklet (EduHub proposal), DEPI guidelines, existing platforms (see Literature Review) |
| Benchmarking | Comparison of Udemy, Coursera, Moodle and Khan Academy |
| Team workshops | Brainstorming and prioritising features using MoSCoW |
| Instructor consultation | Confirming expectations and deliverables with the DEPI lecturer |
| Prototype feedback | Wireframes shown to potential students and instructors during design |
| Pilot testing | Usability questionnaire and observation near the end of the project |

---

## User Stories and Use Cases

**Document owner:** Abdelrhman Raoof | **Reviewer:** Abdelrhman Osama

### 1. Actors

| Actor | Description |
|---|---|
| **Visitor** | Anyone who is not logged in |
| **Student** | Registered learner |
| **Instructor** | Registered course creator |
| **Administrator** | Platform operator |
| **Stripe** (external system) | Payment provider |
| **Azure Blob Storage** (external system) | Video storage |

### 2. User Stories

Format: *As a <role>, I want <goal>, so that <benefit>.* Priority uses MoSCoW (M / S / C). "FR" links to the functional requirement.

#### 2.1 Account and access

| ID | Story | Priority | FR |
|---|---|---|---|
| US-01 | As a visitor, I want to register as a student or an instructor, so that I can use the platform. | M | FR-AUTH-01 |
| US-02 | As a registered user, I want to log in and log out securely, so that my account is protected. | M | FR-AUTH-02 |
| US-03 | As a user, I want to reset my password by e-mail, so that I can recover my account. | S | FR-AUTH-03 |
| US-04 | As a user, I want to edit my profile, so that my information stays correct. | S | FR-AUTH-05 |

#### 2.2 Discovering courses

| ID | Story | Priority | FR |
|---|---|---|---|
| US-05 | As a visitor, I want to browse published courses, so that I can see what is available. | M | FR-CAT-01 |
| US-06 | As a student, I want to search and filter by category, level, price and rating, so that I find a suitable course quickly. | M | FR-CAT-02, FR-CAT-03 |
| US-07 | As a student, I want a course page with the curriculum, instructor and reviews, so that I can decide before enrolling. | M | FR-CAT-04 |

#### 2.3 Enrolling and paying

| ID | Story | Priority | FR |
|---|---|---|---|
| US-08 | As a student, I want to enroll in a free course with one click, so that I can start learning immediately. | M | FR-ENR-01 |
| US-09 | As a student, I want to pay for a paid course securely, so that I get access to it. | M | FR-ENR-02 |
| US-10 | As a student, I want to add several courses to a cart and pay once, so that purchasing is convenient. | S | FR-ENR-03 |
| US-11 | As a student, I want to apply a coupon code, so that I can get a discount. | S | FR-ENR-04 |
| US-12 | As a student, I want to see my purchase history and receipts, so that I have a record of what I paid. | S | FR-ENR-05 |

#### 2.4 Learning

| ID | Story | Priority | FR |
|---|---|---|---|
| US-13 | As a student, I want to watch lesson videos in a full-featured player, so that I can learn comfortably. | M | FR-LRN-01 |
| US-14 | As a student, I want lessons to be marked complete and see a progress bar, so that I know how far I have come. | M | FR-LRN-02, FR-LRN-03 |
| US-15 | As a student, I want a "My Courses" page, so that I can continue learning quickly. | M | FR-LRN-04 |
| US-16 | As a student, I want to resume from where I stopped, so that I do not waste time. | C | FR-LRN-05 |
| US-17 | As a student, I want to take notes and bookmark lessons, so that I can review later. | C | FR-LRN-06 |
| US-18 | As a student, I want to take a quiz at the end of a section or course, so that I can test my understanding. | M | FR-QZ-02 |
| US-19 | As a student, I want instant results with explanations, so that I learn from my mistakes. | S | FR-QZ-04 |
| US-20 | As a student, I want to rate and review a course I took, so that I can help other learners. | S | FR-REV-01 |

#### 2.5 Certificates

| ID | Story | Priority | FR |
|---|---|---|---|
| US-21 | As a student, I want a PDF certificate when I complete a course, so that I can prove my achievement. | M | FR-CRT-01 |
| US-22 | As an employer, I want to verify a certificate by its code on a public page, so that I can trust it. | S | FR-CRT-03 |
| US-23 | As a student, I want to share my certificate on LinkedIn, so that my network can see it. | C | FR-CRT-04 |

#### 2.6 Instructor

| ID | Story | Priority | FR |
|---|---|---|---|
| US-24 | As an instructor, I want to create a course with a title, description, price, level and thumbnail, so that learners understand it. | M | FR-INS-01 |
| US-25 | As an instructor, I want to organise a course into sections and lessons, so that learners follow a clear structure. | M | FR-INS-02 |
| US-26 | As an instructor, I want to upload videos that are stored and streamed securely, so that only enrolled students can watch. | M | FR-VID-01, FR-VID-02 |
| US-27 | As an instructor, I want to save a course as a draft and submit it for approval, so that I publish only when it is ready. | M | FR-INS-04 |
| US-28 | As an instructor, I want to create quizzes with several question types and a passing score, so that I can assess learners. | M | FR-QZ-01 |
| US-29 | As an instructor, I want to see enrollment numbers and revenue, so that I understand how my course performs. | S | FR-INS-05 |
| US-30 | As an instructor, I want to reorder lessons by drag and drop, so that editing is fast. | C | FR-INS-06 |
| US-31 | As an instructor, I want to answer student questions and post announcements, so that I support my learners. | C | FR-INS-07 |

#### 2.7 Administrator

| ID | Story | Priority | FR |
|---|---|---|---|
| US-32 | As an administrator, I want to review and approve or reject submitted courses, so that quality stays high. | M | FR-ADM-02 |
| US-33 | As an administrator, I want to manage users (view, block, change role), so that the platform stays safe. | M | FR-ADM-01 |
| US-34 | As an administrator, I want to manage categories and tags, so that the catalogue is organised. | M | FR-ADM-03 |
| US-35 | As an administrator, I want sales and engagement charts, so that I can monitor the platform. | S | FR-ANL-01 |

### 3. Use Case List

| ID | Use case | Primary actor | Related stories |
|---|---|---|---|
| UC-01 | Register account | Visitor | US-01 |
| UC-02 | Log in / log out | Student, Instructor, Administrator | US-02 |
| UC-03 | Browse and search courses | Visitor, Student | US-05, US-06 |
| UC-04 | View course details | Visitor, Student | US-07 |
| UC-05 | Enroll in a free course | Student | US-08 |
| UC-06 | Purchase a paid course | Student, Stripe | US-09, US-10, US-11 |
| UC-07 | Watch lesson and track progress | Student | US-13, US-14, US-15 |
| UC-08 | Take quiz | Student | US-18, US-19 |
| UC-09 | Receive and download certificate | Student | US-21 |
| UC-10 | Verify certificate | Visitor (verifier) | US-22 |
| UC-11 | Rate and review course | Student | US-20 |
| UC-12 | Create and edit course content | Instructor | US-24, US-25 |
| UC-13 | Upload lesson video | Instructor, Azure Blob Storage | US-26 |
| UC-14 | Create quiz | Instructor | US-28 |
| UC-15 | Submit course for approval | Instructor | US-27 |
| UC-16 | View instructor statistics | Instructor | US-29 |
| UC-17 | Approve or reject course | Administrator | US-32 |
| UC-18 | Manage users | Administrator | US-33 |
| UC-19 | Manage categories | Administrator | US-34 |
| UC-20 | View analytics | Administrator | US-35 |

#### Use cases by actor

| Actor | Use cases |
|---|---|
| Visitor | UC-01, UC-03, UC-04, UC-10 |
| Student | UC-02, UC-03, UC-04, UC-05, UC-06, UC-07, UC-08, UC-09, UC-11 |
| Instructor | UC-02, UC-12, UC-13, UC-14, UC-15, UC-16 |
| Administrator | UC-02, UC-17, UC-18, UC-19, UC-20 |

The formal use case diagram is part of the System Analysis and Design deliverable.

### 4. Use Case Descriptions (key scenarios)

#### UC-01 Register account
| | |
|---|---|
| **Actor** | Visitor |
| **Precondition** | The visitor has no account |
| **Main flow** | 1. Visitor opens the registration page. 2. Chooses a role (Student or Instructor). 3. Enters name, e-mail and password. 4. System validates the data and checks that the e-mail is unique. 5. System creates the account with the selected role. 6. System logs the user in and shows the home page. |
| **Alternative flows** | 4a. Invalid data or duplicate e-mail: the system shows an error message and keeps the entered values. |
| **Postcondition** | A new account with the correct role exists |

#### UC-03 Browse and search courses
| | |
|---|---|
| **Actor** | Visitor / Student |
| **Precondition** | At least one course is published |
| **Main flow** | 1. User opens the catalogue. 2. System lists published courses with pagination. 3. User types a keyword and/or selects category, level, price range or rating. 4. System returns the matching courses. 5. User opens a course. |
| **Alternative flows** | 4a. No result: the system shows a "no courses found" message with suggestions. |
| **Postcondition** | The user sees the courses that match the criteria |

#### UC-06 Purchase a paid course
| | |
|---|---|
| **Actor** | Student (secondary actor: Stripe) |
| **Precondition** | The student is logged in and not yet enrolled in the course |
| **Main flow** | 1. Student selects "Buy". 2. Optionally enters a coupon code and the system applies the discount (Strategy pattern). 3. System creates a Stripe payment session and redirects the student. 4. Student pays. 5. Stripe confirms the payment. 6. System records the order and enrollment in a single transaction (Unit of Work). 7. System shows the receipt and opens the course. |
| **Alternative flows** | 2a. Invalid coupon: the system shows a message and keeps the original price. 5a. Payment failed or cancelled: no enrollment is created and the student can retry. |
| **Postcondition** | Order and enrollment are saved; the student has access to the course |

#### UC-07 Watch lesson and track progress
| | |
|---|---|
| **Actor** | Student |
| **Precondition** | The student is enrolled in the course |
| **Main flow** | 1. Student opens a course from "My Courses". 2. System shows the curriculum and the progress bar. 3. Student selects a lesson. 4. System requests a time-limited signed URL for the video and plays it. 5. When the lesson ends (or the student marks it complete), the system saves the progress. 6. The system updates the course progress percentage. |
| **Alternative flows** | 4a. The student is not enrolled: access is denied and the course page is shown. |
| **Postcondition** | Lesson completion and course progress are stored |

#### UC-08 Take quiz
| | |
|---|---|
| **Actor** | Student |
| **Precondition** | The student is enrolled and the quiz is available |
| **Main flow** | 1. Student opens the quiz. 2. System shows the questions. 3. Student answers and submits. 4. System calculates the score. 5. System shows the result, the passing status and (if enabled) explanations. |
| **Alternative flows** | 5a. Score is below the passing score: the student may retake the quiz. |
| **Postcondition** | The attempt and score are saved |

#### UC-09 Receive and download certificate
| | |
|---|---|
| **Actor** | Student |
| **Precondition** | The student completed all required lessons and passed all required quizzes |
| **Main flow** | 1. System detects that the course is complete. 2. System generates a PDF containing the student's name, course title, completion date and a unique verification code. 3. Student downloads the certificate from the profile or the course page. |
| **Alternative flows** | 1a. Requirements not met: the certificate is not issued and the system shows what remains. |
| **Postcondition** | A certificate record with a unique code exists |

#### UC-10 Verify certificate
| | |
|---|---|
| **Actor** | Visitor (verifier) |
| **Precondition** | The verifier has a certificate code |
| **Main flow** | 1. Verifier opens the public verification page. 2. Enters the code. 3. System looks up the certificate. 4. System shows the student name, course and date. |
| **Alternative flows** | 3a. Code not found: the system shows "certificate not found". |
| **Postcondition** | None |

#### UC-12 / UC-13 / UC-15 Create, upload and submit a course
| | |
|---|---|
| **Actor** | Instructor (secondary actor: Azure Blob Storage) |
| **Precondition** | The instructor is logged in |
| **Main flow** | 1. Instructor creates a course (title, description, price, level, thumbnail). 2. Adds sections and lessons. 3. Uploads a video for each lesson; the system stores it in Blob Storage. 4. Optionally adds quizzes. 5. Previews the course. 6. Saves as draft or submits for approval. |
| **Alternative flows** | 3a. Upload fails or file type is not allowed: the system shows an error and the instructor can retry. 6a. Required information is missing: submission is blocked and the missing items are listed. |
| **Postcondition** | The course exists as a draft or is waiting for approval |

#### UC-17 Approve or reject course
| | |
|---|---|
| **Actor** | Administrator |
| **Precondition** | At least one course is waiting for approval |
| **Main flow** | 1. Administrator opens the approval queue. 2. Reviews the course content. 3. Approves: the course becomes published and visible. |
| **Alternative flows** | 3a. Rejects with a comment: the course returns to draft and the instructor is notified. |
| **Postcondition** | The course status is Published or Rejected |

---

## Functional Requirements

**Document owner:** Omar Mohamed | **Reviewer:** Abdelrhman Raoof

### 1. Conventions

- **ID format**: `FR-<AREA>-<NN>`
- **Priority**: **M** = Must (committed), **S** = Should (planned), **C** = Could (stretch)
- **Actor**: V = Visitor, S = Student, I = Instructor, A = Administrator, Sys = System
- Each requirement is testable and is traced to user stories (see *User Stories and Use Cases*).

### 2. Authentication and Authorisation (AUTH)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-AUTH-01 | The system shall allow a visitor to register as a Student or an Instructor using name, e-mail and password. | V | M |
| FR-AUTH-02 | The system shall allow registered users to log in and log out. | S, I, A | M |
| FR-AUTH-03 | The system shall allow users to reset their password through an e-mail link. | S, I | S |
| FR-AUTH-04 | The system shall enforce role-based access control with three roles (Student, Instructor, Administrator), restricting pages and actions by role. | Sys | M |
| FR-AUTH-05 | The system shall allow users to view and edit their profile. | S, I | S |
| FR-AUTH-06 | The system shall confirm the e-mail address of new accounts. | Sys | C |

### 3. Course Catalogue (CAT)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-CAT-01 | The system shall list published courses with pagination. | V, S | M |
| FR-CAT-02 | The system shall allow searching courses by title and keyword. | V, S | M |
| FR-CAT-03 | The system shall allow filtering by category, level and price range, and sorting by newest, price and rating. | V, S | M |
| FR-CAT-04 | The system shall provide a course details page showing description, curriculum, instructor, price, level and reviews. | V, S | M |
| FR-CAT-05 | The system shall support category navigation. | V, S | S |

### 4. Instructor and Course Management (INS)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-INS-01 | The system shall allow an instructor to create, edit and delete their courses (title, description, price, level, thumbnail). | I | M |
| FR-INS-02 | The system shall allow an instructor to organise a course into sections and lessons and to edit or delete them. | I | M |
| FR-INS-03 | The system shall allow an instructor to set the price (free or paid) and discounts of a course. | I | M |
| FR-INS-04 | The system shall support the course statuses Draft, Pending Approval, Published and Rejected; an instructor can save a draft and submit it for approval. | I | M |
| FR-INS-05 | The system shall show an instructor the number of enrollments and revenue of their courses. | I | S |
| FR-INS-06 | The system shall allow reordering sections and lessons by drag and drop, and previewing the course before publishing. | I | C |
| FR-INS-07 | The system shall allow an instructor to answer student questions and post announcements per course. | I | C |
| FR-INS-08 | The system shall support bulk upload of lessons. | I | C |

### 5. Video Management (VID)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-VID-01 | The system shall allow instructors to upload lesson videos (allowed formats and maximum size defined in the design) to Azure Blob Storage. | I | M |
| FR-VID-02 | The system shall stream videos only to enrolled students, the course instructor and administrators, using time-limited signed URLs. | Sys | M |
| FR-VID-03 | The system shall store each video's duration and URL with the lesson. | Sys | M |
| FR-VID-04 | The system shall generate a thumbnail for each uploaded video. | Sys | C |

### 6. Enrollment and Payment (ENR)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-ENR-01 | The system shall allow a student to enroll in a free course. | S | M |
| FR-ENR-02 | The system shall allow a student to pay for a paid course through Stripe (test mode) and enroll after confirmed payment. | S | M |
| FR-ENR-03 | The system shall provide a shopping cart that allows purchasing several courses in one payment. | S | S |
| FR-ENR-04 | The system shall apply coupon codes and discounts using interchangeable pricing strategies (Strategy pattern). | S | S |
| FR-ENR-05 | The system shall store orders and show the student a purchase history and receipt. | S | S |
| FR-ENR-06 | The system shall save the order, payment record and enrollment in a single transaction (Unit of Work); if any step fails, none is saved. | Sys | M |
| FR-ENR-07 | The system shall not store card numbers or card security data. | Sys | M |

### 7. Learning Experience (LRN)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-LRN-01 | The system shall provide a video player with play, pause, seek, speed and fullscreen controls. | S | M |
| FR-LRN-02 | The system shall record lesson completion for each student. | S, Sys | M |
| FR-LRN-03 | The system shall calculate and display the completion percentage of each enrolled course. | Sys | M |
| FR-LRN-04 | The system shall provide a "My Courses" page listing the student's enrolled courses with progress. | S | M |
| FR-LRN-05 | The system shall resume a lesson from the last watched position. | S | C |
| FR-LRN-06 | The system shall allow students to take notes and bookmark lessons. | S | C |

### 8. Quizzes (QZ)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-QZ-01 | The system shall allow instructors to create quizzes at the end of a section or course, with a minimum passing score. | I | M |
| FR-QZ-02 | The system shall allow enrolled students to take a quiz and shall store the attempt and score. | S | M |
| FR-QZ-03 | The system shall support multiple-choice and true/false questions; fill-in-the-blank questions are added as a Should item. | I | M |
| FR-QZ-04 | The system shall display the result immediately, with explanations of the correct answers. | S | S |
| FR-QZ-05 | The system shall allow a student to retake a failed quiz. | S | S |

### 9. Reviews and Ratings (REV)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-REV-01 | The system shall allow an enrolled student to give a 1-5 star rating and a written review. | S | S |
| FR-REV-02 | The system shall display the average rating and the number of reviews of each course. | Sys | S |
| FR-REV-03 | The system shall allow users to mark a review as helpful. | S | C |

### 10. Certificates (CRT)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-CRT-01 | The system shall generate a PDF certificate with the student name, course title and completion date when the student completes the course and passes the required quizzes. | Sys | M |
| FR-CRT-02 | The system shall assign a unique verification code to every certificate. | Sys | M |
| FR-CRT-03 | The system shall provide a public page where anyone can verify a certificate using its code. | V | S |
| FR-CRT-04 | The system shall allow sharing a certificate on LinkedIn. | S | C |

### 11. Administration (ADM)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-ADM-01 | The system shall allow administrators to view, search, block/unblock users and change user roles. | A | M |
| FR-ADM-02 | The system shall provide a course approval workflow: administrators review submitted courses and approve or reject them with a comment. | A | M |
| FR-ADM-03 | The system shall allow administrators to manage categories and tags. | A | M |
| FR-ADM-04 | The system shall allow administrators to manage platform settings. | A | C |

### 12. Analytics (ANL)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-ANL-01 | The system shall show administrators charts of best-selling courses, course completion rates, instructor earnings and revenue over time (Chart.js). | A | S |
| FR-ANL-02 | The system shall show student engagement metrics. | A | C |

### 13. Notifications (NTF)

| ID | Requirement | Actor | Priority |
|---|---|---|---|
| FR-NTF-01 | The system shall notify users inside the application about key events (enrollment, course approved or rejected, certificate issued) using the Observer pattern. | Sys | C |

### 14. Summary

| Priority | Count |
|---|---|
| Must | 30 |
| Should | 13 |
| Could | 12 |
| **Total** | **55** |

---

## Non-functional Requirements

**Document owner:** Omar Mohamed | **Reviewer:** Abdelrhman Raoof

### 1. Conventions

- **ID format**: `NFR-<CATEGORY>-<NN>`
- **Priority**: M (Must), S (Should), C (Could)
- Each requirement has a **verification method**, so it can be tested or inspected.

### 2. Performance (PERF)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-PERF-01 | Main pages (catalogue, course details, My Courses) shall load within 3 seconds for 95% of requests under normal use. | Load test and browser tools | M |
| NFR-PERF-02 | A lesson video shall start playing within 5 seconds on a normal broadband connection. | Manual timing | M |
| NFR-PERF-03 | The system shall support at least 100 concurrent users in a test environment without errors. | Load test | S |
| NFR-PERF-04 | Lists shall use pagination and database queries shall be indexed on frequently searched fields. | Code and schema review | M |

### 3. Security (SEC)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-SEC-01 | Passwords shall be stored hashed and salted (ASP.NET Core Identity); plain-text passwords shall never be stored or logged. | Code review, database inspection | M |
| NFR-SEC-02 | All pages shall be served over HTTPS in the deployed environment. | Deployment check | M |
| NFR-SEC-03 | Access to pages and actions shall be controlled by roles; users shall not reach another role's functions by changing the URL. | Authorisation test cases | M |
| NFR-SEC-04 | The application shall protect against common attacks: SQL injection (parameterised queries through EF Core), cross-site scripting (output encoding), and cross-site request forgery (anti-forgery tokens). | Security checklist | M |
| NFR-SEC-05 | Videos shall be accessible only through time-limited signed URLs generated for authorised users. | Test cases | M |
| NFR-SEC-06 | Card data shall be handled only by Stripe; the system shall store no card numbers. | Design and code review | M |
| NFR-SEC-07 | Secrets (connection strings, API keys) shall be kept out of the source repository, using user secrets or environment configuration. | Repository scan | M |
| NFR-SEC-08 | User input shall be validated on the client and on the server. | Test cases | M |

### 4. Usability (USA)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-USA-01 | The interface shall be responsive and work on screens from 360 px wide (mobile) to desktop. | Manual test on several devices | M |
| NFR-USA-02 | A student shall reach a lesson from the home page in no more than three clicks once logged in. | Walkthrough | S |
| NFR-USA-03 | The interface shall be consistent (layout, colours, typography, messages) following the UI/UX guidelines. | Design review | M |
| NFR-USA-04 | The system shall show clear, friendly error and success messages. | Test cases | M |
| NFR-USA-05 | The interface shall follow basic accessibility practice: sufficient colour contrast, text alternatives for images, keyboard navigation, labelled form fields (aiming for WCAG 2.1 level AA). | Accessibility checklist | S |
| NFR-USA-06 | The system shall achieve a System Usability Scale score of at least 68 in the pilot. | Pilot questionnaire | S |

### 5. Reliability and Availability (REL)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-REL-01 | The deployed system shall achieve at least 99% availability during the evaluation period. | Monitoring | S |
| NFR-REL-02 | Operations that change several records (for example order and enrollment) shall be atomic through the Unit of Work. | Test cases | M |
| NFR-REL-03 | The application shall handle exceptions gracefully, show friendly error pages, and log errors. | Test cases | M |
| NFR-REL-04 | Database creation, migration and seed scripts shall be kept in the repository so the database can be rebuilt. | Repository check | M |

### 6. Maintainability and Code Quality (MNT)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-MNT-01 | The solution shall follow N-Tier architecture with separate Web, Services and Data projects. | Architecture review | M |
| NFR-MNT-02 | Data access shall use the Repository and Unit of Work patterns; services shall be injected through dependency injection. | Code review | M |
| NFR-MNT-03 | Code shall follow C# naming conventions, be commented where needed and organised into reusable classes and methods. | Code review checklist | M |
| NFR-MNT-04 | The business logic layer shall have automated unit tests for key rules (pricing, progress, quiz scoring). | Test run | S |
| NFR-MNT-05 | Every change shall enter `main` through a reviewed pull request. | GitHub history | M |

### 7. Scalability and Portability (SCL)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-SCL-01 | The web tier shall not keep user state in server memory beyond what is necessary, so that it can run on more than one instance. | Design review | C |
| NFR-SCL-02 | Frequently read data (such as catalogue pages) shall support caching. | Design review | C |
| NFR-SCL-03 | Video delivery shall be able to use a CDN. | Design review | C |

### 8. Compatibility (CMP)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-CMP-01 | The system shall work in the current versions of Chrome, Edge, Firefox and Safari. | Cross-browser test | M |
| NFR-CMP-02 | The system shall run on the supported .NET version with SQL Server and be deployable to Microsoft Azure. | Deployment | M |

### 9. Deployment and Documentation (DEP)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-DEP-01 | The repository README shall contain installation steps, system requirements, configuration instructions and an execution guide. | Checklist | M |
| NFR-DEP-02 | The system shall be deployed to a public URL before the implementation deadline. | Deployment link | M |
| NFR-DEP-03 | Configuration (connection strings, storage and payment settings) shall be separated from code. | Code review | M |

### 10. Data and Privacy (DAT)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-DAT-01 | The system shall collect only the personal data required for its functions. | Design review | M |
| NFR-DAT-02 | The database shall enforce integrity through primary keys, foreign keys and validation rules, and shall be normalised to at least third normal form. | Schema review | M |

### 11. Localisation (LOC)

| ID | Requirement | Verification | Priority |
|---|---|---|---|
| NFR-LOC-01 | The system shall be available in English. | Manual test | M |
| NFR-LOC-02 | The design shall allow adding Arabic with right-to-left layout in a future version. | Design review | C |

### 12. Constraints

| Constraint | Description |
|---|---|
| Technology | ASP.NET Core MVC, Entity Framework Core, SQL Server, Azure services as defined in the proposal |
| Time | DEPI deadlines: 6 Nov (design), 30 Nov (implementation), 4 Dec (final reports) |
| Team | Three members; scope managed with MoSCoW |
| Cost | Zero-cost target using free tiers and Stripe test mode |
