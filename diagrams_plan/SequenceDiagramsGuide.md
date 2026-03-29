# Sequence Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Right-click **Sequence Diagram** and select **New Sequence Diagram**.
2. **Adding Lifelines**: Drop the Actor on the left, and UI/Controller/Engine lifelines to the right.
3. **Drawing Messages**: Use the **Message** tool (solid arrow) for synchronous calls, and **Reply Message** (dashed arrow) for returns.
4. **Activation Blocks**: Let Visual Paradigm autogenerate the vertical rectangular execution boxes.

### 1. Simulate What-If Academic Scenario (Hamdo Alhasan)
* **Lifelines:** `Student Actor` -> `Dashboard UI` -> `AcademicPathwayEngine` -> `Policy Database` -> `Transcript Database`
* **Flow:**
  1. `Student` inputs custom simulation variables into `Dashboard UI` (e.g., "delay course").
  2. `UI` calls `simulateScenario(overrides)` mapping directly to the `AcademicPathwayEngine`.
  3. `AcademicPathwayEngine` triggers `loadPolicyContext()` securing data from `Policy Database`.
  4. `AcademicPathwayEngine` triggers `analyzeHistory()` via `Transcript Database`.
  5. `AcademicPathwayEngine` builds candidate multi-semester options and internally executes workload/prerequisite evaluation checks.
  6. `AcademicPathwayEngine` formats explanations and returns a comprehensive `PathwayPlanList[]` containing generated texts and bottleneck metrics.

### 2. Approve Course Selection (Omar Mohamed)
* **Lifelines:** `Advisor Actor` -> `Dashboard UI` -> `RegistrationController` -> `Database`
* **Flow:**
  1. `Advisor` sends `processRequest()` to `Dashboard UI`.
  2. `UI` triggers `evaluateRequest()` inside `RegistrationController`.
  3. **Alternative Box:**
     * **[If Approved]:** Validation passes. Controller executes `UPDATE status='Approved'` and dispatches a success response.
     * **[If Rejected]:** Validation fails. Controller executes `UPDATE status='Failed'` and returns rejection reason logic.

### 3. Enter Course Grades (Hesham Alfadhl)
* **Lifelines:** `Instructor Actor` -> `GradeEntry UI` -> `GradingController` -> `Transcript DB`
* **Flow:**
  1. `Instructor` inputs numerical scores arrays.
  2. `UI` passes numerical bounds to `GradingController`.
  3. `GradingController` validates integer constraints mapping strictly to proper letter grades.
  4. `GradingController` executes operations to `Transcript DB`.
  5. `Transcript DB` acknowledges the backend update successfully.

### 4. Configure Global Academic Policies (Mohamed Hafedh)
* **Lifelines:** `Admin Actor` -> `PolicyPanel UI` -> `PolicyManager` -> `Database`
* **Flow:**
  1. `Admin` submits custom policy logic boundaries explicitly mapped for generic departments via `PolicyPanel UI`.
  2. `PolicyManager` checks constraint boundaries confirming logic structures do not directly conflict.
  3. **Alternative Box:**
     * **[If Clear]:** `PolicyManager` constructs `AcademicPolicy` instances routing them structurally inside the `Database`.
     * **[If Conflict]:** `PolicyManager` issues direct configuration error trace.
