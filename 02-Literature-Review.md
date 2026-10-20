# Literature Review

| | |
|---|---|
| **Project** | DotTeach - Online Learning Platform |
| **Programme** | DEPI - Digital Egypt Pioneers Initiative |
| **Track** | Full Stack .NET |
| **Group Code** | SWD5_S4 |
| **Team** | Abdelrhman Osama (Team Lead), Abdelrhman Raoof, Omar Mohamed |
| **Version** | 1.0 (initial submission) |
| **Date** | 20 October 2026 |

---

## Literature Review

**Document owner:** Omar Mohamed | **Reviewer:** Abdelrhman Raoof

### 1. Purpose and Method

This review studies existing online learning platforms to understand what the market already does well, where it leaves gaps, and which ideas DotTeach should adopt. The platforms were selected because they represent four different models: an instructor marketplace, a university-partnership platform, an open-source learning management system, and a free non-profit platform.

The review is based on the platforms' publicly available information and public documentation. Features and pricing change over time, so the comparison reflects the general nature of each platform rather than a detailed feature audit.

### 2. Review of Existing Platforms

#### 2.1 Udemy - instructor marketplace
Open marketplace where independent instructors publish video courses and learners buy them individually. Strengths: very wide catalogue, simple course purchase, instructor-led pricing, course reviews and ratings, certificates of completion. Limitations: quality varies because instructors publish with little control, and the platform is a general marketplace rather than something an organisation can adapt or own.

#### 2.2 Coursera - partnership platform
Offers courses and programmes created with universities and companies, with graded assignments, quizzes, and recognised certificates or degrees. Strengths: structured learning paths, assessments, strong credibility. Limitations: content is produced by partners, so individual instructors cannot freely publish, and many features sit behind subscriptions or fees.

#### 2.3 Moodle - open-source learning management system
Open-source system that organisations install and manage themselves. Strengths: highly customisable, strong quiz and assessment tools, a large plugin ecosystem, full control of data. Limitations: it needs hosting and administration effort, the interface can feel heavy for new users, and features such as payments or certificates usually depend on plugins.

#### 2.4 Khan Academy - free non-profit learning
Free learning platform with video lessons, practice exercises and mastery-based progress tracking. Strengths: clear progress and practice model, free access, strong learner experience. Limitations: content is produced by the organisation itself, so there is no instructor marketplace or paid-course model.

### 3. Comparison Matrix

| Capability | Udemy | Coursera | Moodle | Khan Academy | **DotTeach (planned)** |
|---|---|---|---|---|---|
| Instructors publish their own courses | Yes | Through partners | Yes (self-hosted) | No | **Yes, with admin approval** |
| Video lessons | Yes | Yes | Yes (embedded/plugins) | Yes | **Yes, secure streaming** |
| Quizzes and assessment | Yes | Yes, including graded work | Yes, very strong | Yes, practice exercises | **Yes, with passing score** |
| Progress tracking | Yes | Yes | Yes | Yes, mastery-based | **Yes, per lesson and course** |
| Certificates | Yes | Yes | Usually via plugin | Limited | **Yes, with public verification** |
| Paid courses | Yes | Yes, subscription or fee | Via plugin | No (free) | **Yes (Stripe, test mode)** |
| Reviews and ratings | Yes | Yes | Optional | No | **Yes (Should)** |
| Admin quality control | Platform policies | Partner selection | Self-managed | Internal | **Approval workflow** |
| Source available to learn from and extend | No | No | Yes | No | **Yes, academic project** |

### 4. Gaps and Opportunities for DotTeach

1. **Quality control with simplicity.** Marketplaces are open but uneven in quality, while heavy systems are hard to run. An approval workflow inside a lightweight platform is a practical middle ground.
2. **Complete journey in one system.** Many learners move between catalogue, payment, video, assessment and certificate. DotTeach provides the full chain end to end.
3. **Verifiable achievement.** A unique verification code and public verification page let employers check a certificate without an account.
4. **Protected content.** Time-limited signed video links reduce uncontrolled sharing of paid videos.
5. **Maintainable architecture.** The N-Tier structure with Repository and Unit of Work patterns makes the system easy to extend, which is valuable for a platform that must grow.
6. **Regional fit.** Arabic-language support (a "Could" requirement) is an opportunity for the local market.

### 5. Lessons Applied to DotTeach

| Lesson from existing platforms | Decision in DotTeach |
|---|---|
| Learners value visible progress (Khan Academy, Coursera) | Progress bar and "continue learning" in My Courses |
| Social proof drives course choice (Udemy) | Ratings and written reviews |
| Assessments make learning credible (Coursera, Moodle) | Quizzes with minimum passing score before a certificate |
| Flexibility needs structure (Moodle) | Clear roles and a simple, consistent interface |
| Pricing flexibility matters (Udemy) | Strategy pattern for coupons and discounts |

### 6. Feedback and Evaluation (lecturer)

*To be completed by the lecturer after reviewing the project.*

| Area | Lecturer's assessment | Date |
|---|---|---|
| Project idea and scope | | |
| Planning and management | | |
| Requirements | | |
| Overall comments | | |

### 7. Suggested Improvements

#### 7.1 Team's own suggestions for future versions
- Arabic language and right-to-left layout
- Native mobile application and offline lesson viewing
- Discussion forums or Q&A per course and learner messaging
- Gamification: badges, streaks and leaderboards
- Course recommendations based on learner interests and behaviour
- Live sessions and scheduled webinars

#### 7.2 Improvements suggested by the lecturer
*To be completed after the lecturer's feedback.*

| # | Suggested improvement | Decision | Status |
|---|---|---|---|
| 1 | | | |

### 8. Final Grading Criteria

*The mark breakdown is defined by the programme and the lecturer and will be entered here once confirmed.*

| Criterion | Marks | Notes |
|---|---|---|
| Documentation | To be confirmed | |
| Implementation | To be confirmed | |
| Testing | To be confirmed | |
| Presentation | To be confirmed | |
| **Total** | | |

Individual contribution is assessed through the weekly evaluation and the final presentation, where each member explains the work they completed.

### 9. References

- Udemy - https://www.udemy.com
- Coursera - https://www.coursera.org
- Moodle - https://moodle.org
- Khan Academy - https://www.khanacademy.org
- DEPI Project Documentation Guidelines and Full Stack .NET project booklet (programme material)
