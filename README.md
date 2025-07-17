# 🏛️ DepartmentConnect

A full-stack, role-based academic portal built for college departments. It supports Admin, HOD, Professors, Students, and Alumni, delivering seamless academic operations, performance insights, and community interaction.

---

## 🚀 Project Overview

**DepartmentConnect** is a responsive web + mobile-ready application designed to manage and streamline:

- Class and subject assignment
- Attendance tracking and internal evaluations
- Student onboarding and promotion
- Real-time announcements and group discussions
- Alumni data viewing and interaction

The platform follows a clean UI layout with collapsible sidebars, WhatsApp-style chat, and modular role-based dashboards.

---

## 👥 User Roles

| Role       | Description                                                                 |
|------------|-----------------------------------------------------------------------------|
| **Admin**  | Clerk-level account with full control. Assigns professors, manages classes |
| **HOD**    | Inherits Admin permissions for a semester. Assigned to existing professors |
| **Professor** | Handles attendance, internal marks, and class performance                 |
| **Student**   | Views attendance, marks, faculty info, and participates in discussions   |
| **Alumni**    | Views academic records and joins alumni conversations                     |

---

## 🎯 Features Summary

### ✅ Common
- Fully **mobile-responsive** layout (Tailwind CSS)
- Smooth navigation with collapsible **Sidebar** and **Chat Panel**
- Role-based login and protected dashboard routes
- Unified backend for web and app

### 🏛️ Public Website
- Announcements carousel
- Faculty horizontal scroll
- Events gallery

### 👨‍💼 Admin/HOD
- Create/manage Years, Semesters, Sections
- Assign Subjects and Professors
- Upload students via Excel
- Promote students to next year

### 👨‍🏫 Professors
- Take subject-wise attendance
- Upload Internal Marks (Mid 1/2/3 + Assignment 1/2/3)
- View class analytics (attendance % graphs)

### 👨‍🎓 Students
- View assigned subjects and teachers
- Attendance progress (circular chart)
- Internal marks breakdown (bar/pie chart)

### 🎓 Alumni
- View academic records
- Join global/section chats
- Submit achievements/testimonials (optional)

### 💬 Chat System
- Role-tagged, timestamped group messaging
- Section-level and global discussion groups
- Collapsible chat panel for immersive UX

---

## 🎨 UI Theme

- 🔴 Red: `#8B0000` – Primary Accent (Buttons, Highlights)
- 🔵 Blue: `#001F54` – Header, Nav, Footer
- 🟤 Brown: `#8B5E3C` – Sub-accents, cards
- ⚪ Neutral: `#F5F5F5` – Background

---

## 🛠️ Tech Stack

| Layer       | Technology                           |
|-------------|--------------------------------------|
| Frontend    | React.js + Tailwind CSS              |
| App         | React Native / PWA-ready             |
| Backend     | Node.js + Express.js or FastAPI      |
| Database    | Microsoft SQL Server (MSSQL)         |
| Charts      | Recharts / Chart.js                  |
| Chat        | Socket.io or Firebase                |
| Auth        | JWT with Role-based Routing          |
| Deployments | Netlify, Railway, Azure SQL          |

---

## 📦 Phase-Wise Implementation

### 🔹 Phase 1: Foundation
- Homepage + Login UI
- Role-based routing
- Basic dashboard scaffolds
- Sidebar & ChatPanel collapsible layouts

### 🔹 Phase 2: Functional Dashboards
- Attendance form + circular charts
- Marks entry and student views
- Excel upload for admin
- Role-specific widgets and charts

### 🔹 Phase 3: Chat & Mobile App
- WhatsApp-style real-time chat
- Role badges, emoji picker
- Installable PWA/mobile-friendly layout
- Year-end promotions and dark mode (optional)

---

## 🧱 Database Structure (MSSQL)

```sql
-- Key Tables
Users (user_id, name, email, password, role)
Students (student_id, user_id, year, section)
Professors (prof_id, user_id)
Subjects (subject_id, name, sem)
Classes (class_id, year, section)
Assignments (prof_id, subject_id, class_id)
Attendance (student_id, subject_id, date, status)
Marks (student_id, subject_id, mid1, mid2, mid3, assign1, assign2, assign3)
Announcements (id, title, content, role, created_at)
ChatMessages (msg_id, sender_id, group_id, message, timestamp)
```
