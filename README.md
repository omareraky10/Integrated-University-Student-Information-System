# Integrated University Student Information System

Welcome to the central repository for the **CENG3004 Software Engineering Project**.

## 📖 Project Overview
This project is an advanced, OBS-style platform unifying university academic operations. Instead of keeping graduation checks, grading, and advising in isolated silos, this seamlessly handles full-lifecycle student management. 

**🔥 Added Value Feature:** An **AI-Assisted Smart Course Recommendation Module** that actively analyzes a student's academic history to recommend compulsory courses and specialization-focused electives (e.g., dynamically suggesting *Advanced NLP* if the student passed *AI*), while strictly avoiding timetable clashes.

---

## 👥 Team Assignments & Workflows

To satisfy the system architecture and ensure everyone has an equal workload, the **13 Core Use Cases** have been divided among the team as follows. You are responsible for modeling and eventually implementing your respective domain:

### 1. 👨‍🎓 Hamdo Alhasan (Student Workflows)
* **UC-1:** Register for Courses
* **UC-2:** Generate Smart Course Recommendations *(Core Innovation)*
* **UC-3:** View Transcript
* **UC-4:** Request Graduation Audit

### 2. 👨‍🏫 Omar Mohamed Elerakky (Advisor Workflows)
* **UC-5:** Approve Course Selection
* **UC-6:** Review Student Study Plan
* **UC-7:** Send Academic Warning

### 3. 👨‍💻 Hesham Alfadhl (Instructor Workflows)
* **UC-8:** Enter Course Grades
* **UC-9:** Record Attendance
* **UC-10:** Update Course Syllabus

### 4. 🛠️ Mohamed elhafedh el gharachi (Admin / Department Workflows)
* **UC-11:** Create New Course Section
* **UC-12:** Manage System Roles
* **UC-13:** Configure Academic Calendar

---

## 🏗️ UML Diagram Checklists
Our project utilizes **Visual Paradigm** to map out the system architecture. We have exactly **16 Core Classes** serving our workflows. Every team member is responsible for drawing their specific logic flows:

* **1 Master Use Case Diagram** connecting our 4 Actors (Student, Advisor, Instructor, Admin) to the 13 modules above.
* **1 Master Class Diagram** featuring exactly 16 Classes (e.g., `Student`, `RecommendationEngine`, `RegistrationRequest`).
* **4 Sequence Diagrams** (1 logic sequence mapped per member for your main Use Case).
* **4 Activity Diagrams** (1 algorithm flowchart mapped per member).
* **1 Master Statechart Diagram** tracking the state lifecycle of the `RegistrationRequest` module.

*(For exact, step-by-step UI drawing instructions and the full Use Case tables, please refer to the detailed Project Analysis artifacts successfully generated alongside this repo!)*

---

## 🚀 Getting Started
1. Clone this repository to your local machine.
2. Review your specific assigned Use Cases above.
3. Open the shared `.vpp` Visual Paradigm file (once initialized) and begin modeling your specific Sequence and Activity diagrams.
4. Update the formal `ProjectAnalysisDocument.md` or `.docx` with your diagrams.
5. Good luck with the midterm presentation!