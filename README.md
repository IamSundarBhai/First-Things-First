### **Software Requirements Specification (SRS) for the First Things First (FTF) Application**

---

#### **1. Introduction**

**1.1 Purpose**
The purpose of this document is to outline the software requirements for the development of the First Things First (FTF) application. FTF is a task management and prioritization application that assists users in identifying and focusing on their most important and urgent tasks. The application helps users manage their time efficiently by categorizing tasks into various priority levels and enabling effective scheduling.

**1.2 Scope**
The FTF application will include the following functionalities:
- Task creation and categorization (by urgency and importance).
- Calendar and reminder integration.
- Prioritization of tasks using the Eisenhower matrix.
- Task completion tracking.
- Analytics and reporting on task completion rates and trends.
- Multi-device support (Mobile, Web).
- Integration with third-party calendar applications (Google Calendar, Outlook).
  
**1.3 Definitions, Acronyms, and Abbreviations**
- **FTF**: First Things First
- **UX**: User Experience
- **UI**: User Interface
- **CRUD**: Create, Read, Update, Delete
- **API**: Application Programming Interface

**1.4 Overview**
The remainder of this document outlines the functional and non-functional requirements, user stories, modules, and wireframes for the FTF application.

---

#### **2. Functional Requirements**

**2.1 User Registration and Authentication**
- **FR-1**: The application must allow users to register via email, Google, or social media.
- **FR-2**: Users must be able to log in and log out securely.
- **FR-3**: Users can reset passwords using a password recovery feature.
- **FR-4**: OAuth integration for Google and Facebook login.

**2.2 Task Management**
- **FR-5**: Users must be able to create new tasks with a title, description, and due date.
- **FR-6**: Users can assign tasks a priority level (urgent, not urgent, important, not important).
- **FR-7**: Users must be able to assign a task category (work, personal, etc.).
- **FR-8**: Users can set reminders for tasks.
- **FR-9**: Tasks must be editable and deletable.
- **FR-10**: Users should be able to drag and drop tasks within the Eisenhower matrix (urgent/important matrix).

**2.3 Task Prioritization (Eisenhower Matrix)**
- **FR-11**: Tasks must be categorized into four quadrants:
  - **Q1**: Urgent and Important
  - **Q2**: Not Urgent but Important
  - **Q3**: Urgent but Not Important
  - **Q4**: Neither Urgent nor Important
- **FR-12**: Users can manually move tasks between quadrants.
  
**2.4 Calendar Integration**
- **FR-13**: Users must be able to sync tasks with Google Calendar, Outlook, and other calendar apps.
- **FR-14**: Tasks with due dates must be displayed in a calendar view.
- **FR-15**: Users can set recurring tasks on a weekly or daily basis.

**2.5 Notifications and Reminders**
- **FR-16**: Users must receive push notifications and email reminders for tasks before the deadline.
- **FR-17**: Notifications must be customizable based on user preferences (e.g., 10 minutes before, 1 day before).

**2.6 Task Completion and Analytics**
- **FR-18**: Users must be able to mark tasks as complete.
- **FR-19**: A task completion rate should be displayed, along with trends over a week, month, and year.
- **FR-20**: Analytics on time spent on different task categories (work, personal, etc.).

**2.7 User Profiles and Settings**
- **FR-21**: Users must be able to update their profile information (name, email, profile picture).
- **FR-22**: Users can manage notification settings, language preferences, and theme (dark/light mode).
- **FR-23**: The application must support both dark mode and light mode.

---

#### **3. Non-Functional Requirements**

**3.1 Usability**
- The user interface must be intuitive and easy to use.
- Provide onboarding for new users to understand the Eisenhower matrix.

**3.2 Performance**
- The application should load tasks in under 2 seconds.
- Task creation and updates should be reflected instantly.

**3.3 Security**
- User data must be encrypted in transit and at rest.
- Sensitive data such as passwords must follow security best practices (e.g., hashing).

**3.4 Reliability**
- The application must be available 99.9% of the time.
- Scheduled maintenance windows should be communicated to users.

**3.5 Compatibility**
- The mobile application must be available on both iOS and Android platforms.
- The web version must be compatible with modern browsers (Chrome, Firefox, Safari, Edge).

---

#### **4. Use Cases**

**Use Case 1: User Registration**
- **Primary Actor**: New user
- **Precondition**: The user has not registered before.
- **Main Scenario**: 
  1. The user opens the app and selects "Sign up."
  2. The user provides an email, password, and name.
  3. The system sends a verification email.
  4. The user verifies the email and logs in.
  
**Use Case 2: Create Task**
- **Primary Actor**: Registered user
- **Precondition**: User is logged in.
- **Main Scenario**:
  1. User selects "Create Task."
  2. User enters task title, description, category, and priority level.
  3. User sets a due date and reminder.
  4. Task is saved and appears in the appropriate quadrant of the matrix.

**Use Case 3: Sync with Calendar**
- **Primary Actor**: Registered user
- **Precondition**: User is logged in and has tasks with due dates.
- **Main Scenario**:
  1. User navigates to the calendar settings.
  2. User selects "Sync with Google Calendar."
  3. The app requests Google account permissions.
  4. Tasks with due dates are synced to the user's Google Calendar.

---

#### **5. Wireframes**

##### **5.1 Home Screen**
**Description**: The home screen will feature a dashboard displaying the Eisenhower matrix, task count per quadrant, and a "Create Task" button.

*Wireframe:*

```
------------------------------------------------
|   Welcome, [User]!                           |
|                                              |
|   +-------------------------------------+    |
|   |  Quadrant 1: Urgent & Important     |    |
|   |  [Task 1] [Task 2]                  |    |
|   +-------------------------------------+    |
|                                              |
|   +-------------------------------------+    |
|   |  Quadrant 2: Not Urgent, Important  |    |
|   |  [Task 3] [Task 4]                  |    |
|   +-------------------------------------+    |
|                                              |
|   +-------------------------------------+    |
|   |  Quadrant 3: Urgent, Not Important  |    |
|   |  [Task 5]                           |    |
|   +-------------------------------------+    |
|                                              |
|   +-------------------------------------+    |
|   |  Quadrant 4: Neither Urgent/Imp     |    |
|   |  [Task 6]                           |    |
|   +-------------------------------------+    |
|                                              |
|   [Create Task]  [Calendar]  [Profile]       |
------------------------------------------------
```

##### **5.2 Create Task Screen**
**Description**: This screen allows users to create a new task by providing all necessary details, including priority and reminders.

*Wireframe:*

```
------------------------------------------------
|  Create Task                                 |
|                                              |
|  Task Title:  [_____________________]        |
|  Description: [_____________________]        |
|                                              |
|  Priority:                                   |
|  [Urgent & Important] [Not Urgent, Important]|
|  [Urgent, Not Important] [Neither]           |
|                                              |
|  Category: [Work] [Personal]                 |
|                                              |
|  Due Date: [MM/DD/YYYY]                      |
|  Reminder: [____ Minutes Before]             |
|                                              |
|  [Save Task] [Cancel]                        |
------------------------------------------------
```

##### **5.3 Calendar View**
**Description**: This screen provides a calendar view of tasks based on their due dates.

*Wireframe:*

```
------------------------------------------------
|  Calendar View                               |
|                                              |
|  [October 2024]                              |
|                                              |
|  Sun  Mon  Tue  Wed  Thu  Fri  Sat           |
|   1    2    3    4    5    6    7            |
|   [Task 1]                                   |
|   8    9   10   11   12   13   14            |
|   [Task 2]                                   |
|                                              |
|   [Add Task]   [Sync with Google Calendar]   |
------------------------------------------------
```

##### **5.4 Profile Settings**
**Description**: Users can update their profile, notification preferences, and application themes here.

*Wireframe:*

```
------------------------------------------------
|  Profile Settings                            |
|                                              |
|  Name: [________]                            |
|  Email: [________]                           |
|  Profile Picture: [Upload
