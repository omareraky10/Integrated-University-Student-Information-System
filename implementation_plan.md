# System Design & Implementation Plan: Integrated University Student Information System

This document outlines the system architecture and project blueprints required for the CENG3004 Software Engineering course project. 

## Overview
The "Integrated University Student Information System" is a comprehensive, OBS-style platform unifying academic operations. Rather than just tracking graduation in isolation, it handles full-lifecycle student management—registration, grading, advising, transcripts, degree auditing, AND smart course scheduling.

**Added Value Feature:** A Smart Course Recommendation module that analyzes a student's academic history, selects compulsory courses, and recommends electives based on specialization history (e.g., suggesting NLP following an AI course) while strictly avoiding timetable conflicts.

## Actors and Roles
The system accommodates workflows for 4 primary actors, tailored for a 4-person development team:
1. **Student:** Registers for courses, receives smart scheduling recommendations, tracks grades, and requests audits.
2. **Instructor:** Manages syllabi, documents attendance, and enters midterm/final grades.
3. **Academic Advisor:** Reviews, approves, or rejects student course registrations and monitors academic warnings.
4. **Department Staff / Admin:** Schedules courses, assigns capacities, resolves conflicts, and manages overarching system deadlines.

## Functional Requirements (FR)
- **FR-1:** The system shall allow students to register for courses subject to prerequisite checks.
- **FR-2:** The system shall actively block registration if course capacity or prerequisite rules fail.
- **FR-3 (Smart Recommendation):** The system shall analyze the student’s academic history and recommend courses for the upcoming semester. It must prioritize unfulfilled required courses, then recommend electives based on specialization direction (e.g., AI -> NLP). It must ensure prerequisite satisfaction, evaluate remaining credits, and provide multiple conflict-free schedule options.
- **FR-4:** Instructors must be able to upload grades to the centralized database linked to student portals.
- **FR-5:** Advisors shall have dedicated dashboards to approve/reject student course selections.
- **FR-6:** The system shall calculate CGPA/GPA and generate official transcripts.
- **FR-7:** Admins shall be able to establish course schedules and allocate physical classrooms.
- **FR-8:** The system must process a "Graduation Audit," comparing earned credits against curriculum restrictions.

## Nonfunctional Requirements (NR)
- **NR-1 (Security):** Student records must be encrypted, complying with KVKK/FERPA standards.
- **NR-2 (Availability):** The system shall guarantee 99.9% uptime, particularly during registration week.
- **NR-3 (Performance):** Query response times must remain under 2.0 seconds under standard loads.
- **NR-4 (Usability):** The interface must be responsive (web and mobile compatible) and multilingual.

## Use Case Distribution (13 Total - Minimum 3 per Team Member)
**Member 1: Hamdo Alhasan (Student Focused):**
1. Register for Courses (UC-1)
2. Generate Smart Course Recommendations (UC-2) **[Core Value Add]**
3. View Transcript (UC-3)
4. Request Graduation Audit (UC-4)

**Member 2: Omar Mohamed (Advisor Focused):**
5. Approve Course Selection (UC-5)
6. Review Student Study Plan (UC-6)
7. Send Academic Warning (UC-7)

**Member 3: Hesham Alfadhl (Instructor Focused):**
8. Enter Course Grades (UC-8)
9. Record Attendance (UC-9)
10. Update Course Syllabus (UC-10)

**Member 4: Mohamed Hafedh (Admin/Department Focused):**
11. Create New Course Section (UC-11)
12. Manage System Roles (UC-12)
13. Configure Academic Calendar (UC-13)

## Class Diagram Targets (17 Core Classes)
`User`, `Student`, `Instructor`, `Advisor`, `SystemAdmin`, `Course`, `CourseSection`, `Semester`, `RegistrationRequest`, `Transcript`, `GradeEntry`, `AttendanceRecord`, `GraduationAudit`, `Curriculum`, `PrerequisiteRule`, `Classroom`, `RecommendationEngine`.

## Next Steps
This enhanced blueprint integrates the cutting-edge academic AI recommendation engine directly into the core workflows required by the professor's rubric. I will proceed to transcribe this design into the formal [ProjectAnalysisDocument.md](file:///home/omar/.gemini/antigravity/brain/77a204a9-a7e8-469d-9e7f-fd377b94cf9b/ProjectAnalysisDocument.md).
