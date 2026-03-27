# Statechart Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open the **Diagram Navigator**, right-click **State Machine Diagram**, and select **New**.
2. **Start and Terminate**: Place an **Initial Pseudo State** (black dot) to start, and a **Final State** (target symbol) to act as the eventual destruction of the object.
3. **Defining States**: Drop **State** nodes (rounded rectangles) onto the canvas for each distinct phase of the `RegistrationRequest` lifecycle (e.g., `Draft`, `Officially_Enrolled`).
4. **Drawing Transitions**: Use the **Transition** arrow to connect the states. 
5. **Adding Triggers**: Double-click the transition arrows to label them with the exact triggering event (e.g., "Advisor clicks Approve" or "Semester naturally concludes") that causes the object to shift states.

Draw **1 State Machine Diagram** illustrating the strict object lifecycle transitions of a `RegistrationRequest` module in Visual Paradigm state nodes.

1. **Initial Node (Black Dot)** points an arrow to -> `[Draft]`
2. **State:** `[Draft]`
   * Trigger arrow: `User clicks Submit` 
   * Destination: `[Pending_Advisor_Review]`
3. **State:** `[Pending_Advisor_Review]`
   * Trigger arrow 1: `Advisor clicks Reject` -> Destination: `[Failed_and_Returned]`
   * Trigger arrow 2: `Advisor clicks Approve` -> Destination: `[Officially_Enrolled]`
4. **State:** `[Officially_Enrolled]`
   * Trigger arrow 1: `Student withdraws mid-semester` -> Destination: `[Dropped_With_W_Record]`
   * Trigger arrow 2: `Semester naturally concludes` -> Destination: `[Completed]`
5. From `[Completed]`, draw an arrow to the **Final Node (Target Circle)** to signify the end of the object's mutability lifecycle.
