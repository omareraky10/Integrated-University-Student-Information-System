# Sequence Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Right-click **Sequence Diagram** and select **New Sequence Diagram**.
2. **Adding Lifelines**: Drop the Actor on the left, and UI/Controller/Database lifelines to the right.
3. **Drawing Messages**: Use the **Message** tool (solid arrow) for synchronous calls, and **Reply Message** (dashed arrow) for returns.
4. **Activation Blocks**: Let Visual Paradigm autogenerate the vertical rectangular execution boxes.

### 1. Smart Course Recommendation (Hamdo Alhasan)
* **Lifelines:** `Student Actor` -> `Dashboard UI` -> `RecommendationEngine` -> `Database`
* **Flow:**
  1. `Student` sends `clickRecommend()` to `UI`.
  2. `UI` calls `analyzeHistory()` on `RecommendationEngine`.
  3. `RecommendationEngine` requests missing courses and checks for timetable conflicts via `checkConflicts()`.
  4. `Database` returns data.
  5. `RecommendationEngine` processes data and returns a `CourseList[]` array.

### 2. Approve Course Selection (Omar Mohamed)
* **Lifelines:** `Advisor Actor` -> `Dashboard UI` -> `RegistrationController` -> `Database`
* **Flow:**
  1. `Advisor` sends `processRequest()` to `Dashboard UI`.
  2. `UI` triggers `evaluateRequest()` in `RegistrationController`.
  3. **Alternative Fragment (ALT Box):**
     * **[If Approved]:** Validation passes. Controller executes `UPDATE status='Approved'` in `Database` and sends a success notification.
     * **[If Rejected]:** Validation fails. Controller executes `UPDATE status='Failed'` in `Database` and sends a rejection email.

### 3. Enter Course Grades (Hesham Alfadhl)
* **Lifelines:** `Instructor Actor` -> `GradeEntry UI` -> `GradingController` -> `Transcript DB`
* **Flow:**
  1. `Instructor` inputs numerical scores into `GradeEntry UI`.
  2. `UI` passes numerical values to `GradingController`.
  3. `GradingController` validates numerical boundaries and computes letter grades.
  4. `GradingController` writes the sorted results directly to `Transcript DB`.
  5. `Transcript DB` acknowledges the backend update.

### 4. Create New Course Section (Mohamed Hafedh)
* **Lifelines:** `Admin Actor` -> `AdminPanel UI` -> `CourseManager` -> `Database`
* **Flow:**
  1. `Admin` submits form data to `AdminPanel UI`.
  2. `CourseManager` queries `Database` to check Instructor Availability, Section Time Conflict, and Classroom Capacity.
  3. **Alternative Fragment (ALT Box):**
     * **[If Conflict Found]:** `Database` rejects constraints. `CourseManager` returns an explicit error message to the UI.
     * **[If Clear]:** `CourseManager` saves the new section instance into the `Database`.
