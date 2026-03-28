# Class Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open Visual Paradigm, navigate to the **Diagram Navigator**, right-click **Class Diagram**, and select **New Class Diagram**.
2. **Drawing Classes**: Use the **Class** tool to drop exactly **17** class rectangles onto the canvas. Double-click to set names.
3. **Adding Attributes & Methods**: Right-click a Class -> **Add** -> **Attribute** (or **Operation** for methods). 
4. **Drawing Generalization (Inheritance)**: Select the **Generalization** arrow tool. Click from child classes to the `User` parent class.
5. **Drawing Associations**: Use the **Association** line tool. 
6. **Drawing Dependencies**: Use the **Dependency** dashed arrow.

Draw exactly **1 large Class Diagram** mapping the **17 core classes** below. 

### Core User Inheritance
1. **User (Parent Class)**
2. **Student (Inherits from User)**
   - Association: `Student` (1) connected to (1) `Curriculum`.
3. **Instructor (Inherits from User)**
4. **Advisor (Inherits from User)**
5. **SystemAdmin (Inherits from User)**

### Academic Modules
6. **Course**
7. **PrerequisiteRule**
   - Association: `Course` (1) has (*) `PrerequisiteRule`.
8. **CourseSection**
   - Association: `Course` (1) has (*) `CourseSection`.
   - Association: `CourseSection` (*) taught by (1) `Instructor`.
   - Association: `CourseSection` (*) located in (1) `Classroom`.
   - Association: `CourseSection` (*) belongs to (1) `Semester`.
9. **Semester**
10. **Curriculum**
11. **Classroom**

### Transactions & Business Logic
12. **RegistrationRequest**
    - Association: Connects `Student` to `CourseSection`.
13. **GradeEntry**
    - Association: Belongs to one `CourseSection` and one `Student`.
14. **Transcript**
    - Association: Connected to exactly one `Student` (1 to 1).
15. **AttendanceRecord**
    - Association: Tracks `Student` inside a single `CourseSection`.
16. **GraduationAudit**
    - Dependency: Draws implicitly from matching `Student` and `Curriculum`.
17. **RecommendationEngine**
    - Dependency: Draws from `Transcript` and `Curriculum`.
