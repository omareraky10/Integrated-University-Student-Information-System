# Class Diagram Blueprint

## Visual Paradigm Drawing Instructions
1. **Selecting the Tool**: Open Visual Paradigm, navigate to the **Diagram Navigator**, right-click **Class Diagram**, and select **New Class Diagram**.
2. **Drawing Classes**: Use the **Class** tool from the left palette to drop 16 class rectangles onto the canvas. Double-click to set the names.
3. **Adding Attributes & Methods**: Right-click a Class -> **Add** -> **Attribute** (or **Operation** for methods). Include the attributes and methods mapped below.
4. **Drawing Generalization (Inheritance)**: Select the **Generalization** arrow tool. Click and drag from the child classes (`Student`, `Instructor`, `Advisor`, `SystemAdmin`) to the parent class (`User`).
5. **Drawing Associations**: Use the **Association** line tool to connect transactional classes (e.g., `Course` to `CourseSection`). Set the multiplicity (e.g., `1` to `*`) by right-clicking the ends of the association line.
6. **Drawing Dependencies**: Use the **Dependency** dashed arrow from `RecommendationEngine` to `Transcript` to show it relies on this data.

Draw exactly **1 large Class Diagram** mapping the interconnected web of the **16 core classes** below. 

### Core User Inheritance
1. **User (Parent Class)**
   - Attributes: `userID`, `passwordHash`, `email`
   - Methods: `authenticate()`, `resetPassword()`
2. **Student (Inherits from User)**
   - Attributes: `studentNumber`, `gpa`, `startingYear`
   - Methods: `requestAudit()`, `registerCourse()`
3. **Instructor (Inherits from User)**
   - Attributes: `title`, `officeBlock`
   - Methods: `publishGrades()`, `takeAttendance()`
4. **Advisor (Inherits from User)**
   - Attributes: `departmentAssigned`
   - Methods: `approveSchedule()`, `sendWarning()`
5. **SystemAdmin (Inherits from User)**
   - Attributes: `permissionLevel`
   - Methods: `updateCalendar()`, `assignRoles()`

### Academic Modules
6. **Course**
   - Attributes: `courseCode`, `name`, `credits`, `isCompulsory`
7. **CourseSection**
   - Attributes: `sectionID`, `currentCapacity`, `maxCapacity`, `timeSlot`
   - Association: `Course` (1) has (many) `CourseSection`
8. **Semester**
   - Attributes: `termName`, `year`, `isActive`
9. **Curriculum**
   - Attributes: `programName`, `requiredCredits`
10. **Classroom**
   - Attributes: `roomNumber`, `maxSeats`, `buildingName`

### Transactions & Business Logic
11. **RegistrationRequest**
    - Attributes: `status` (Pending/Approved/Rejected), `dateSubmitted`
    - Association: Connects `Student` to `CourseSection`.
12. **GradeEntry**
    - Attributes: `midtermScore`, `finalScore`, `letterGrade`
    - Association: Belongs to one `CourseSection` and one `Student`.
13. **Transcript**
    - Attributes: `totalCreditsEquated`, `cgpa`
    - Association: Connected to exactly one `Student`.
14. **AttendanceRecord**
    - Attributes: `dateRecorded`, `isPresent`
    - Association: Tracks `Student` inside a `CourseSection`.
15. **GraduationAudit**
    - Attributes: `isEligible`, `remainingRequiredCredits`
    - Methods: `generateReport()`
16. **RecommendationEngine**
    - Methods: `analyzeHistory()`, `suggestConflictFreeCourses()`
    - Dependency: Draws data from `Transcript` and `Curriculum`.
