# Activity Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Under **Diagram Navigator**, right-click **Activity Diagram** and select **New**. Create 4 distinct diagrams.
2. **Start and End Nodes**: Place an **Initial Node** at the top, and an **Activity Final Node** at the bottom.
3. **Drawing Actions**: Use the **Action** tool (rounded rectangles) to represent steps.
4. **Control Flows**: Use the **Control Flow** tool (solid arrows) to connect nodes.
5. **Decision/Merge Nodes**: Drop **Decision Nodes** (diamonds) for splits and **Merge Nodes** for reconnections.

### 1. Adaptive Academic Pathway Engine (Hamdo Alhasan)
* **Start Node** -> **Action:** Load transcript and curriculum context.
* **Action:** Load dynamic generic program and academic policy rules.
* **Action:** Identify compulsory rules and evaluate elective pathway targets.
* **Action:** Build candidate multi-semester plans based on priorities.
* **Action:** Validate prerequisites and timetable overlap metrics.
* **Decision Node:** Policy violation boundary or excessive workload bottleneck?
  * `[Yes]` --> **Action:** Perform risk assessment generating mitigation alternatives.
  * `[No]` --> Proceed.
* **Action:** Formulate explanation text for the scenario tradeoffs.
* **Action:** Rank the plans (e.g., Fastest Graduation, Balanced Workload).
* **Action:** Output multiple pathway planning results.
* **End Node**

### 2. Advising Workflow (Omar Mohamed)
* **Start Node** -> **Action:** Open Student Registration Block.
* **Decision Node:** Are structural prerequisites satisfied?
  * `[No]` --> **Action:** Reject Request and document error constraint. --> **End Node**
  * `[Yes]` --> Proceed downwards.
* **Decision Node:** Is the credit metric marking an Overload?
  * `[Yes]` --> **Decision Node:** Is mapped Overload Petition Approved via Administration bounds?
    * `[No]` -> Reject request mapping generic failures.
    * `[Yes]` -> Approve request cleanly.
  * `[No]` --> **Action:** Approve request seamlessly.
* **End Node**

### 3. Record Attendance Flow (Hesham Alfadhl)
* **Start Node** -> **Action:** Boot attendance matrix module tracking section logic.
* **Action:** Instructor inputs boolean absent/present states.
* **Action:** System permanently updates record lists structurally.
* **Action:** Compute aggregate student absence metrics.
* **Decision Node:** Maximum absence policy limit breached?
  * `[Yes]` --> **Action:** Trigger active administrative fail flags mapping an `NA` warning block globally.
  * `[No]` --> Proceed smoothly.
* **Action:** Securely close process tracking block.
* **End Node**

### 4. Create New Course Section Lifecycle (Mohamed Hafedh)
* **Start Node** -> **Action:** Populate scheduling rule templates mapping capacity limits.
* **Action:** System queries faculty availability configurations checking internal schedule objects.
* **Decision Node:** Infrastructure capacity or logic timetable collision overlaps?
  * `[Yes]` --> Return explicit error stopping construction constraints block mapping specifically back to UI form constraints.
  * `[No]` --> Proceed efficiently.
* **Action:** Materialize section entity successfully loading visibility parameters across student registration limits securely.
* **End Node**
