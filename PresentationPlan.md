# Midterm Presentation Plan

**Project:** Integrated University Student Information System
**Time Allocation:** 10 minutes presentation + 5 minutes Q&A

---

## Slide 1: Title Slide (1 minute)
* **Project Name:** Integrated University Student Information System
* **Course:** CENG3004 Software Engineering
* **Team Members:** Omar Mohamed Elerakky, Hamdo Alhasan, Hesham Alfadhl, Mohamed elhafedh el gharachi

## Slide 2: Project Motivation (Why? What is the problem?) (2.5 minutes)
* **The Problem:** Many universities use fragmented systems. Students struggle to navigate disjointed platforms to check graduation requirements, advisors spend hours manually validating prerequisites, and course registration often involves confusing schedule classes and poor elective guidance. 
* **Our Solution:** A unified, centralized platform that seamlessly handles registration, advisory, grading, and graduation auditing all in one place.
* **The Core Innovation:** We augmented the standard flow with an **AI-Assisted Smart Course Recommendation Module**. This module actively analyzes a student's academic history to recommend conflict-free, specialization-focused schedules (e.g., dynamically suggesting *Advanced NLP* if the student successfully completed *AI*). 

## Slide 3: Example Functional Requirement (2 minutes)
* **Requirement (FR-3): Smart Course Recommendation Engine**
* **Description:** The system shall analyze a student’s academic history and automatically recommend a comprehensive course schedule for the upcoming semester.
* **Key Mechanisms:** 
  1. Identifies and strictly prioritizes unfulfilled compulsory courses.
  2. Evaluates past completed electives to uncover a specialization direction, recommending relevant follow-up courses to build a consistent academic pathway.
  3. Executes real-time prerequisite validation and filters out any options that clash in the weekly timetable.

## Slide 4: Example Nonfunctional Requirement (1 minute)
* **Requirement (NR-2): High Availability & Concurrency during Peak Events**
* **Description:** The system must guarantee 99.9% uptime and smoothly handle massive concurrent traffic spikes (simulating up to 5,000 active sessions) during the critical "Registration Week" period.
* **Why it matters:** Course registration is notoriously stressful for students. Our system architecture ensures that the database and session managers scale properly, preventing the dreaded system crashes that typically plague university registration portals under extreme load.

## Slide 5: One Use Case Diagram (2 minutes)
* **Diagram to Draw:** "Generate Smart Course Recommendations" (UC-2)
* **Description of the Drawing:** 
  * Add a primary actor on the left: **Student**.
  * Add the central use case oval: **Generate Smart Course Recommendations**. 
  * Draw a solid association line connecting the Student to this central use case.
  * Add additional use case ovals that are `<<include>>`d: **Validate Prerequisites** and **Check Timetable Conflicts**. Draw dashed arrows pointing to them from the central use case with the `<<include>>` stereotype.
  * Add a secondary actor on the right: **Scheduling Database**. Connect it with a solid line to the primary use case to show where the system pulls the active course metrics from.

## Slide 6: One Class Diagram (1.5 minutes)
* **Diagram to Draw:** Academic Registration and Recommendation Framework
* **Description of the Drawing:** 
  * Draw a central **Student** class (attributes: `studentID`, `GPA`, `semester`).
  * Draw a **Transcript** class and connect it to the Student (1 to 1). This holds historical grades.
  * Draw a **RecommendationEngine** class (methods: `analyzeHistory()`, `findElectiveTrends()`). Show a dependency arrow pointing from it to the Transcript.
  * Draw a **CourseSection** class (attributes: `capacity`, `schedule`, `instructorID`).
  * Draw a **RegistrationRequest** class (attributes: `status`, `dateSubmitted`).
  * Show the relations: A Student explicitly initiates a RegistrationRequest (1 to Many), which maps to one or more CourseSections (Many to Many).
