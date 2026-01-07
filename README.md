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

---

## 🚀 Getting Started

### 1️⃣ Requirements
- **.NET 8 SDK**
- **dotnet-ef** tool

Install EF Core CLI (if not installed):
```bash
dotnet tool install --global dotnet-ef


dotnet restore
dotnet ef migrations add InitialCreate
dotnet ef database update
dotnet run

👑 Default Roles (seeded)
	•	Admin
	•	Student
	•	Lecturer

Admin account is created via SeedData (for development only).
Credentials are not shown in UI.


🔒 Security Notes
	•	Automatic logout after 10 minutes of inactivity
	•	Cookies configured with:
	•	HttpOnly
	•	SameSite=Lax
	•	Cache disabled for authenticated pages
	•	Browser back-button login illusion fixed (no-store + JS pageshow reload)

⸻

🧠 Design Decisions
	•	Groups are the central unit:
	•	Students → Group
	•	Subjects → Group
	•	Enrollment handled automatically
	•	Avoided nested HTML forms (stable bulk & single operations)
	•	Simple, readable EF Core relationships
	•	UI optimized for dark mode first

⸻

🛣 Possible Extensions
	•	Grades & exams
	•	Lecturer self-management
	•	Student self-enrollment (with rules)
	•	Notifications
	•	REST API
	•	React / Blazor frontend

⸻

📜 License

This project is for educational purposes.
Feel free to fork, modify and experiment.

⸻

👋 Author

Built as a learning project to understand:
	•	ASP.NET Core MVC
	•	Identity & security
	•	EF Core relationships
	•	real-world admin workflows
