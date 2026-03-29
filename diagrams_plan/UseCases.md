# Use Case Diagrams & Specifications Guide

This artifact outlines the **Use Case Diagrams** architecture for Visual Paradigm and provides the **14 fully detailed Use Cases** representing the adaptive decision-support platform.

## 1. Use Case Diagram Drawing Instructions
* **Actors:** Student, Advisor, Instructor, Admin.
* **Use Cases (Ovals):** Draw all 14 Use Cases mapped below.
* **Relationships (Dashed Arrows):** Add `<<include>>` arrows pointing directly from *Generate Academic Pathway Plan* to *Validate Prerequisites*, *Check Timetable Conflicts*, and *Assess Academic Risk*.

---

## 2. Complete Use Case Catalog

### 👨‍🎓 Hamdo Alhasan (Student Workflows)

| Use Case Identifier | UC-1 |
| :--- | :--- |
| **Use Case Name** | Register for Courses |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student logs in and navigates to the Registration Module.<br>2. Student selects courses to add to their cart.<br>3. System validates course prerequisites and remaining seat capacities.<br>4. IF validation fails:<br>&nbsp;&nbsp;&nbsp;* System displays an error message explaining the specific failure.<br>&nbsp;&nbsp;&nbsp;* Student modifies their course selection.<br>5. IF validation succeeds:<br>&nbsp;&nbsp;&nbsp;* Student clicks submit.<br>6. System saves the registration request with a 'Pending Advisor Approval' status. |
| **Entry Condition** | Registration period is open. |
| **Exit Condition** | Registration request is created and pending advisor review. |
| **Related NFR** | NR-2, NR-3 |

| Use Case Identifier | UC-2 |
| :--- | :--- |
| **Use Case Name** | Generate Academic Pathway Plan |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses the Pathway Planning module.<br>2. System securely loads the student's transcript alongside generic Departmental policies.<br>3. System builds candidate multi-semester schedules aiming for fastest graduation and balanced workload.<br>4. System validates prerequisite logic across the multi-semester timeframe.<br>5. IF policy conflicts occur:<br>&nbsp;&nbsp;&nbsp;* System assesses the risk and marks the pathway option with a warning.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* System ranks the valid plans based on workload safety.<br>7. System generates explainable text clarifying why each path is recommended.<br>8. Student selects their preferred long-term pathway. |
| **Entry Condition** | Planning configuration is actively open. |
| **Exit Condition** | Ranked Pathway Plan options are saved to the dashboard. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-3 |
| :--- | :--- |
| **Use Case Name** | Simulate What-If Academic Scenario |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student inputs a hypothetical override (e.g., delaying a key prerequisite).<br>2. System loads the AcademicPathwayEngine and simulates the future semesters based on the override.<br>3. System analyzes the new path for graduation delays and bottleneck risks.<br>4. IF the scenario violates core generic University policies:<br>&nbsp;&nbsp;&nbsp;* System flags the scenario as highly risky.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System computes the output timeline.<br>6. System displays the simulated strategy comparison and saves the Planning Scenario. |
| **Entry Condition** | Student has an existing academic profile. |
| **Exit Condition** | What-if simulation results are calculated and displayed. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-4 |
| :--- | :--- |
| **Use Case Name** | Request Graduation Audit |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses the 'Graduation' tab.<br>2. Student clicks 'Run Degree Audit'.<br>3. System retrieves the student’s passed courses and the generic Graduation Policy.<br>4. System maps the passed credits against the programmatic rules.<br>5. IF the student lacks required constraints:<br>&nbsp;&nbsp;&nbsp;* System highlights missing obligations in red.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* System flags profile as 'Eligible for Graduation' and generates a printable certificate. |
| **Entry Condition** | Student has Senior status. |
| **Exit Condition** | Degree audit report is generated. |
| **Related NFR** | NR-3 |

---
### 👨‍🏫 Omar Mohamed (Advisor Workflows)

| Use Case Identifier | UC-5 |
| :--- | :--- |
| **Use Case Name** | Approve Course Selection |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor navigates to the pending registration requests dashboard.<br>2. Advisor selects a specific student's request.<br>3. System retrieves and displays the student's current transcript and the requested schedule.<br>4. Advisor reviews the schedule to ensure the workload is appropriate.<br>5. IF the advisor identifies an issue (e.g., excessive credit overload):<br>&nbsp;&nbsp;&nbsp;* Advisor rejects the request and inputs a required reason.<br>&nbsp;&nbsp;&nbsp;* System updates the request status to 'Rejected' and notifies the student.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* Advisor clicks 'Approve'.<br>&nbsp;&nbsp;&nbsp;* System updates the request status to 'Approved' and finalizes the enrollment in the database. |
| **Entry Condition** | Advisor has pending requests queued. |
| **Exit Condition** | Registration request is approved or rejected. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-6 |
| :--- | :--- |
| **Use Case Name** | Review Student Pathway Plan |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor navigates to the Student Search module and accesses a specific ID.<br>2. System displays the student's active Pathway Plan and their recent what-if simulations.<br>3. Advisor identifies any flagged risk assessments.<br>4. Advisor inputs academic advisory notes directly onto the pathway.<br>5. System saves the active corrections permanently. |
| **Entry Condition** | Advisor is logged in. |
| **Exit Condition** | Advisory notes are saved to the student profile. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-7 |
| :--- | :--- |
| **Use Case Name** | Send Academic Warning |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor runs the risk assessment filter across their assigned student array.<br>2. System retrieves a list of students failing Academic Policy thresholds.<br>3. Advisor selects a student and drafts an official intervention message.<br>4. System permanently attaches the warning flag to the student's database record.<br>5. System sends an automated email notification to the student. |
| **Entry Condition** | Student triggers a risk threshold. |
| **Exit Condition** | Academic warning is saved and emailed. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-8 |
| :--- | :--- |
| **Use Case Name** | View Transcript |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor queries the Grade Database for all completed courses belonging to a student.<br>2. IF no data records are found:<br>&nbsp;&nbsp;&nbsp;* System displays "No transcript data available".<br>3. ELSE:<br>&nbsp;&nbsp;&nbsp;* System calculates the Cumulative Grade Point Average (CGPA).<br>&nbsp;&nbsp;&nbsp;* System formats and renders the official digital transcript on screen. |
| **Entry Condition** | Advisor is actively authorized for the queried department. |
| **Exit Condition** | Transcript is displayed on screen. |
| **Related NFR** | NR-1 |

---
### 👨‍💻 Hesham Alfadhl (Instructor Workflows)

| Use Case Identifier | UC-9 |
| :--- | :--- |
| **Use Case Name** | Enter Course Grades |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the Grade Entry module.<br>2. Instructor inputs numerical scores for course assessments (e.g., midterms, finals, projects, quizzes).<br>3. System validates that inputs fall between 0 and 100.<br>4. IF any score is invalid:<br>&nbsp;&nbsp;&nbsp;* System highlights the field and prevents submission.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System converts scores to letter grades.<br>&nbsp;&nbsp;&nbsp;* Instructor clicks 'Publish Grades'.<br>&nbsp;&nbsp;&nbsp;* System updates the associated students' transcripts. |
| **Entry Condition** | Grading period is actively open. |
| **Exit Condition** | Final grades are saved and transcripts are updated. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-10 |
| :--- | :--- |
| **Use Case Name** | Record Attendance |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the precise attendance roster.<br>2. Instructor manually inputs present/absent markers for the date.<br>3. System updates the attendance database.<br>4. System automatically recalculates the absence percentage based on University Policy.<br>5. IF the student violates the active attendance rule:<br>&nbsp;&nbsp;&nbsp;* System flags them with an 'Attendance Failure (NA)'.<br>&nbsp;&nbsp;&nbsp;* System issues a warning trigger. |
| **Entry Condition** | Semester week is active. |
| **Exit Condition** | Attendance record is saved and warnings are issued if needed. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-11 |
| :--- | :--- |
| **Use Case Name** | Update Course Syllabus |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the Course Settings module.<br>2. Instructor uploads a new PDF syllabus document.<br>3. System validates the uploaded file type and file size.<br>4. IF the validation fails:<br>&nbsp;&nbsp;&nbsp;* System rejects the upload and displays an error message.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System saves the document to the repository.<br>&nbsp;&nbsp;&nbsp;* System publishes the syllabus to the student dashboard.<br>&nbsp;&nbsp;&nbsp;* System emails an update notification to enrolled students. |
| **Entry Condition** | Instructor is assigned to the active course. |
| **Exit Condition** | Syllabus is published and students are notified. |
| **Related NFR** | NR-4 |

---
### 🛠️ Mohamed Hafedh (Admin Workflows)

| Use Case Identifier | UC-12 |
| :--- | :--- |
| **Use Case Name** | Create New Course Section |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to the Curriculum Manager module.<br>2. Admin inputs the section configuration (instructor, capacity, time block).<br>3. System checks the database for instructor availability and specific classroom physical capacity conflicts.<br>4. IF a scheduling conflict exists:<br>&nbsp;&nbsp;&nbsp;* System blocks the creation and maps a specific conflict error.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System saves the new course section.<br>&nbsp;&nbsp;&nbsp;* System makes the section visible to students for the upcoming registration period. |
| **Entry Condition** | Curriculum planning period is open. |
| **Exit Condition** | New course section is saved and visible. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-13 |
| :--- | :--- |
| **Use Case Name** | Manage System Roles |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin searches and accesses a target user profile.<br>2. System verifies the Admin's master security clearance.<br>3. IF clearance is insufficient:<br>&nbsp;&nbsp;&nbsp;* System rejects the action and logs an audit alert.<br>4. ELSE:<br>&nbsp;&nbsp;&nbsp;* Admin assigns new functional roles (e.g., granting "Advisor" privileges).<br>&nbsp;&nbsp;&nbsp;* System saves the new access matrix securely updating application bounds globally. |
| **Entry Condition** | Admin is logged in. |
| **Exit Condition** | User roles are updated. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-14 |
| :--- | :--- |
| **Use Case Name** | Configure Global Academic Policies |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin accesses the master Policy Configuration engine.<br>2. Admin defines scalable generic constraints matching the University or Department (e.g., max credits per semester, warning thresholds).<br>3. System evaluates rule viability to prevent contradiction.<br>4. IF logic contradiction is detected:<br>&nbsp;&nbsp;&nbsp;* System blocks save action and displays error trace.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System saves the `AcademicPolicy` mapping directly into the master platform bounds enforcing rules universally across all simulation engines. |
| **Entry Condition** | Global settings mode is active. |
| **Exit Condition** | Policy rules are updated and securely enforced platform-wide. |
| **Related NFR** | NR-2 |
