# Use Case Diagrams & Specifications Guide

This artifact outlines the **Use Case Diagrams** architecture for Visual Paradigm and provides the **13 fully detailed Use Cases** you must paste directly into Section 4 of your `ProjectAnalysisDocument`.

## 1. Use Case Diagram Drawing Instructions
*You can draw one massive diagram covering everything, or break it up into 4 smaller diagrams based on your Team Members.*

* **Actors (Stick Figures):** Student, Advisor, Instructor, Admin. Add a secondary system actor rectangle on the right: `Recommendation Database`.
* **Use Cases (Ovals):** Draw all 13 Use Cases mapped below.
* **Associations (Solid Lines):**
  * **Student:** Register for Courses, Generate Smart Course Recommendations, View Transcript, Request Graduation Audit.
  * **Advisor:** Approve Course Selection, Review Student Study Plan, Send Academic Warning.
  * **Instructor:** Enter Course Grades, Record Attendance, Update Course Syllabus.
  * **Admin:** Create New Course Section, Manage System Roles, Configure Academic Calendar.
* **Relationships (Dashed Arrows):**
  * Add an `<<include>>` arrow pointing from *Register for Courses (UC-1)* to a sub-oval named *Validate Prerequisites*.
  * Add an `<<extend>>` arrow from *Generate Smart Course Recommendations (UC-2)* pointing to *Check Timetable Conflicts*.

---

## 2. Complete Use Case Catalog

### 👨‍🎓 Hamdo Alhasan (Student Workflows)

| Use Case Identifier | UC-1 |
| :--- | :--- |
| **Use Case Name** | Register for Courses |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student logs in.<br>2. Navigates to Registration Module.<br>3. Adds desired courses to cart.<br>4. System validates prerequisites and capacity.<br>5. Student submits request.<br>6. Status updates to 'Pending Advisor Approval'. |
| **Entry Condition** | System clock matches active registration period. |
| **Exit Condition** | Request is queued for Advisor review. |
| **Related NFR** | NR-2, NR-3 |

| Use Case Identifier | UC-2 |
| :--- | :--- |
| **Use Case Name** | Generate Smart Course Recommendations |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses Course Selection.<br>2. System analyzes academic history, credits, and prerequisites.<br>3. System prioritizes unresolved compulsory courses.<br>4. System recommends electives matching past specialization (e.g., AI -> NLP).<br>5. Generates conflict-free timetable options.<br>6. Student selects a recommended schedule directly into cart. |
| **Entry Condition** | Authenticated during pre-registration period. |
| **Exit Condition** | Registration cart populated with a conflict-free, graduation-oriented schedule. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-3 |
| :--- | :--- |
| **Use Case Name** | View Transcript |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student navigates to 'My Profile'.<br>2. Clicks 'View Official Transcript'.<br>3. System queries GradeDatabase.<br>4. Computes CGPA in real-time.<br>5. Displays formatted transcript. |
| **Entry Condition** | User logged in. |
| **Exit Condition** | Transcript is cleanly displayed. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-4 |
| :--- | :--- |
| **Use Case Name** | Request Graduation Audit |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses 'Graduation' tab.<br>2. Runs 'Degree Audit'.<br>3. System compares passed courses vs Curriculum rules.<br>4. Outputs a progress bar of remaining mandatory credits. |
| **Entry Condition** | Senior student status. |
| **Exit Condition** | PDF audit report generated. |
| **Related NFR** | NR-3 |

### 👨‍🏫 Omar Mohamed (Advisor Workflows)

| Use Case Identifier | UC-5 |
| :--- | :--- |
| **Use Case Name** | Approve Course Selection |
| **Participating Actors** | Academic Advisor, System |
| **Flow of Events** | 1. Advisor views pending student registration requests.<br>2. Reviews student's study plan and grades.<br>3. Clicks "Approve".<br>4. System finalizes student enrollment. |
| **Entry Condition** | Advisor has pending requests in dashboard. |
| **Exit Condition** | Registration finalized. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-6 |
| :--- | :--- |
| **Use Case Name** | Review Student Study Plan |
| **Participating Actors** | Academic Advisor, System |
| **Flow of Events** | 1. Advisor searches for specific Student ID.<br>2. System retrieves Transcript and active courses.<br>3. Advisor adds academic notes. |
| **Entry Condition** | Authenticated as Advisor. |
| **Exit Condition** | Student plan successfully reviewed/commented. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-7 |
| :--- | :--- |
| **Use Case Name** | Send Academic Warning |
| **Participating Actors** | Academic Advisor, System |
| **Flow of Events** | 1. Advisor flags a student with CGPA < 2.0.<br>2. Navigates to Messaging module.<br>3. Drafts official warning.<br>4. System sends email/UI notification to student. |
| **Entry Condition** | Student identified as at-risk. |
| **Exit Condition** | Official warning documented in system. |
| **Related NFR** | NR-1 |

### 👨‍💻 Hesham Alfadhl (Instructor Workflows)

| Use Case Identifier | UC-8 |
| :--- | :--- |
| **Use Case Name** | Enter Course Grades |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor selects active course.<br>2. Navigates to "Grade Entry".<br>3. Inputs numerical scores.<br>4. System computes letter grades (AA, BA).<br>5. Instructor clicks "Publish". |
| **Entry Condition** | Active grade submission deadline. |
| **Exit Condition** | Grades visible on student portals. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-9 |
| :--- | :--- |
| **Use Case Name** | Record Attendance |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor opens Week class roster.<br>2. Marks Present/Absent.<br>3. System calculates absence percentage.<br>4. Warns standard if absence > 30%. |
| **Entry Condition** | Ongoing class week. |
| **Exit Condition** | Attendance metrics updated. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-10 |
| :--- | :--- |
| **Use Case Name** | Update Course Syllabus |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to Course Settings.<br>2. Edits weekly topic layout.<br>3. Uploads new PDF syllabus.<br>4. System notifies enrolled students. |
| **Entry Condition** | Assigned as primary instructor. |
| **Exit Condition** | Syllabus explicitly updated. |
| **Related NFR** | NR-4 |

### 🛠️ Mohamed Hafedh (Admin/Department Workflows)

| Use Case Identifier | UC-11 |
| :--- | :--- |
| **Use Case Name** | Create New Course Section |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to Curriculum Manager.<br>2. Creates new instance (e.g., CENG3004 Section 1).<br>3. Sets capacity to 60, assigns Instructor.<br>4. Assigns classroom.<br>5. System saves section. |
| **Entry Condition** | Pre-semester planning phase. |
| **Exit Condition** | Section visible to Students for registration. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-12 |
| :--- | :--- |
| **Use Case Name** | Manage System Roles |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin accesses User Database.<br>2. Selects new faculty member.<br>3. Assigns "Instructor" and "Advisor" roles.<br>4. Saves profile. |
| **Entry Condition** | Top-level Admin clearance. |
| **Exit Condition** | Access rights instantly updated. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-13 |
| :--- | :--- |
| **Use Case Name** | Configure Academic Calendar |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to Global Settings.<br>2. Sets specific date ranges for 'Registration Week' and 'Finals Week'.<br>3. System applies constraints across all modules. |
| **Entry Condition** | Start of academic year. |
| **Exit Condition** | System deadlines actively enforced. |
| **Related NFR** | NR-2 |
