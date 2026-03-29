# Class Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open Visual Paradigm, navigate to the **Diagram Navigator**, right-click **Class Diagram**, and select **New Class Diagram**.
2. **Drawing Classes**: Use the **Class** tool to drop all **27** class rectangles onto the canvas. Double-click to set names.
3. **Defining the Generic Platform**: Arrange the institutional foundation (`University`, `Faculty`) separate from generic `AcademicPolicy` rules.
4. **Drawing Generalization (Inheritance)**: Select the **Generalization** arrow tool. Click from child classes to the `User` parent class.
5. **Drawing Associations**: Use the **Association** line tool. 
6. **Drawing Dependencies**: Use the **Dependency** dashed arrow.

Draw exactly **1 large Class Diagram** mapping the **27 core classes** below. 

### Core User Identity
1. **User (Parent Class)**
2. **Student**
3. **Instructor**
4. **Advisor**
5. **SystemAdmin**

### Institutional Infrastructure (Generic Domain)
6. **University**
7. **Faculty**
8. **Department**
9. **Program**
10. **AcademicPolicy**
11. **GraduationPolicy**

### Academic Framework
12. **Curriculum**
13. **Course**
14. **PrerequisiteRule**
15. **CourseSection**
16. **Semester**
17. **Classroom**

### Adaptive Decision Support Engine
18. **AcademicPathwayEngine**
19. **PlanningScenario**
20. **PathwayPlan**
21. **RiskAssessment**
22. **RecommendationExplanation**

### Primary Transactions
23. **RegistrationRequest**
24. **Transcript**
25. **GradeEntry**
26. **AttendanceRecord**
27. **GraduationAudit**

### Key Structural Associations to Draw
* `University` contains `Faculty`, which contains `Department`, which offers modern `Program` bounds pointing to a specific `Curriculum`.
* Each `Program` is mapped to generic configurable `AcademicPolicy` boundaries.
* A `Student` initiates a hypothetical `PlanningScenario`.
* The `AcademicPathwayEngine` directly integrates `PlanningScenario`, `Transcript`, and `AcademicPolicy`.
* The engine actively produces `PathwayPlan` arrays mapping to one `RiskAssessment` block and a `RecommendationExplanation`.
