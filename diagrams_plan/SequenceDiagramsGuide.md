# Sequence Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Over in the **Diagram Navigator**, right-click **Sequence Diagram** and select **New Sequence Diagram**. You will create 4 separate diagrams.
2. **Adding Lifelines (Actors/Objects)**: Use the **Actor** and **Lifeline** tools from the palette. Drop the initiating Actor on the far left, and place UI/Controller/Database lifelines to their right sequentially.
3. **Drawing Messages**: Use the **Message** tool (solid arrow) to draw synchronous calls from one lifeline's activation box to another. Name the message exactly as described in the flow (e.g., `clickRecommend()`).
4. **Drawing Return Messages**: Use the **Reply Message** tool (dashed arrow) to show data returning backwards (e.g., returning the CourseList to the UI).
5. **Activation Blocks**: Visual Paradigm will automatically generate the vertical rectangular Activation blocks when you connect messages. Adjust their height to indicate how long the process takes.

Draw **4 distinct Sequence Diagrams** (one for each team member) modeling the lifelines of the core Use Cases.

### 1. Smart Course Recommendation (Hamdo Alhasan)
* **Lifelines (top blocks):** `Student Actor` -> `Dashboard UI` -> `RecommendationEngine` -> `Transcript DB` -> `Curriculum DB`
* **Flow:**
  1. `Student` sends message `clickRecommend()` to `UI`.
  2. `UI` calls `analyzeHistory(studentID)` on `RecommendationEngine`.
  3. `RecommendationEngine` queries `Transcript DB` (`getPastGrades()`) and `Curriculum DB` (`getRules()`).
  4. Both databases return the data arrays.
  5. `RecommendationEngine` processes constraints internally and returns a `CourseList[]` object back to the `UI`.
  6. `UI` displays the conflict-free schedule to the `Student`.

### 2. Approve Course Selection (Omar Mohamed)
* **Lifelines:** `Advisor Actor` -> `Dashboard UI` -> `RegistrationController` -> `Database` -> `NotificationSystem`
* **Flow:**
  1. `Advisor` sends `approveRequest(requestID)` to `Dashboard UI`.
  2. `Dashboard UI` passes the command to `RegistrationController`.
  3. `RegistrationController` validates and executes an UPDATE in `Database`.
  4. `Database` returns an `ACK/Success` signal to `RegistrationController`.
  5. `RegistrationController` invokes `sendEmail()` on the `NotificationSystem`.
  6. `RegistrationController` returns the green "Success" flag to the `Dashboard UI` for the Advisor.

### 3. Enter Course Grades (Hesham Alfadhl)
* **Lifelines:** `Instructor Actor` -> `GradeEntry UI` -> `GradingController` -> `TranscriptCalculator` -> `Database`
* **Flow:**
  1. `Instructor` inputs numerical scores into the `GradeEntry UI`.
  2. `UI` passes numerical arrays to `GradingController`.
  3. `GradingController` converts numericals to Letter Grades.
  4. `GradingController` fires an event to `TranscriptCalculator` to update the CGPA.
  5. Both objects save their definitive states into the `Database`.
  6. `Database` acknowledges, and `GradingController` confirms success to the Instructor.

### 4. Create New Course Section (Mohamed Hafedh)
* **Lifelines:** `Admin Actor` -> `AdminPanel UI` -> `CourseManager` -> `Classroom DB` -> `Course DB`
* **Flow:**
  1. `Admin` submits the form to `AdminPanel UI`.
  2. `UI` routes the `createSection()` command to `CourseManager`.
  3. `CourseManager` queries `Classroom DB` to check for timetable conflicts.
  4. `Classroom DB` returns boolean `isFree == True`.
  5. `CourseManager` persists the new section instance into `Course DB`.
  6. Success response bubbles back up to the Admin.
