# DevUniApp
Modern ASP.NET Core MVC university app with Identity, role-based access, student groups, subjects, calendar and admin tools.
# 🎓 University Management System (ASP.NET Core MVC)

Modern university management system built with **ASP.NET Core MVC**, **Entity Framework Core** and **ASP.NET Identity**.  
The application supports role-based access, student groups, subjects, scheduling and an admin panel with a clean glass-style UI.

---

## ✨ Features

### 🔐 Authentication & Authorization
- ASP.NET Identity (login, registration, logout)
- Role-based access:
  - **Admin**
  - **Student**
  - **Lecturer**
- Secure cookies with automatic logout after inactivity
- Protection against browser back-button login cache (no-store + bfcache fix)

### 👨‍🎓 Students & Groups
- Student profiles linked to Identity users
- Student groups (e.g. `INF2-B_26/27`)
- Admin panel to:
  - create groups
  - assign students to groups (single or bulk assignment)

### 📚 Subjects & Enrollment
- Subjects created by Admin
- Subjects assigned to groups
- Automatic enrollment of all students in a group to a subject
- Lecturer assignment to subjects

### 📅 Calendar / Classes
- Class scheduling per subject
- Calendar view for logged-in users
- Role-based visibility (students see their classes, admin manages all)

### 🛠 Admin Panel
- Manage:
  - users & roles
  - student groups
  - subjects
  - group–subject relations
  - scheduled classes
- Bulk operations (group assignments)
- Clean and readable admin UI

### 🎨 UI
- Modern **glass / dark UI**
- Bootstrap 5
- Responsive layout
- No white Bootstrap tables in dark mode 😉

---

## 🧱 Tech Stack

- **ASP.NET Core MVC (.NET 8)**
- **Entity Framework Core**
- **SQLite** (easy local setup)
- **ASP.NET Identity**
- **Bootstrap 5**
- **Razor Pages (Identity UI)**

---

## 📂 Project Structure (simplified)
University/
│
├── Controllers/
│   ├── AdminGroupsController.cs
│   ├── AdminSubjectsController.cs
│   ├── AdminLecturesController.cs
│   └── …
│
├── Models/
│   ├── ApplicationUser.cs
│   ├── Student.cs
│   ├── Lecturer.cs
│   ├── StudentGroup.cs
│   ├── Subject.cs
│   └── …
│
├── Data/
│   ├── UnivercityDbContext.cs
│   └── SeedData.cs
│
├── Views/
│   ├── AdminGroups/
│   ├── AdminSubjects/
│   ├── AdminLectures/
│   └── Shared/_Layout.cshtml
│
├── Program.cs
└── appsettings.json
