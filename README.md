# SMS Cloud — Student Management System

A static, front-end **Student Management System (SMS)** for **Cloud Institute of Engineering**. The project is a multi-role web application with public pages, authentication (login/register), and separate **Admin** and **Student** dashboards. All data is currently static/demo (no backend or database).

---

## Features

### Public (unauthenticated)
- **Landing** — Entry page with steps to use the site (`index.html`).
- **Home** — Institute intro, facilities (faculties, students, hostel, bus), and links to other sections.
- **About** — About the institute, placement info, and company logos.
- **Courses** — List of courses (e.g. CSE, Civil, EEE, ECE, Mechanical) with links and download placeholder.
- **Blogs** — Campus gallery (campus, library, auditorium, hostel, canteen, etc.).
- **Services** — Institute services overview.
- **Contact** — Contact form section, phone, email, map link, and social links (Facebook, Instagram, LinkedIn, WhatsApp).
- **Not Upload** — Placeholder page for “file not uploaded” (e.g. course downloads).

### Authentication
- **Login** — Username/password with client-side validation and role-based redirect (Admin vs Student).
- **Register** — Registration form with validation (username, email, password, confirm password).
- **Forgot password** — Modal for “forgot password” (UI only; no backend).

**Demo login credentials (hardcoded in `assets/js/scriptlogin.js`):**
| Role   | Username | Password |
|--------|----------|----------|
| Admin  | `admin`  | `admin`  |
| Student| `mdk`    | `mdk`    |

### Admin
- **Dashboard** — Overview with student count, attendance, results, timetable, reports.
- **Register List** — List of registered entries with edit links.
- **Register Edit** — Edit registration entry (UI only).
- **Student Details** — View student details.
- **Student Details View** — Detailed view of a student.
- **Attendance** — Attendance management view.
- **Timetable** — Timetable view.
- **Fees** — Fees details.
- **Exam** — Exam details and exam hall allocation.
- **Results** — Result details and link to result view.
- **Reports** — Reports list with view links.
- **Report View** — Individual report view.

### Student
- **Dashboard** — Welcome and quick links (attendance, results, timetable, reports).
- **Student Details** — View own details.
- **Attendance** — View attendance.
- **Timetable** — View timetable.
- **Fees** — Fees overview with “pay now” links.
- **Fees Pay** — Fee payment (card form, UI only).
- **Fees View** — Fee payment view.
- **Exam** — Exam details and link to exam view.
- **Results** — Result details and link to result view.
- **Report** — Reports / enquiry.

### Shared (used by both Admin and Student)
- **Exam View** — Exam/fee payment–style view (e.g. register number, card payment form).
- **Result View** — Result view (register number, name, grades).

---

## Tech Stack

- **HTML5** — Structure and content.
- **CSS3** — Styling (custom stylesheets + Font Awesome + Google Fonts).
- **JavaScript (vanilla)** — Form validation, redirects, clock, UI behavior.
- **Font Awesome 5.15.4** — Icons.
- **Unicons (iconscout)** — Used in admin UI.
- **Google Fonts** — Nunito, Poppins (via CSS).

No build tools, package manager, or server required; runs as static files.

---

## Project Structure

```
SMS-V1/
├── index.html                 # Entry / landing page
├── README.md                  # This file
├── assets/
│   ├── css/
│   │   ├── style.css         # Public pages (home, about, courses, etc.)
│   │   ├── stylelogin.css    # Login & register
│   │   ├── styleadmin.css    # Admin dashboard & pages
│   │   └── styleuser.css     # Student dashboard & pages
│   ├── js/
│   │   ├── script.js         # Public (navbar, contact, courses/blogs UI)
│   │   ├── scriptlogin.js    # Login/register validation, redirects
│   │   ├── scriptadmin.js    # Admin (clock, redirects, exam/result)
│   │   └── scriptuser.js     # Student (clock, redirects, fees, result)
│   └── images/               # Images organized by section
│       ├── icons/            # title-img, tick, card_img, review-img, error_404
│       ├── home/             # front-img, home-1, home-2, home-about, heading-bg
│       ├── about/            # about-1, about-2, company-1…16
│       ├── courses/          # course-1…11
│       ├── blogs/            # blogs-1…9
│       ├── contact/          # contact-img
│       └── misc/             # 1…6.jpg, Education, main-image (placeholders)
├── public/                    # Public marketing/institute pages
│   ├── home.html
│   ├── about.html
│   ├── contact.html
│   ├── blogs.html
│   ├── courses.html
│   ├── services.html
│   └── notupload.html
├── auth/
│   ├── loginpage.html
│   └── registerpage.html
├── admin/                     # Admin-only pages
│   ├── AdminDashboard.html
│   ├── AdminRegisterList.html
│   ├── AdminRegisterEdit.html
│   ├── AdminDetails.html
│   ├── AdminDetailsView.html
│   ├── AdminAttendance.html
│   ├── AdminTimetable.html
│   ├── AdminFees.html
│   ├── AdminExam.html
│   ├── AdminResults.html
│   ├── AdminReport.html
│   └── AdminReportView.html
├── student/                   # Student-only pages
│   ├── StudentDashboard.html
│   ├── StudentDetails.html
│   ├── StudentAttendance.html
│   ├── StudentTimetable.html
│   ├── StudentFees.html
│   ├── StudentFeesPay.html
│   ├── StudentFeesview.html
│   ├── StudentExam.html
│   ├── StudentResults.html
│   └── StudentReport.html
└── shared/                    # Used by both admin and student
    ├── ExamViewPage.html
    └── ResultViewPage.html
```

---

## How to Run

1. **Clone or download** the project.
2. **Open the entry point** in a browser:
   - Double-click `index.html`, or  
   - Serve the project folder with any static server (e.g. Live Server in VS Code, or `npx serve .`).
3. From the landing page, click **“Click Here to go…”** to open **Home**.
4. Use **Login** in the navbar to sign in:
   - **Admin:** `admin` / `admin` → redirects to Admin Dashboard.
   - **Student:** `mdk` / `mdk` → redirects to Student Dashboard.

**Note:** For correct routing of relative links (e.g. `public/home.html`, `auth/loginpage.html`), open the app from the **project root** (e.g. `http://localhost:3000/` or `file:///path/to/SMS-V1/index.html`). Using a local server is recommended to avoid path issues.

---

## Scripts Overview

| File            | Purpose |
|-----------------|--------|
| `script.js`     | Public: mobile menu, contact map/time popups, course/blog visibility toggles. |
| `scriptlogin.js`| Login validation, admin/student redirect, register validation, forgot-password UI, redirect to home. |
| `scriptadmin.js`| Admin: sidebar “Cloud” redirect to login, live clock, redirect to result view, exam hall allocation UI. |
| `scriptuser.js` | Student: same sidebar/clock/result redirect as admin, plus fees/payment and exam UI. |

---

## Current Limitations

- **No backend** — All data is static; no real database or API.
- **Hardcoded credentials** — Only `admin`/`admin` and `mdk`/`mdk` work for login.
- **No persistence** — Registration and form submissions do not save.
- **No security** — Passwords and auth are client-side only; not suitable for production.

---

## Possible Future Enhancements

- Backend (e.g. Node.js, PHP, or Python) with a database for users, attendance, fees, results.
- Real authentication (e.g. JWT, sessions) and role-based access control.
- Replace static tables with data from an API.
- File upload for course materials and reports.
- Email/notification for forgot password and contact form.

---

## License

Use for learning or internal demos. Adjust branding and content as needed for your institute.
