# Statechart Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open the **Diagram Navigator**, right-click **State Machine Diagram**, and select **New**.
2. **Start and Terminate**: Place an **Initial Pseudo State** (black dot) to start, and a **Final State** (target symbol) to terminate the object.
3. **Defining States**: Drop **State** nodes (rounded rectangles).
4. **Drawing Transitions**: Use the **Transition** arrow to connect the states. 
5. **Adding Triggers**: Double-click the transition arrows to label them with the triggering event.

Draw **1 State Machine Diagram** illustrating the lifecycle of a `PlanningScenario` inside the `AcademicPathwayEngine`.

1. **Initial Node (Black Dot)** transitions to -> `[Drafting_Parameters]`
2. **State:** `[Drafting_Parameters]`
   * Trigger: `Student defines assumptions` -> Destination: `[Simulating_Pathways]`
3. **State:** `[Simulating_Pathways]`
   * Trigger 1: `Rule contradiction found` -> Destination: `[Evaluating_Risk_Mitigation]`
   * Trigger 2: `Clean calculation` -> Destination: `[Ranked_and_Reviewed]`
4. **State:** `[Evaluating_Risk_Mitigation]`
   * Trigger: `Engine marks warnings` -> Destination: `[Ranked_and_Reviewed]`
5. **State:** `[Ranked_and_Reviewed]`
   * Trigger 1: `Student discards scenario` -> Destination: **[Final Node]**
   * Trigger 2: `Student confirms selection` -> Destination: `[Saved_Active_Strategy]`
6. **State:** `[Saved_Active_Strategy]` transitions implicitly to **[Final Node]** upon graduation or abandonment.
