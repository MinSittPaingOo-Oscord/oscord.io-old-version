# Oscord Code Academy

**Online programming education platform** for students in Myanmar and beyond.  
This repository contains an older version of the Oscord.io learning management system.

---

## About

Oscord Code Academy is a full-stack web application that lets students discover programming courses, enroll in batches, access learning materials, leave reviews, and receive certificates. Instructors and admins can manage courses, students, and content through dedicated dashboards.

**Live site (reference):** [oscord.io](https://oscord.io)

---

## Features

### Public / Student
- Modern dark neon-themed homepage with course catalog
- Course details, batches, schedules, and fees (MMK)
- Student registration & login
- Student dashboard (enrolled courses, materials, progress)
- Student reviews & testimonials
- Educational articles / blog (AI, Web Development, Databases, REST API, SSH, Proxy, Cookies, etc.)
- FAQ section
- Contact form
- Certificate generation
- Password recovery

### Instructor
- Instructor login & control panel
- Manage students per course
- View course-specific data
- Password recovery

### Admin
- Full admin dashboard
- Course, batch, student, and content management
- Analytics / charts

---

## Tech Stack

| Layer        | Technology                          |
|--------------|-------------------------------------|
| Backend      | PHP (procedural + mysqli)           |
| Database     | MySQL 8.x                           |
| Frontend     | HTML5, CSS3, Bootstrap 5, Font Awesome |
| UI Style     | Custom dark theme with cyan/magenta neon accents |
| Fonts        | Orbitron, Inter, Times New Roman    |
| Server       | Apache / XAMPP / any PHP-compatible server |

---

## Project Structure

```
oscord.io-old-version-Min-Sitt/
├── index.html                  # Redirects to oscord_home.php
├── oscord_home.php             # Main homepage
├── connectdb.php               # Database connection
├── nav.php / footer.php        # Shared layout components
├── admin_dashboard.php         # Admin panel
├── student_dashboard.php       # Student panel
├── instructor_*.php            # Instructor tools
├── oscord_course.php           # Course listing
├── oscord_batch.php            # Batch management
├── oscord_signUpPage.php       # Registration
├── oscord_login.php            # Login
├── article_*.php               # Blog / learning articles
├── review.php / studentReview.php
├── our_impact.php              # Stats & impact page
├── oscord_faq.php
├── contact.php
├── database/
│   ├── oscord.sql              # Full database dump (sample data)
│   └── readme.md
└── image/                      # Course images & assets
```

---

## Database

The application expects a MySQL database named **`oscord3.0`** (connection is configured in `connectdb.php`).

### Main Tables
- `oscord_course` – Courses (Java, Python, Web Development, Database, etc.)
- `batch` – Course batches with schedule & seats
- `oscord_student` – Student accounts
- `oscord_instructor` – Instructor accounts
- `oscord_studentxcourse` – Enrollments
- `oscord_instructorxcourse` – Instructor assignments
- `oscord_coursedetail` – Detailed course content
- `oscord_vidlec` / `file` / `lecture_link` – Learning materials
- `oscord_studentreview` – Student reviews
- `coursecategory` / `coursexcategory` – Categories

### Setup
1. Create a MySQL database (recommended name: `oscord3.0`).
2. Import the SQL dump:
   ```bash
   mysql -u root -p oscord3.0 < database/oscord.sql
   ```
3. Update credentials in `connectdb.php` if needed.

> **Note:** The SQL dump was originally created for `oscord2.0`. You may need to adjust the database name or create the DB first.

---

## Installation & Local Setup

### Requirements
- PHP 8.0+
- MySQL 8.0+
- Apache (XAMPP / Laragon / WAMP recommended on Windows)

### Steps
1. **Clone or extract** this repository into your web root:
   ```bash
   # Example with XAMPP
   cp -r oscord.io-old-version-Min-Sitt /opt/lampp/htdocs/oscord
   ```

2. **Configure database** – edit `connectdb.php`:
   ```php
   $servername   = "localhost";
   $username     = "root";
   $password     = "your_password";
   $databasename = "oscord3.0";
   $port         = 3306;
   ```

3. **Import database** (see Database section above).

4. **Start services** (Apache + MySQL) and open:
   ```
   http://localhost/oscord/oscord_home.php
   ```
   or
   ```
   http://localhost/oscord/
   ```
   (`index.html` automatically redirects to the homepage).

---

## Sample Courses (from database)

| Course                              | Fee          | Duration          |
|-------------------------------------|--------------|-------------------|
| Java Programming (Basic to Advanced)| 500,000 MMK  | 4–5 months        |
| Python Programming (Basic to Advanced)| 500,000 MMK| 4–5 months        |
| Database Systems and Design (MySQL) | 230,000 MMK  | 3 months          |
| Frontend Web Development            | 290,000 MMK  | 3 months          |
| … and more                          |              |                   |

---

## Security Notes

 This is an **older version** of the platform.  
 Before deploying to production:

- Change the hardcoded database password in `connectdb.php`
- Move credentials to environment variables or a config outside the web root
- Use prepared statements consistently (some pages already do)
- Add CSRF protection and stronger password hashing if not already present
- Restrict direct access to sensitive PHP files

---

## License

This project appears to be proprietary to Oscord Code Academy.  
All rights reserved unless otherwise stated by the original authors.

---

## Credits

- **Oscord Code Academy** – Original platform
- Built with PHP, MySQL, Bootstrap 5
- UI inspired by modern dark / cyberpunk aesthetics

---

*This README was generated for the archived “old version – Min Sitt” snapshot of the Oscord.io project.*
```
