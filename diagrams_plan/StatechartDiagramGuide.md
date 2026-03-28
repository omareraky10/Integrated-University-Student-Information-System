# Statechart Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open the **Diagram Navigator**, right-click **State Machine Diagram**, and select **New**.
2. **Start and Terminate**: Place an **Initial Pseudo State** (black dot) to start, and a **Final State** (target symbol) to terminate the object.
3. **Defining States**: Drop **State** nodes (rounded rectangles).
4. **Drawing Transitions**: Use the **Transition** arrow to connect the states. 
5. **Adding Triggers**: Double-click the transition arrows to label them with the triggering event.

Draw **1 State Machine Diagram** illustrating the lifecycle of a `RegistrationRequest`.

1. **Initial Node (Black Dot)** transitions to -> `[Draft]`
2. **State:** `[Draft]`
   * Trigger: `Student Submits` -> Destination: `[Pending_Advisor_Review]`
3. **State:** `[Pending_Advisor_Review]`
   * Trigger 1: `Advisor Rejects` -> Destination: `[Failed_and_Returned]`
   * Trigger 2: `Advisor Approves` -> Destination: `[Officially_Enrolled]`
4. **State:** `[Failed_and_Returned]`
   * Trigger 1: `Student Edits & Resubmits` -> Destination: `[Draft]`
   * Trigger 2: `Student Cancels Request` -> Destination: **[Final Node]**
5. **State:** `[Officially_Enrolled]`
   * Trigger 1: `Student Withdraws` -> Destination: `[Dropped_With_W_Record]`
   * Trigger 2: `Semester concludes` -> Destination: `[Completed]`
6. **State:** `[Dropped_With_W_Record]` transitions to **[Final Node]**.
7. **State:** `[Completed]` transitions to **[Final Node]**.
