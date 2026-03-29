# Generic Academic Planning and Decision-Support Platform

Welcome to the central repository for the **CENG3004 Software Engineering Project**.

## 📖 Project Overview
This project is an adaptive academic pathway planning, simulation, and decision-support platform. It evaluates, compares, and optimizes academic plans across different generic universities, departments, and policy environments.

**🔥 Added Value Feature:** A generic **Adaptive Academic Pathway Planning Engine** that supports multi-semester pathway generation, what-if scenario simulation, policy-aware recommendation, and explainable decision support across different institutions.

---

## 👥 Team Assignments & Workflows

To satisfy the system architecture and ensure everyone has an equal workload, the **14 Core Use Cases** have been divided among the team as follows. You are responsible for modeling and eventually implementing your respective domain:

### 1. 👨‍🎓 Hamdo Alhasan (Student Workflows)
* **UC-1:** Register for Courses
* **UC-2:** Generate Academic Pathway Plan *(Core Engine)*
* **UC-3:** Simulate What-If Academic Scenario *(Core Target)*
* **UC-4:** Request Graduation Audit

### 2. 👨‍🏫 Omar Mohamed Elerakky (Advisor Workflows)
* **UC-5:** Approve Course Selection
* **UC-6:** Review Student Pathway Plan
* **UC-7:** Send Academic Warning
* **UC-8:** View Transcript

### 3. 👨‍💻 Hesham Alfadhl (Instructor Workflows)
* **UC-9:** Enter Course Grades
* **UC-10:** Record Attendance
* **UC-11:** Update Course Syllabus

### 4. 🛠️ Mohamed elhafedh el gharachi (Admin / Department Workflows)
* **UC-12:** Create New Course Section
* **UC-13:** Manage System Roles
* **UC-14:** Configure Global Academic Policies

---

## 🏗️ UML Diagram Checklists
Our project utilizes **Visual Paradigm** to map out the heavily integrated system architecture. We have precisely **27 Core Classes** securely mapping our workflows. Every team member is responsible for drawing their specific logic flows:

* **1 Master Use Case Diagram** connecting our 4 Actors (Student, Advisor, Instructor, Admin) to the 14 modules above.
* **1 Master Class Diagram** featuring exactly 27 Classes (e.g., `University`, `AcademicPolicy`, `PlanningScenario`, `AcademicPathwayEngine`).
* **4 Sequence Diagrams** (1 logic sequence mapped per member for your main Use Case).
* **4 Activity Diagrams** (1 algorithm flowchart mapped per member).
* **1 Master Statechart Diagram** tracking the state lifecycle of a `PlanningScenario` transitioning safely from Drafting to Evaluated states.

*(For exact, step-by-step UI drawing instructions and the full Use Case tables, please refer to the detailed Project Analysis artifacts successfully generated alongside this repo!)*

---

## 🚀 Getting Started
1. Clone this repository to your local machine.
2. Review your specific assigned Use Cases above.
3. Open the shared `.vpp` Visual Paradigm file (once initialized) and begin modeling your specific Sequence and Activity diagrams.
4. Update the formal `ProjectAnalysisDocument.md` or `.docx` with your diagrams.
5. Good luck with the midterm presentation!