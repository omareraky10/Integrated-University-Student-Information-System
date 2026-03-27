# Activity Diagrams Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Under **Diagram Navigator**, right-click **Activity Diagram** and select **New**. Create 4 distinct diagrams.
2. **Start and End Nodes**: Always begin by placing an **Initial Node** (solid black circle) at the top, and an **Activity Final Node** (target circle) at the bottom.
3. **Drawing Actions**: Use the **Action** tool (rounded rectangles) to represent the steps.
4. **Control Flows**: Use the **Control Flow** tool (solid arrows) to connect the nodes in sequence.
5. **Decision Nodes**: Drop a **Decision Node** (diamond shape) wherever there is a question (e.g., "Conflict Detected?"). From this diamond, draw two Control Flows out and label them `[Yes]` and `[No]` using the Guard Condition property.
6. **Merge Nodes**: If the `[Yes]` and `[No]` paths eventually meet back up, use a **Merge Node** (also a diamond) to bring them together cleanly before moving to the next Action.

Draw **4 distinct Activity Diagrams** representing logical flowcharts for the system's core algorithmic decisions. Provide one for each member domain.

### 1. Recommendation Engine Algorithm (Hamdo Alhasan)
* **Start Node (Solid Black Circle)**
* **Action:** Check Passed Credits.
* **Decision Node (Diamond):** Missing Compulsory Courses?
  * `[Yes]` --> **Action:** Add Compulsory Courses to pool.
  * `[No]` --> **Action:** Analyze specialized electives from past.
* **Action (Merge point):** Filter matches against Timetable.
* **Decision Node (Diamond):** Timetable Conflict Detected?
  * `[Yes]` --> **Action:** Drop lowest priority elective and search alternative.
  * `[No]` --> **Action:** Render Final Schedule Block.
* **End Node (Target Circle)**

### 2. Advising Workflow (Omar Mohamed)
* **Start Node**
* **Action:** Open Student Registration Request.
* **Decision Node:** Are all prerequisites perfectly met?
  * `[No]` --> **Action:** Reject Request and append reason string. --> **End Node**
  * `[Yes]` --> Proceed downwards.
* **Decision Node:** Is the student asking for more than max limit credits (Overload)?
  * `[Yes]` --> **Action:** Halt process and prompt for 'Official Overload Petition Workflow'.
  * `[No]` --> **Action:** Formally Approve Request.
* **End Node**

### 3. Grading Curve Algorithm (Hesham Alfadhl)
* **Start Node**
* **Action:** Read raw MT & Final scores from memory.
* **Decision Node:** Are ALL enrolled students graded?
  * `[No]` --> **Action:** Loop back to next missing student row.
  * `[Yes]` --> Proceed.
* **Action:** Calculate standard deviation & bell curve boundaries.
* **Action:** Assign categorical Letter Grades (AA, BA, BB...).
* **Action:** Permanently Publish logic block.
* **End Node**

### 4. System Calendar Lifecycle (Mohamed Hafedh)
* **Start Node**
* **Action:** Master Clock reads the active Calendar range.
* **Decision Node:** Is the current date within "Registration Week"?
  * `[No]` --> **Action:** Output "Module Locked". --> **End Node**
  * `[Yes]` --> Proceed.
* **Action:** Enable UC-1 and unfreeze the Registration UI.
* **Action:** Enter a 'Wait/Sleep' state monitoring real-time.
* **Decision Node:** Has the deadline expired?
  * `[Yes]` --> **Action:** Freeze student enrollment capabilities permanently for the active term.
* **End Node**
