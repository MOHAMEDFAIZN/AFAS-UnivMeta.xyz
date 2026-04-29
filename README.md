# 🎓 AFAS — UnivMeta.xyz
### Academic Form Automation System

[![Node.js](https://img.shields.io/badge/Node.js-18.x-339933?style=flat-square&logo=nodedotjs)](https://nodejs.org/)
[![Express.js](https://img.shields.io/badge/Express.js-4.x-000000?style=flat-square&logo=express)](https://expressjs.com/)
[![MySQL](https://img.shields.io/badge/MySQL-2.x-4479A1?style=flat-square&logo=mysql)](https://www.mysql.com/)
[![Puppeteer](https://img.shields.io/badge/Puppeteer-23.x-40B5A4?style=flat-square&logo=googlechrome)](https://pptr.dev/)
[![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4-412991?style=flat-square&logo=openai)](https://openai.com/)
[![Twilio](https://img.shields.io/badge/Twilio-WhatsApp-F22F46?style=flat-square&logo=twilio)](https://www.twilio.com/)
[![License: ISC](https://img.shields.io/badge/License-ISC-blue.svg?style=flat-square)](https://opensource.org/licenses/ISC)
[![Live](https://img.shields.io/badge/Live-univmeta.xyz-28a745?style=flat-square&logo=googlechrome)](https://www.univmeta.xyz)

---

## 📌 Overview

**AFAS (Academic Form Automation System)** is a full-stack web platform developed under the **UnivMeta** initiative to digitize and automate the academic administrative workflows of higher-education institutions. Built for Kalasalingam Academy of Research and Education, AFAS eliminates paper-based form processing by providing role-based digital portals for students, faculty, HODs, and administrators.

Students can apply for **Leave, On-Duty (OD), Bonafide Certificates, Duplicate ID Cards, No-Due Certificates, and Internship approvals** — all from a single dashboard. Faculty and administrators receive instant notifications via **Email and WhatsApp**, review applications online, and trigger automated **PDF certificate generation** upon approval. The system also integrates an **AI-powered chatbot** (GPT-4) to guide users through workflows in real time.

> 🏫 Developed for: **Kalasalingam Academy of Research and Education**
> 🌐 Live at: [https://www.univmeta.xyz](https://www.univmeta.xyz)

---

## ✨ Features

- 🔐 **Role-Based Authentication** — Separate secure login portals for Students, Faculty, HODs, and Administrators using JWT tokens and session management
- 📝 **Multi-Form Application System** — Digital submission of Leave, OD, Bonafide Certificate, No-Due Certificate, Duplicate ID Card, and Internship approval forms
- 📋 **Multi-Level Approval Workflow** — Applications flow from Faculty → HOD → Admin with status tracking at every stage
- 📄 **Automated PDF Certificate Generation** — Approved certificates are generated on-the-fly using Puppeteer and Playwright, with institutional seals and signatures embedded
- 📧 **Email Notifications** — Automated emails via Nodemailer sent to both students and faculty on every status change
- 💬 **WhatsApp Notifications** — Real-time application alerts pushed to faculty via Twilio WhatsApp API
- 🤖 **AI-Powered Chatbot** — GPT-4 integrated assistant with structured FAQ responses for form guidance and status queries
- 📊 **Attendance Tracking** — Per-subject attendance percentage monitoring with automatic log updates when leave/OD is approved
- 📥 **Excel Export** — Admin can export application data (Bonafide, Leave, Event) directly to `.xlsx` using ExcelJS
- 🔔 **In-App Notification System** — Real-time notification feeds for all roles
- 🔑 **Password Management** — Secure change-password flows for Student, Faculty, and Admin with bcrypt hashing
- 🗃️ **Dual Database Architecture** — Separate MySQL databases for application data (`univmeta`) and student academic records (`studentinfo`)
- 📱 **AMP-Enabled Landing Page** — Google AMP-compatible index page for faster mobile loading and improved SEO
- 📈 **Google Analytics Integration** — Built-in G4 analytics tracking (G-GPE7N86WMD) on the landing page
- 🗺️ **SEO-Optimized** — sitemap.xml, robots.txt, Schema.org structured data, and canonical URLs configured
- 👨‍💼 **Developer Credits Page** — Dedicated team page with contributor profiles

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **Runtime** | Node.js |
| **Backend Framework** | Express.js |
| **Templating** | EJS |
| **Database** | MySQL (mysql2) — dual database: `univmeta` + `studentinfo` |
| **Authentication** | JWT (jsonwebtoken), express-session, bcrypt / bcryptjs |
| **PDF Generation** | Puppeteer, Playwright (Chromium) |
| **Email Service** | Nodemailer (SMTP) |
| **WhatsApp API** | Twilio |
| **AI Chatbot** | OpenAI GPT-4 API |
| **Excel Export** | ExcelJS |
| **File Uploads** | Multer |
| **Security** | Helmet.js, CORS, dotenv |
| **HTTP Client** | Axios |
| **Frontend** | HTML5, CSS3, Bootstrap 5, Vanilla JavaScript |
| **Animations** | GSAP (GreenSock) |
| **Icons** | Font Awesome 6 |
| **Fonts** | Google Fonts |
| **AMP** | Google AMP (landing page) |
| **Analytics** | Google Analytics 4 |
| **Hosting** | Microsoft Azure / Custom Domain (univmeta.xyz) |
| **CDN** | Cloudflare |

---

## 🗂️ Project Structure

```
AFAS-UnivMeta.xyz/
│
├── server.js                        # Main Express server — all routes & business logic (3,396 lines)
├── package.json                     # Node.js dependencies and scripts
├── .gitignore
├── robots.txt                       # SEO crawler config
├── sitemap.xml                      # Sitemap for search engine indexing
│
├── public/                          # All static frontend files
│   ├── index.html                   # AMP-enabled landing page (Google Analytics, Schema.org)
│   ├── About.html                   # Platform overview and tech showcase
│   ├── Registration.html            # Student & Faculty registration
│   ├── dash.html                    # General dashboard
│   ├── hoddashboard.html            # HOD portal dashboard
│   ├── Privacy Policy.html
│   ├── Terms of Use.html
│   │
│   ├── Student/                     # Student portal
│   │   ├── login.html               # Student login
│   │   ├── change-password.html
│   │   ├── form.html                # Application form selector
│   │   ├── leave_form.html          # Leave application form
│   │   ├── On Duty Form.html        # OD application form
│   │   ├── Bonafide Form.html       # Bonafide certificate request
│   │   ├── student-application-review.html
│   │   ├── Student Notification.html
│   │   ├── Bonofide Confirmation.html
│   │   ├── OD.Confirmation.html
│   │   ├── Application Forms/
│   │   │   ├── Duplicate Id Form.html
│   │   │   ├── internship.html
│   │   │   └── No Due Form.html
│   │   └── Univmeta Presentations/  # PBL presentation assets
│   │
│   ├── faculty/                     # Faculty portal
│   │   ├── Faculty Login Page.html
│   │   ├── Faculty Dashboard.html
│   │   ├── Applications Review.html # OD/Leave review
│   │   ├── Applications Review Bonafide.html
│   │   ├── Faculty Notifications.html
│   │   ├── facultyleave.html
│   │   ├── facultyevent.html
│   │   ├── facultybonafide.html
│   │   ├── hod-login.html
│   │   ├── change-password.html
│   │   └── dashboard.js
│   │
│   ├── Admin/                       # Admin portal
│   │   ├── Admin Login Page.html
│   │   ├── Admin Dashboard.html
│   │   ├── Applications Review Bonafide.html
│   │   ├── Applications Review Faculty.html
│   │   ├── Student Details.html
│   │   ├── Total Event.html
│   │   ├── Total leave.html
│   │   ├── Notifications.html
│   │   ├── view-applications.html
│   │   ├── view-leave.html
│   │   └── change-password.html
│   │
│   ├── HOD login/                   # HOD review pages
│   │   ├── hodbonofide.html
│   │   └── hodreveiw.html
│   │
│   ├── Attendance System/           # Attendance module
│   │   └── Attendance.html
│   │
│   ├── Developers Details UnivMeta/ # Team/credits page
│   ├── UnivMeta Index Page/         # Landing page assets
│   ├── General Assest/              # Shared images and logos
│   ├── About Images/                # Tech stack logos (SVGs)
│   ├── css/styles.css
│   └── js/print.js
│
├── templates/                       # HTML certificate templates (rendered by Puppeteer)
│   ├── Bonafide Certificate.html
│   ├── OD Certificate.html
│   ├── certificate-template.html
│   ├── email 2.html
│   └── Application Confirmations/
│
└── FrontEnd Assest Images/          # Brand and UI images
```

---

## ⚙️ Installation & Setup

### Prerequisites

- **Node.js** v18 or higher
- **MySQL** v8.0 or higher
- A `.env` file with valid credentials (see below)

### 1. Clone the Repository

```bash
git clone https://github.com/your-username/AFAS-UnivMeta.xyz.git
cd AFAS-UnivMeta.xyz
```

### 2. Install Dependencies

```bash
npm install
```

### 3. Configure Environment Variables

Create a `.env` file in the project root:

```env
# Server
PORT=3078
SESSION_SECRET=your_session_secret

# MySQL — Primary DB (univmeta)
DB_HOST=your_db_host
DB_USER=your_db_user
DB_PASSWORD=your_db_password
DB_NAME=univmeta
DB_PORT=3306

# Email (SMTP)
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password

# Twilio (WhatsApp)
TWILIO_ACCOUNT_SID=your_twilio_sid
TWILIO_AUTH_TOKEN=your_twilio_auth_token
TWILIO_WHATSAPP_NUMBER=whatsapp:+14155238886

# OpenAI
OPENAI_API_KEY=your_openai_api_key

# JWT
JWT_SECRET=your_jwt_secret
```

### 4. Set Up MySQL Databases

Create two databases in MySQL:

```sql
CREATE DATABASE univmeta;
CREATE DATABASE studentinfo;
```

Import your schema files into both databases (tables include `students`, `faculty`, `admin`, `applications`, `attendancedetails`, `attendance_logs`, etc.).

### 5. Start the Server

```bash
node server.js
```

The application will be available at `http://localhost:3078`.

---

## 🚀 Usage

### 👨‍🎓 Student Workflow
1. Register at `/Registration.html` using your student credentials
2. Log in via `/Student/login.html`
3. Navigate to **Application Forms** to apply for Leave, OD, Bonafide, No-Due, Duplicate ID, or Internship
4. Track your application status in real time from the student dashboard
5. Download your approved certificate as a PDF once processed

### 👨‍🏫 Faculty Workflow
1. Log in at `/faculty/Faculty Login Page.html`
2. Receive WhatsApp and email notifications when a student submits an application
3. Review pending applications from the **Faculty Dashboard**
4. Approve or reject applications with remarks
5. Approved applications are forwarded to the HOD/Admin tier automatically

### 🏛️ HOD Workflow
1. Log in via `/faculty/hod-login.html`
2. Review Bonafide and OD applications escalated from faculty
3. Provide final departmental approval before Admin processing

### 🔧 Admin Workflow
1. Log in at `/Admin/Admin Login Page.html`
2. View all applications across the institution from the **Admin Dashboard**
3. Approve Bonafide certificate requests (triggers PDF generation and email)
4. Export application data to Excel for records
5. Manage student registrations and view detailed student profiles

### 🤖 AI Chatbot
- The chatbot is accessible from the landing page and student portal
- Ask about form status, how to apply for specific forms, or platform FAQs
- Powered by OpenAI GPT-4 with a structured FAQ layer for common queries

---

## 📸 Screenshots

> 📌 Add screenshots in a `/screenshots` folder and link them here:

| Page | Preview |
|---|---|
| Landing Page | `screenshots/landing-page.png` |
| Student Dashboard | `screenshots/student-dashboard.png` |
| Faculty Review Panel | `screenshots/faculty-review.png` |
| Admin Dashboard | `screenshots/admin-dashboard.png` |
| Generated Certificate | `screenshots/bonafide-certificate.png` |
| AI Chatbot | `screenshots/chatbot.png` |

---

## 🌐 Live Demo

🔗 **Production URL:** [https://www.univmeta.xyz](https://www.univmeta.xyz)

| Portal | URL |
|---|---|
| Landing Page | [univmeta.xyz](https://www.univmeta.xyz) |
| Student Login | [/Student/login.html](https://www.univmeta.xyz/Student/login.html) |
| Faculty Login | [/faculty/Faculty Login Page.html](https://www.univmeta.xyz/faculty/Faculty%20Login%20Page.html) |
| Admin Login | [/Admin/Admin Login Page.html](https://www.univmeta.xyz/Admin/Admin%20Login%20Page.html) |
| About | [/About.html](https://www.univmeta.xyz/About.html) |

---

## 🧠 Challenges Solved

**1. End-to-End Paperless Workflow**
Replaced entirely manual, paper-based academic form processing with a structured digital approval pipeline spanning Student → Faculty → HOD → Admin.

**2. Real-Time Multi-Channel Notifications**
Integrated both SMTP email (Nodemailer) and WhatsApp (Twilio) to ensure faculty never miss a pending application, regardless of their preferred communication channel.

**3. Dynamic PDF Certificate Generation**
Used headless browser automation (Puppeteer + Playwright/Chromium) to render HTML templates with student data and generate institutionally formatted certificates on-demand — no manual document creation required.

**4. Attendance Reconciliation**
When a leave application is approved, the system automatically updates the `attendance_logs` table in the `studentinfo` database, preventing manual attendance record corrections by faculty.

**5. Dual Database Architecture**
Decoupled application data (`univmeta`) from student academic records (`studentinfo`), allowing independent scaling and access control for different institutional modules.

**6. AI-Guided User Experience**
Integrated OpenAI GPT-4 with a structured FAQ knowledge base so students can get instant, accurate guidance on form procedures without contacting the admin office.

**7. SEO & Performance Optimization**
Implemented Google AMP on the landing page, configured sitemap.xml, robots.txt, canonical URLs, and Schema.org structured data to maximize search engine visibility for an institutional platform.

---

## 🔮 Future Enhancements

- 📱 **Progressive Web App (PWA)** — Offline support and native app-like experience on mobile devices
- 🔔 **Push Notifications** — Browser push notifications for real-time status updates without WhatsApp dependency
- 📊 **Analytics Dashboard** — Visual insights on application volumes, approval rates, and turnaround times for administrators
- 🔒 **Two-Factor Authentication (2FA)** — OTP-based verification for login security
- 🌍 **Multi-Institution Support** — Extend the platform to serve multiple colleges under a single deployment (multi-tenancy)
- 🤖 **LLM Fine-Tuning** — Train a domain-specific model on institutional FAQs for more accurate chatbot responses
- 📋 **Digital Signature Integration** — Replace image-based signatures with cryptographically verifiable digital signatures on certificates
- 🗄️ **MongoDB Migration** — Move from MySQL to MongoDB for unstructured application metadata and improved flexibility
- 🐳 **Docker Containerization** — Package the app for reproducible deployments across environments

---

## 👨‍💻 Author

**Mohamed Faiz N**
BCA — Kalasalingam Academy of Research and Education

[![GitHub](https://img.shields.io/badge/GitHub-MohamedFaizN-181717?style=flat-square&logo=github)](https://github.com/)
[![Email](https://img.shields.io/badge/Email-support@univmeta.xyz-D14836?style=flat-square&logo=gmail)](mailto:support@univmeta.xyz)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0077B5?style=flat-square&logo=linkedin)](https://www.linkedin.com/company/univmeta)

> Co-developed as part of the **UnivMeta** team — see [Developers Page](https://www.univmeta.xyz/Developers%20Details%20UnivMeta/developers.html) for all contributors.

---

## 📄 License

This project is licensed under the **ISC License**.

---

<p align="center">
  Built with ❤️ for smarter campuses — <strong>UnivMeta.xyz</strong>
</p>
