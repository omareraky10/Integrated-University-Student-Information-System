# Activity Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Under **Diagram Navigator**, right-click **Activity Diagram** and select **New**. Create 4 distinct diagrams.
2. **Start and End Nodes**: Place an **Initial Node** at the top, and an **Activity Final Node** at the bottom.
3. **Drawing Actions**: Use the **Action** tool (rounded rectangles) to represent steps.
4. **Control Flows**: Use the **Control Flow** tool (solid arrows) to connect nodes.
5. **Decision/Merge Nodes**: Drop **Decision Nodes** (diamonds) for splits and **Merge Nodes** for reconnections.

### 1. Recommendation Engine Algorithm (Hamdo Alhasan)
* **Start Node** -> **Action:** Check Passed Courses/Transcript.
* **Action:** Identify Missing Compulsory Courses.
* **Action:** Select Candidate Electives.
* **Action:** Validate Prerequisites.
* **Decision Node:** Timetable Conflict Detected?
  * `[Yes]` --> **Action:** Choose alternative elective --> **(Loops back to Validate Prerequisites)**.
  * `[No]` --> **Action:** Output Final Schedule.
* **End Node**

### 2. Advising Workflow (Omar Mohamed)
* **Start Node** -> **Action:** Open Student Registration Request.
* **Decision Node:** Are all prerequisites met?
  * `[No]` --> **Action:** Reject Request and record reason. --> **End Node**
  * `[Yes]` --> Proceed downwards.
* **Decision Node:** Is the workload an Overload?
  * `[Yes]` --> **Decision Node:** Is Overload Petition Approved?
    * `[No]` -> Reject request.
    * `[Yes]` -> Approve request.
  * `[No]` --> **Action:** Approve request.
* **End Node**

### 3. Standard Grade-Entry Workflow (Hesham Alfadhl)
* **Start Node** -> **Action:** Open Grade Sheet.
* **Action:** Enter Numerical Scores.
* **Action:** Validate Scores (0-100).
* **Decision Node:** Are all inputs valid?
  * `[No]` --> Return Error and Loop Back.
  * `[Yes]` --> Proceed.
* **Action:** Convert Scores to Letter Grades.
* **Action:** Publish Grades.
* **Action:** Update Transcripts in database.
* **End Node**

### 4. System Calendar Lifecycle (Mohamed Hafedh)
* **Start Node** -> **Action:** Monitor current date/time.
* **Decision Node:** Has the academic deadline expired?
  * `[No]` --> **(Loops back)** to "Monitor current date/time".
  * `[Yes]` --> Proceed.
* **Action:** Freeze student enrollment capabilities.
* **End Node**
