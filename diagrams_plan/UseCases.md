# Use Case Diagrams & Specifications Guide

This artifact outlines the **Use Case Diagrams** architecture for Visual Paradigm and provides the **13 fully detailed Use Cases** written in plain, human-readable English steps. It clearly maps out alternative flows and system validations.

## 1. Use Case Diagram Drawing Instructions
*You can draw one massive diagram covering everything, or break it up into 4 smaller diagrams based on your Team Members.*

* **Actors (Stick Figures):** Student, Advisor, Instructor, Admin. *(Do NOT include the Database as an actor, as it is an internal system).*
* **Use Cases (Ovals):** Draw all 13 Use Cases mapped below.
* **Associations (Solid Lines):** Match actors cleanly to their assigned nodes.
* **Relationships (Dashed Arrows):** Add `<<include>>` arrows pointing directly from *Generate Smart Course Recommendations* to *Validate Prerequisites* and *Check Timetable Conflicts*.

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
| **Use Case Name** | Generate Smart Course Recommendations |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses the Course Selection page and clicks "Generate Recommendations".<br>2. System retrieves the student’s academic transcript and the active curriculum rules.<br>3. System identifies any missing compulsory courses.<br>4. System selects candidate electives based on the student's historical specialization trend.<br>5. System filters the candidate courses by validating prerequisites and checking for timetable clashes.<br>6. IF no valid conflict-free schedule can be generated:<br>&nbsp;&nbsp;&nbsp;* System displays a warning message.<br>7. ELSE:<br>&nbsp;&nbsp;&nbsp;* System displays multiple conflict-free schedule options.<br>8. Student selects their preferred schedule.<br>9. System adds the selected courses directly into the registration cart. |
| **Entry Condition** | Student is navigating course selection. |
| **Exit Condition** | Selected courses are added to the registration cart. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-3 |
| :--- | :--- |
| **Use Case Name** | View Transcript |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student navigates to the 'My Profile' dashboard.<br>2. Student clicks 'View Official Transcript'.<br>3. System queries the Grade Database for all completed courses belonging to the student.<br>4. IF no course records are found:<br>&nbsp;&nbsp;&nbsp;* System displays "No transcript data available".<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System calculates the current Cumulative Grade Point Average (CGPA).<br>&nbsp;&nbsp;&nbsp;* System formats and displays the official digital transcript on screen. |
| **Entry Condition** | Student is logged in. |
| **Exit Condition** | Transcript is displayed on screen. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-4 |
| :--- | :--- |
| **Use Case Name** | Request Graduation Audit |
| **Participating Actors** | Student, System |
| **Flow of Events** | 1. Student accesses the 'Graduation' tab.<br>2. Student clicks 'Run Degree Audit'.<br>3. System retrieves the student’s passed courses and the official degree curriculum requirements.<br>4. System compares the passed courses against the curriculum rules.<br>5. IF the student is missing required credits:<br>&nbsp;&nbsp;&nbsp;* System highlights the missing courses in red and generates a progress report.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* System marks the profile as 'Eligible for Graduation' and generates a printable certificate. |
| **Entry Condition** | Student has 'Senior' status. |
| **Exit Condition** | Degree audit report is generated. |
| **Related NFR** | NR-3 |

---
### 👨‍🏫 Omar Mohamed (Advisor Workflows)

| Use Case Identifier | UC-5 |
| :--- | :--- |
| **Use Case Name** | Approve Course Selection |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor navigates to the pending registration requests dashboard.<br>2. Advisor selects a specific student's request.<br>3. System retrieves and displays the student's current transcript and the requested schedule.<br>4. Advisor reviews the schedule to ensure the workload is appropriate.<br>5. IF the advisor identifies an issue (e.g., excessive credit overload):<br>&nbsp;&nbsp;&nbsp;* Advisor rejects the request and inputs a required reason.<br>&nbsp;&nbsp;&nbsp;* System updates the request status to 'Rejected' and notifies the student.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* Advisor clicks 'Approve'.<br>&nbsp;&nbsp;&nbsp;* System updates the request status to 'Approved' and finalizes the enrollment in the database. |
| **Entry Condition** | Advisor has pending requests queued in their dashboard. |
| **Exit Condition** | Registration request is approved or rejected. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-6 |
| :--- | :--- |
| **Use Case Name** | Review Student Study Plan |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor navigates to the Student Search module.<br>2. Advisor enters a specific Student ID.<br>3. System verifies that the Advisor has departmental permission to view this student.<br>4. IF permission is denied:<br>&nbsp;&nbsp;&nbsp;* System displays an "Access Denied" error message.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System displays the student's active study plan and historical grades.<br>&nbsp;&nbsp;&nbsp;* Advisor inputs academic advisory notes into the text field.<br>&nbsp;&nbsp;&nbsp;* System saves the advisory notes permanently to the student's profile. |
| **Entry Condition** | Advisor is logged in. |
| **Exit Condition** | Advisory notes are saved to the student profile. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-7 |
| :--- | :--- |
| **Use Case Name** | Send Academic Warning |
| **Participating Actors** | Advisor, System |
| **Flow of Events** | 1. Advisor navigates to the Academic Monitoring module and runs the CGPA risk filter.<br>2. System retrieves a list of students with a CGPA below 2.0.<br>3. Advisor selects a specific student from the list.<br>4. Advisor drafts an official warning message.<br>5. System saves the warning flag to the student's database record.<br>6. System dispatches an automated email notification to the student. |
| **Entry Condition** | Student CGPA is lower than 2.0. |
| **Exit Condition** | Academic warning is saved and emailed to the student. |
| **Related NFR** | NR-1 |

---
### 👨‍💻 Hesham Alfadhl (Instructor Workflows)

| Use Case Identifier | UC-8 |
| :--- | :--- |
| **Use Case Name** | Enter Course Grades |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the Grade Entry module and selects an active course section.<br>2. Instructor inputs numerical scores for midterms and finals into the grade roster.<br>3. System validates that all numerical inputs precisely fall between 0 and 100.<br>4. IF any score is invalid:<br>&nbsp;&nbsp;&nbsp;* System highlights the invalid field in red and prevents submission.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System calculates the final letter grades corresponding to the scores.<br>&nbsp;&nbsp;&nbsp;* Instructor clicks 'Publish Grades'.<br>&nbsp;&nbsp;&nbsp;* System saves the final grades and updates the students' central transcripts. |
| **Entry Condition** | Grading period is actively open. |
| **Exit Condition** | Final grades are saved and transcripts are updated. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-9 |
| :--- | :--- |
| **Use Case Name** | Record Attendance |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the Attendance module and opens the weekly class roster.<br>2. Instructor manually marks students as present or absent for the date.<br>3. Instructor clicks 'Save'.<br>4. System updates the attendance database records for the course section.<br>5. System automatically recalculates the total absence percentage for each student.<br>6. IF a student's absence percentage exceeds 30%:<br>&nbsp;&nbsp;&nbsp;* System automatically flags the student with an 'Attendance Failure (NA)' status.<br>&nbsp;&nbsp;&nbsp;* System displays a warning to the instructor. |
| **Entry Condition** | Semester week is active. |
| **Exit Condition** | Attendance record is saved and warnings are issued if needed. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-10 |
| :--- | :--- |
| **Use Case Name** | Update Course Syllabus |
| **Participating Actors** | Instructor, System |
| **Flow of Events** | 1. Instructor navigates to the Course Settings module.<br>2. Instructor uploads a new PDF syllabus document.<br>3. System validates the uploaded file type and file size.<br>4. IF the validation fails (e.g., file is too large or not a PDF):<br>&nbsp;&nbsp;&nbsp;* System rejects the upload and displays an error message.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System saves the document to the course repository.<br>&nbsp;&nbsp;&nbsp;* System publishes the syllabus to the student dashboard.<br>&nbsp;&nbsp;&nbsp;* System emails an update notification to all enrolled students. |
| **Entry Condition** | Instructor is assigned to the active course. |
| **Exit Condition** | Syllabus is published and students are notified. |
| **Related NFR** | NR-4 |

---
### 🛠️ Mohamed Hafedh (Admin Workflows)

| Use Case Identifier | UC-11 |
| :--- | :--- |
| **Use Case Name** | Create New Course Section |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to the Curriculum Manager module.<br>2. Admin inputs the section details (course ID, capacity, assigned instructor, and classroom time slot).<br>3. Admin clicks 'Save Section'.<br>4. System checks the database for instructor availability, classroom physical capacity, and timetable conflicts.<br>5. IF a conflict exists (e.g., room is already booked):<br>&nbsp;&nbsp;&nbsp;* System blocks the creation and displays a specific conflict error message.<br>6. ELSE:<br>&nbsp;&nbsp;&nbsp;* System successfully creates and saves the new course section to the database.<br>&nbsp;&nbsp;&nbsp;* System makes the section visible to students for the upcoming registration period. |
| **Entry Condition** | Curriculum planning period is open. |
| **Exit Condition** | New course section is saved and visible. |
| **Related NFR** | NR-3 |

| Use Case Identifier | UC-12 |
| :--- | :--- |
| **Use Case Name** | Manage System Roles |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to the User Management dashboard.<br>2. Admin searches for and selects a specific faculty profile.<br>3. System verifies the Admin's master security clearance.<br>4. IF clearance is insufficient:<br>&nbsp;&nbsp;&nbsp;* System rejects the action and logs a security alert.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* Admin assigns a new role (e.g., adding "Advisor" privileges to an existing "Instructor").<br>&nbsp;&nbsp;&nbsp;* Admin clicks 'Update Roles'.<br>&nbsp;&nbsp;&nbsp;* System saves the new privilege matrix to the database, granting immediate access. |
| **Entry Condition** | Admin is logged in. |
| **Exit Condition** | User roles are updated. |
| **Related NFR** | NR-1 |

| Use Case Identifier | UC-13 |
| :--- | :--- |
| **Use Case Name** | Configure Academic Calendar |
| **Participating Actors** | Admin, System |
| **Flow of Events** | 1. Admin navigates to the Global System Settings module.<br>2. Admin inputs the start and end dates for the upcoming Registration Week and Finals Week.<br>3. System verifies that the start dates logically precede the end dates.<br>4. IF a chronological violation is detected:<br>&nbsp;&nbsp;&nbsp;* System highlights the invalid dates in red and prevents saving.<br>5. ELSE:<br>&nbsp;&nbsp;&nbsp;* System saves the new temporal boundaries to the global database.<br>&nbsp;&nbsp;&nbsp;* System master clock automatically locks or unlocks student registration interfaces based on these dates. |
| **Entry Condition** | Academic calendar configuration is open. |
| **Exit Condition** | Calendar dates are saved and system locks are scheduled. |
| **Related NFR** | NR-2 |
