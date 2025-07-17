# 🏛️ DepartmentConnect

**DepartmentConnect** is a full-stack, role-based academic portal for college departments — built to handle academic workflows, student lifecycle, performance tracking, and collaborative communication — all in one beautifully designed platform. It supports **Admin**, **HOD**, **Professors**, **Students**, and **Alumni**, and is available on **web** and as a **mobile app**.

---

## 🚀 Project Overview

A responsive and modern academic portal that helps institutions:
- Manage students across 4 academic years and multiple sections
- Assign professors and subjects dynamically per semester
- Track attendance and evaluate internal performance continuously
- Upload student data and marks via Excel
- Empower students and alumni with dashboards and analytics
- Enable real-time communication across all roles

Built using **React.js**, **React Native**, **Tailwind CSS**, and **MSSQL**, with a shared backend for web and mobile experiences.

---

## 👥 User Roles

| Role       | Capabilities                                                                 |
|------------|-------------------------------------------------------------------------------|
| **Admin**  | Full control. Manage years, classes, students, professors, subjects, and promotions |
| **HOD**    | Same as Admin but scoped to department and semester                           |
| **Professor** | Attendance, internal marks entry, analytics, and student performance views  |
| **Student**   | Attendance dashboard, internal marks, subject-wise faculty view             |
| **Alumni**    | View past records, achievements, participate in discussion groups           |

---

## 🎯 Key Features

### 🛡️ Authentication & Access Control
- Secure JWT-based login
- Role-specific dashboard redirection
- Protected routes using frontend guards

### 🏛️ Department Management
- Create/manage academic Years, Semesters, Sections
- Assign Subjects per semester
- Assign Professors to specific class-subject combinations
- Designate HODs from existing faculty
- Excel-based bulk student uploads
- Year-end student promotion & graduation logic

### 📆 Attendance Management
- Professors can mark attendance only for assigned subjects
- Date + Subject based filter for attendance entry
- Real-time dashboard for attendance percentage (circular meters)
- Alerts for students < 75% attendance

### 📝 Internal Evaluations
- Upload marks for:
  - Mid-1, Mid-2, Mid-3
  - Assignment-1, 2, 3
- Students see full evaluation breakdown in charts
- Professors view class-level performance analytics

### 🧠 Student Dashboard
- Auto-detected semester and subject list
- Assigned faculty info
- Attendance pie chart + test/assignment bar charts
- Notice board with important alerts

### 🎓 Alumni Access
- Persistent academic record visibility
- Access to general and alumni-only group chats
- Achievement upload feature (optional)

### 📊 Visual Analytics
- Circular progress meters (attendance)
- Pie charts (attendance per subject)
- Stacked bar graphs (test scores across attempts)
- Role-specific dashboards with analytics widgets

### 💬 Real-Time Chat System
- Socket.io or Firebase-based group chat
- Section-based, role-based, and global group discussions
- WhatsApp-style interface:
  - Collapsible panel
  - Emoji picker
  - Role badge (Admin, Prof, Student, Alumni)
  - Timestamped messages

### 📱 Web + Mobile App
- Fully mobile-responsive layout with Tailwind CSS
- PWA installable via browser
- Optional React Native app with shared backend
- Touch-friendly UI, offline-ready with service workers

### ⚙️ Extra Features
- Toast alerts for actions (success/error)
- Collapsible sidebar and chat panels
- Loading states and skeleton UIs
- Optional Dark Mode support
- Deep linking & push notifications for mobile (future-ready)

---

## 🎨 UI Theme

| Element    | Color     | Code        |
|------------|-----------|-------------|
| Primary    | Deep Red  | `#8B0000`   |
| Secondary  | Navy Blue | `#001F54`   |
| Accent     | Brown     | `#8B5E3C`   |
| Background | Neutral   | `#F5F5F5`   |

---

## 🛠️ Tech Stack

| Layer       | Technology                           |
|-------------|--------------------------------------|
| Frontend    | React.js + Tailwind CSS              |
| App         | React Native or Progressive Web App  |
| Backend     | Node.js + Express.js or FastAPI      |
| Database    | Microsoft SQL Server (MSSQL)         |
| Charts      | Recharts / Chart.js                  |
| Chat        | Socket.io or Firebase                |
| Auth        | JWT with Role-based Routing          |
| Deployments | Netlify, Railway, Azure App Service  |

---

## 🧱 Database Schema (MSSQL)

```sql
-- Core Tables
Users (user_id, name, email, password, role)
Students (student_id, user_id, year, section)
Professors (prof_id, user_id)
Subjects (subject_id, name, semester)
Classes (class_id, year, section)
Assignments (assignment_id, prof_id, subject_id, class_id)
Attendance (student_id, subject_id, date, status)
Marks (student_id, subject_id, mid1, mid2, mid3, assign1, assign2, assign3)
Announcements (id, title, content, role, created_at)
ChatMessages (msg_id, sender_id, group_id, message, timestamp)
```
