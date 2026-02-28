
EaglesTeam Task Manager – User Guide

Welcome to the Eagles Team task management system. This guide explains all features available to you based on your role. The application helps teams organize tasks, track progress, report issues, and collaborate efficiently.

---

1. Getting Started

1.1 Login

· Open the application in your browser.
· Enter your Username and Password (provided by your administrator).
· Click Log in.

Default credentials (if not changed):

· Admin: admin / Awes123456789@
· Manager: Manager / manager
· Engineer: Engineer / eng

After login, you will see the main dashboard.

1.2 Interface Overview

· Header: Shows your username, role, logout button, and action buttons (Export, Import, Sync, etc., depending on your role).
· Sidebar (hamburger menu on mobile): Contains all navigation sections (Dashboard, Tasks, Issues, etc.). Click any item to switch views.
· Main content area: Displays the selected view (tasks, charts, etc.).

---

2. Common Features for All Users

2.1 Theme Toggle

Click the Theme button (moon icon) in the header to switch between light and dark mode. Your preference is saved.

2.2 Dashboard

The dashboard shows an overview of all tasks:

· Total Tasks, Completed, In Progress, To Do cards.
· A doughnut chart visualising task distribution.
  This view is read-only and gives a quick snapshot.

2.3 Tasks

The Tasks section is the core of the application.

Task List

· All tasks are displayed as cards with: title, status, assigned user, progress, start date, and deadline.
· Filter tabs (All, To Do, In Progress, Done) let you quickly see tasks by status.
· Search bar – type any text to filter tasks by title (case-insensitive).
· User filter (admin/manager only) – select a team member to see only tasks assigned to them.

Creating a New Task

· Click the New Task button.
· Fill in the form:
  · Title (required)
  · Description
  · Status
  · Progress (slider)
  · Assigned To – for engineers, this is fixed to yourself; for admin/manager, you can choose any user.
  · Priority (Low, Medium, High)
  · Start Date, Deadline (optional)
· Click Create Task. The new task appears in the list and is selected for editing.

Viewing and Editing a Task

· Click any task card to open its details (on desktop, details appear in the right panel; on mobile, a full-screen modal opens).
· You can edit all fields directly – changes are saved automatically when you move away.
· Comments – add comments to discuss the task. Type in the box and click Add Comment (desktop) or Send (mobile). All comments are visible to everyone.

Deleting a Task

· In the task detail view, click the Delete button (red outline) and confirm.
  Note: Only users with delete permission (admin/manager) can delete tasks.

Holding a Task

· If a task cannot be progressed, you can put it on hold.
· In the task detail, click Hold.
· Choose hold type:
  · Reassign to another user (hold) – the task will be held for a specific user.
  · General hold – no specific user.
· Enter a reason.
· Click Submit. The task status becomes hold and appears in the Hold Tasks section.
· To release a hold, go to Hold Tasks and click Release on the task.

2.4 Issues

Issues are used to report problems, questions, or suggestions. They can be linked to users by mentioning them.

Viewing Issues

· In the sidebar, click Issues.
· Issues are listed with title, description, creator, date, and mentions. Solved issues have a green background and a checkmark.
· The sidebar badge shows the number of unsolved issues you are involved in (created by you or where you are mentioned).

Creating an Issue

· Click New Issue.
· Enter a Title and Description.
· Mention users – hold Ctrl (or Cmd) and click to select multiple team members who should be notified.
· Click Save. The issue is now visible to everyone.

Editing an Issue

· Only the creator of the issue or users with edit_issue permission can edit.
· Click the Edit button (pencil icon) on the issue card, modify the fields, and save.

Solving / Unsolving an Issue

· If you are the creator, mentioned, or have solve_issue permission, you can toggle the solved status.
· Click Mark Solved (or Mark Unsolved) on the issue card. The badge updates and the sidebar count changes accordingly.

2.5 Hold Tasks

· The Hold Tasks section lists all tasks currently on hold.
· For each task, you see the holder (user or general) and the reason.
· Click Release to move the task back to the main task list (status becomes To Do).

2.6 Team Performance

· Shows overall completion rate and a per-user breakdown of tasks assigned and completed.
· Useful for managers to monitor team workload.

2.7 Gantt Timeline

· Displays tasks with start and end dates as horizontal bars.
· Helps visualize project schedules and overlaps.

2.8 Export Tasks

· Click the Export button in the header.
· If you have export_all permission, you can export all tasks to a CSV file.
· If you only have export_own, you export only tasks assigned to you.
· The CSV file includes all task details and comments.

2.9 Org Chart

· Shows the team hierarchy based on manager assignments.
· Click any user card to see their details (email, role, manager).
· Departments are separated into IT Department (admin role) and Technical Office Department (all other roles).

2.10 Profile

· Click Profile in the sidebar.
· You can update your username, email, and password.
· You must enter your current password to save changes.

---

3. Role-Specific Features

3.1 Engineer

· View tasks – sees only tasks assigned to them (unless they have broader permissions, but by default only own tasks).
· Create tasks – can create new tasks, but the task is automatically assigned to themselves (cannot assign to others).
· Hold tasks – can put tasks (assigned to them) on hold.
· Comments – can add comments to any task they can view.
· Issues – can create issues, edit own issues, and toggle solved if mentioned or creator.
· Export – can export only their own tasks.

3.2 Manager

· Full task management: create, edit, delete, assign tasks to any user.
· Can hold any task.
· User filter – can filter tasks by any team member.
· Import tasks – can upload CSV files to bulk add/update tasks (see section 4.1).
· Issues – full control (create, edit any, solve any).
· Team Performance and Gantt views available.
· Export – can export all tasks.
· User and role management are not available to managers.

3.3 Admin

· All manager features, plus:
· User Management – add, edit, delete users; assign roles and managers.
· Role Management – create custom roles and set granular permissions.
· System Update – view version info and reset all data to defaults (dangerous – use with caution).
· Sync with file system – set a sync folder, manually sync, backup, and restore data (see section 4.2).
· Import tasks – same as manager.
· All permissions are granted by default.

---

4. Advanced Features (Admin Only)

4.1 Import Tasks from CSV

Admins and managers can import tasks in bulk using a CSV file.

· Click the Import button in the header.
· Select a CSV file with the following columns (in order):
  ```
  ID,Title,Description,Status,Progress,AssignedTo,Priority,Start,Deadline,Created
  ```
  · ID – optional; if provided and matches an existing task, that task will be updated. If omitted or new, a new task is created.
  · AssignedTo – must be the username of an existing user (case-sensitive).
  · Status – todo, in-progress, or done.
  · Progress – number 0–100.
  · Priority – low, medium, high.
  · Start, Deadline, Created – dates in YYYY-MM-DD format (Created is a timestamp; if missing, current time is used).
· After upload, you'll see a summary of added/updated tasks.

4.2 File System Sync (Browser with File System Access API)

Admin can synchronize data with a local encrypted file for sharing across devices.

· Set Sync Folder: Click Set Sync and choose a folder on your computer. A file named tasks.enc will be created.
· Sync Now: After setting the folder, click Sync to reload data from the file (useful if another user has updated it).
· Backup: Downloads a full JSON backup of all data.
· Restore: Upload a previously downloaded JSON backup to replace current data.

Note: This feature requires a modern browser (Chrome, Edge) that supports the File System Access API. It is optional and not required for normal operation.

4.3 User Management

· Go to Manage Users in the sidebar.
· Click Add User to create a new account.
· Edit or delete existing users.
· When editing, you can set a Manager (the person this user reports to). This defines the org chart hierarchy.
· Deleting a user will unassign them from any tasks.

4.4 Role Management

· Go to Manage Roles.
· Create a new role or edit existing ones.
· Assign permissions by checking the boxes. Permissions control what actions users with that role can perform.
· The admin role (r1) cannot be deleted.

4.5 System Update

· Displays current version.
· Clear All Data – resets the entire application to default tasks, users, and roles. Use with extreme caution – all your data will be lost.

---

5. Mobile Experience

The application is fully responsive. On small screens:

· The sidebar becomes a hamburger menu (top‑left).
· Task list and detail view are separate: tapping a task opens a full-screen overlay with all details.
· Use the Back to list button or close (×) to return.
· Filters and search are stacked for easy thumb access.

---

6. Troubleshooting

· I cannot see any tasks: Check your role – engineers see only tasks assigned to them. If none are assigned, the list will be empty.
· I cannot delete a user: Make sure they are not assigned to any tasks. Reassign those tasks first.
· Import fails: Verify that the CSV uses the correct column order and that usernames match exactly.
· Sync folder not working: Your browser may not support the File System Access API. Use Chrome or Edge, or rely on backup/restore.

For further assistance, contact your system administrator.

---

Document version 1.0 – March 2026
