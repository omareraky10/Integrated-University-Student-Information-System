# System Design & Implementation Plan: Generic Academic Planning and Decision-Support Platform

This document outlines the system architecture and project blueprints required for the CENG3004 Software Engineering course project. 

## Overview
The platform represents a generic academic pathway planning, simulation, and decision-support system. Rather than just tracking registration automation in isolation (like a standard OBS), it helps students and advisors evaluate, compare, and optimize academic plans across different universities, departments, and policy environments.

**Added Value Feature:** A generic adaptive academic planning engine that supports multi-semester pathway generation, what-if scenario simulation, policy-aware recommendation, and explainable decision support across different universities, faculties, and departments.

## Actors and Roles
The system accommodates workflows for 4 primary actors:
1. **Student:** Generates long-term academic pathway plans, tests what-if scenarios, and registers for approved schedules.
2. **Instructor:** Manages syllabi, documents attendance, and enters all course assessments (e.g., midterms, finals, projects, quizzes).
3. **Advisor:** Reviews pathway simulations, mitigates risk-assessed warnings, and guides students towards optimal graduation strategies.
4. **Department Staff / Admin:** Configures global/departmental Academic and Graduation Policies, schedules courses, and resolves conflicts.

## Functional Requirements (FR)
- **FR-1:** The system shall manage student registrations and handle prerequisite blocks or exceeded maximum capacities with explicit error messages.
- **FR-2:** The system shall automatically reject unapproved course additions by communicating exact error statuses.
- **FR-3 (Adaptive Academic Planning):** The system shall analyze a student’s transcript, curriculum progress, institutional policies, and scheduling constraints to generate ranked semester and multi-semester academic plans. The system shall prioritize compulsory requirements, recommend suitable electives, validate prerequisites, avoid timetable conflicts, balance workload, and explain the reasoning behind each plan.
- **FR-4:** Instructors must be able to upload grades to the database, enforced by input-value validation.
- **FR-5:** Advisors shall have dedicated dashboards to approve or reject student course selections, requiring a clear reason for any rejections.
- **FR-6:** The system shall calculate CGPA/GPA and dynamically generate official PDF transcripts.
- **FR-7:** Admins shall be able to establish course schedules. The system must prevent classroom or instructor conflicts during creation.
- **FR-8:** The system must process a "Graduation Audit," comparing passed courses against the core curriculum requirements.
- **FR-9 (Simulation):** The system shall support what-if academic planning scenarios and simulate the impact of alternative course selections, delayed courses, and different workload strategies.
- **FR-10 (Strategy Generation):** The system shall generate multiple ranked academic pathway strategies, including at minimum a fastest-graduation plan, a balanced-workload plan, and a recovery-oriented plan when applicable.
- **FR-11 (Generic Policies):** The system shall enforce configurable university, faculty, department, and program-level academic policies during planning and registration.
- **FR-12 (Explainability):** The system shall provide explainable recommendation outputs, including why courses or plans were selected, rejected, or flagged for advisor review.
- **FR-13 (Risk Assessment):** The system shall assess academic planning risks such as overload, delayed graduation, bottleneck prerequisites, and policy-sensitive schedule combinations.

## Nonfunctional Requirements (NR)
- **NR-1 (Security):** Student records must be encrypted, complying with KVKK/FERPA privacy data standards.
- **NR-2 (Availability):** The system shall guarantee 99.9% uptime and remain stable under thousands of concurrent queries during registration week.
- **NR-3 (Performance):** Complex query response times (e.g., Pathway Simulation Generation) must remain under 2.5 seconds under standard loads.
- **NR-4 (Usability):** The interface must be responsive (web and mobile compatible) and support multilingual access.

## Use Case Distribution (14 Total)
*(Note: All use cases assigned below include atomic steps, explicit system responsibilities, and IF/ELSE alternative workflows).*

**Member 1: Hamdo Alhasan (Student Focused):**
1. Register for Courses (UC-1)
2. Generate Academic Pathway Plan (UC-2) **[Core Engine]**
3. Simulate What-If Academic Scenario (UC-3) **[New]**
4. Request Graduation Audit (UC-4)

**Member 2: Omar Mohamed (Advisor Focused):**
5. Approve Course Selection (UC-5)
6. Review Student Pathway Plan (UC-6)
7. Send Academic Warning (UC-7)
8. View Transcript (UC-8) *(Moved to balance load)*

**Member 3: Hesham Alfadhl (Instructor Focused):**
9. Enter Course Grades (UC-9)
10. Record Attendance (UC-10)
11. Update Course Syllabus (UC-11)

**Member 4: Mohamed Hafedh (Admin/Department Focused):**
12. Create New Course Section (UC-12)
13. Manage System Roles (UC-13)
14. Configure Global Academic Policies (UC-14)

## Class Diagram Targets (27 Core Classes)
`User`, `Student`, `Instructor`, `Advisor`, `SystemAdmin`, `Course`, `CourseSection`, `Semester`, `RegistrationRequest`, `Transcript`, `GradeEntry`, `AttendanceRecord`, `GraduationAudit`, `Curriculum`, `PrerequisiteRule`, `Classroom`, `AcademicPathwayEngine`, `University` *(New)*, `Faculty` *(New)*, `Department` *(New)*, `Program` *(New)*, `AcademicPolicy` *(New)*, `GraduationPolicy` *(New)*, `PlanningScenario` *(New)*, `PathwayPlan` *(New)*, `RiskAssessment` *(New)*, `RecommendationExplanation` *(New)*.

## Next Steps
This blueprint transforms the project from a standard OBS into an advanced, configurable, and generic decision-support platform, natively fulfilling the rigorous demands for what-if simulation, multi-semester evaluation, and explainable logic.
