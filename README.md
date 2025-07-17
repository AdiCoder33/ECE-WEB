# 🏛️ DepartmentConnect

**DepartmentConnect** is a full-stack, role-based academic portal for college departments — built to streamline academic workflows, student lifecycle management, performance analytics, and real-time collaboration. Supports roles: **Admin**, **HOD**, **Professors**, **Students**, and **Alumni** with seamless experience on both **web** and **mobile (PWA)**.

---

## 🚀 Project Overview

A responsive academic platform designed using **Next.js 14 App Router**, featuring:
- Centralized class/subject/student control
- Attendance + internal marks management
- Excel-based onboarding and year promotions
- Role-specific dashboards and analytics
- Real-time chat for section/global discussions
- Alumni visibility and community extension
- PWA-ready and mobile-first design

---

## 👥 User Roles

| Role       | Permissions                                                                 |
|------------|------------------------------------------------------------------------------|
| **Admin**  | Global control: users, years, subjects, professors, classes, promotions      |
| **HOD**    | Inherits Admin rights within a semester or branch                            |
| **Professor** | View and manage attendance, internal assessments for assigned classes      |
| **Student**   | Track academic performance, view assigned subjects and announcements       |
| **Alumni**    | Access past data and join community discussions                            |

---

## 🎯 Key Features

### 🛡️ Authentication & Access
- JWT-based secure login system
- Role-aware routing with dynamic redirects
- Session-based access using `next-auth` or `iron-session`

### 🏛️ Department & Class Management
- Year/Sem/Section creation
- Subject and professor assignment
- HOD assignment from professor pool
- Excel sheet upload for bulk student addition
- Section-wise promotion logic (auto-graduation)

### 📆 Attendance & Evaluation
- Daily subject-wise attendance by assigned professors
- Attendance dashboard with circular charts and warnings
- Mid 1/2/3 and Assignment 1/2/3 internal mark uploads
- Student dashboard with bar/pie chart analytics

### 🧠 Dashboards per Role
- Role-based routing using Next.js dynamic segments
- Admin: section control, uploads, announcements
- Professor: performance overview, subject filters
- Student: attendance %, subject-wise performance
- Alumni: records + achievement upload

### 💬 Chat System (Section-wise + Global)
- WebSocket or Firebase-powered real-time chat
- WhatsApp-style layout
- Group/channel list, scrollable messages, emoji picker
- Role-badged and timestamped bubbles

### 📱 Mobile Optimization + PWA
- Tailwind’s mobile-first design
- Collapsible sidebars & chat drawers
- PWA support via `next-pwa` for installable app
- Offline-ready service workers

### 🎨 UI Color Palette
| Element    | Color     | Code        |
|------------|-----------|-------------|
| Primary    | Deep Red  | `#8B0000`   |
| Secondary  | Navy Blue | `#001F54`   |
| Accent     | Brown     | `#8B5E3C`   |
| Background | Neutral   | `#F5F5F5`   |

---

## 🛠️ Tech Stack

| Layer         | Technology                             |
|---------------|----------------------------------------|
| Frontend      | **Next.js 14 (App Router)** + Tailwind CSS |
| App           | PWA + Mobile-First UI                  |
| Backend       | Node.js + Express.js or FastAPI        |
| Database      | Microsoft SQL Server (MSSQL)           |
| Charts        | Recharts / Chart.js                    |
| Realtime Chat | Socket.io / Firebase                   |
| Auth          | NextAuth.js / Iron Session (JWT)       |
| Deployment    | Vercel (Frontend) + Railway/Azure (Backend & DB) |

---

## 🧱 Database Schema (MSSQL)

```sql
-- Core Tables
Users (user_id, name, email, password_hash, role)
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
