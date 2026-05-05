# 🎓 Coaching Center Management System

A complete, production-ready coaching center management platform with student admission, fee tracking, class scheduling, and comprehensive admin controls.

---

## 📋 Features Overview

### 🟢 **Public Features**
- ✅ Home page with coaching info, teachers, toppers, success rate
- ✅ Apply for admission with auto Student ID generation
- ✅ Role-based login (Student/Teacher)
- ✅ Instagram popup integration
- ✅ Multi-language support (English/Hindi/Punjabi)
- ✅ Dark mode theme

### 🔵 **Student Panel** (15+ Features)
- ✅ Dashboard with class timing & announcements
- ✅ Class schedule with subject-wise timing
- ✅ Subject list management
- ✅ Announcements (read-only)
- ✅ Academic tasks with deadline tracking
- ✅ Video library (subject-wise)
- ✅ Notes section (subject → chapter → link)
- ✅ Fee payment tracking with screenshot upload
- ✅ Full profile view (readonly)
- ✅ Profile update requests (1-time approval)
- ✅ Settings (password change, language, logout)
- ✅ Performance reports and analytics
- ✅ Activity history
- ✅ Attendance tracking
- ✅ Bookmark important notes/videos

### 🔴 **Teacher/Admin Panel** (20+ Features)
- ✅ Dashboard with statistics
- ✅ Admission request management (Approve/Deny)
- ✅ Student management (Edit, Delete, Reset Password)
- ✅ Fee request verification (Chat-like interface)
- ✅ Class & Subject management
- ✅ Schedule management (No time conflicts)
- ✅ Notes management (Subject → Chapter → Link)
- ✅ Video management (Upload/Delete/Control homepage)
- ✅ Announcement management
- ✅ Attendance marking system
- ✅ Performance analytics
- ✅ Bulk operations (Approve multiple admissions, Send mass announcements)
- ✅ Data export (CSV/Excel)
- ✅ Admin settings (Coaching name, logo, teachers info)
- ✅ Homepage content control
- ✅ Feature toggle system
- ✅ Activity logs
- ✅ Backup system
- ✅ Role management (Sub-teachers with limited access)
- ✅ Maintenance mode

---

## 🏗️ Project Architecture

```
cohing_canter_managment/
├── backend/
│   ├── config/
│   │   ├── database.js
│   │   ├── constants.js
│   │   └── logger.js
│   ├── models/
│   │   ├── Student.js
│   │   ├── Teacher.js
│   │   ├── AdmissionRequest.js
│   │   ├── FeeRequest.js
│   │   ├── Subject.js
│   │   ├── Schedule.js
│   │   ├── Notes.js
│   │   ├── Video.js
│   │   ├── Announcement.js
│   │   ├── Task.js
│   │   ├── Attendance.js
│   │   ├── ActivityLog.js
│   │   ├── AdminSettings.js
│   │   └── SubTeacher.js
│   ├── routes/
│   │   ├── auth.js
│   │   ├── public.js
│   │   ├── student.js
│   │   ├── teacher.js
│   │   └── admin.js
│   ├── middleware/
│   │   ├── auth.js
│   │   ├── errorHandler.js
│   │   ├── validation.js
│   │   ├── fileUpload.js
│   │   ├── rateLimit.js
│   │   └── sessionTimeout.js
│   ├── utils/
│   │   ├── idGenerator.js
│   │   ├── encryption.js
│   │   ├── validators.js
│   │   ├── fileHandler.js
│   │   └── cronJobs.js
│   ├── services/
│   │   ├── admissionService.js
│   │   ├── studentService.js
│   │   ├── feeService.js
│   │   ├── contentService.js
│   │   └── analyticsService.js
│   ├── controllers/
│   │   ├── authController.js
│   │   ├── studentController.js
│   │   ├── teacherController.js
│   │   ├── adminController.js
│   │   └── publicController.js
│   ├── server.js
│   ├── .env.example
│   └── package.json
│
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   │   ├── common/
│   │   │   │   ├── Header.jsx
│   │   │   │   ├── Sidebar.jsx
│   │   │   │   ├── Footer.jsx
│   │   │   │   ├── Modal.jsx
│   │   │   │   ├── Toast.jsx
│   │   │   │   └── Loader.jsx
│   │   │   ├── public/
│   │   │   │   ├── HomePage.jsx
│   │   │   │   ├── LoginPage.jsx
│   │   │   │   ├── ApplyAdmissionPage.jsx
│   │   │   │   └── InstagramPopup.jsx
│   │   │   ├── student/
│   │   │   │   ├── StudentDashboard.jsx
│   │   │   │   ├── ClassTiming.jsx
│   │   │   │   ├── Subjects.jsx
│   │   │   │   ├── Announcements.jsx
│   │   │   │   ├── AcademicTasks.jsx
│   │   │   │   ├── Videos.jsx
│   │   │   │   ├── Notes.jsx
│   │   │   │   ├── FeeSection.jsx
│   │   │   │   ├── Profile.jsx
│   │   │   │   ├── ProfileUpdateRequest.jsx
│   │   │   │   ├── Settings.jsx
│   │   │   │   ├── Reports.jsx
│   │   │   │   ├── Attendance.jsx
│   │   │   │   └── ActivityHistory.jsx
│   │   │   └── teacher/
│   │   │       ├── TeacherDashboard.jsx
│   │   │       ├── AdmissionManagement.jsx
│   │   │       ├── StudentManagement.jsx
│   │   │       ├── FeeRequestPanel.jsx
│   │   │       ├── ClassSubjectManagement.jsx
│   │   │       ├── ScheduleManagement.jsx
│   │   │       ├── NotesManagement.jsx
│   │   │       ├── VideoManagement.jsx
│   │   │       ├── AnnouncementManagement.jsx
│   │   │       ├── AttendanceMarking.jsx
│   │   │       ├── AdminSettings.jsx
│   │   │       ├── ActivityLogs.jsx
│   │   │       ├── DataExport.jsx
│   │   │       ├── TeacherSettings.jsx
│   │   │       └── SubTeacherManagement.jsx
│   │   ├── pages/
│   │   ├── hooks/
│   │   │   ├── useAuth.js
│   │   │   ├── useFetch.js
│   │   │   ├── useForm.js
│   │   │   └── useNotification.js
│   │   ├── services/
│   │   │   ├── apiService.js
│   │   │   ├── authService.js
│   │   │   ├── studentService.js
│   │   │   ├── teacherService.js
│   │   │   └── publicService.js
│   │   ├── context/
│   │   │   ├── AuthContext.jsx
│   │   │   ├── ThemeContext.jsx
│   │   │   └── LanguageContext.jsx
│   │   ├── styles/
│   │   │   ├── index.css
│   │   │   ├── variables.css
│   │   │   ├── responsive.css
│   │   │   └── darkMode.css
│   │   ├── App.jsx
│   │   └── index.js
│   ├── public/
│   │   └── index.html
│   ├── .env.example
│   └── package.json
│
├── docs/
│   ├── DATABASE_SCHEMA.md
│   ├── API_DOCUMENTATION.md
│   ├── SETUP_GUIDE.md
│   ├── DEPLOYMENT_GUIDE.md
│   ├── SECURITY_GUIDELINES.md
│   └── CONTRIBUTING.md
│
└── docker-compose.yml
```

---

## 🛡️ Security Features

✅ **Password Protection**
- Minimum 8 characters with numbers & letters
- Hash encryption (bcrypt)
- Account lock after 5 failed attempts (15 min)

✅ **Authentication**
- JWT token-based authentication
- Refresh token mechanism
- Role-based access control (RBAC)

✅ **Session Management**
- Auto logout after 30 min inactivity
- Prevent multiple device login (optional)
- Activity logging

✅ **File Security**
- Image-only file uploads (jpg/png)
- Max 2MB file size
- Random filename generation
- Store outside public folder

✅ **Data Protection**
- Soft delete (no permanent removal)
- Audit trails for all actions
- Data validation on both frontend & backend

✅ **Automation Rules**
- Fee screenshot auto-delete after 10 days
- Old records auto-delete after 1 year
- Daily database backups

---

## 🔐 Default Credentials

### Teacher Login
```
Teacher ID: 12516775
Password: Teacher123
```

---

## 🚀 Quick Start

### Prerequisites
- Node.js (v14+)
- MongoDB (local or cloud)
- npm or yarn

### Backend Setup
```bash
cd backend
npm install
cp .env.example .env
# Edit .env with your MongoDB URI
npm start
```

### Frontend Setup
```bash
cd frontend
npm install
cp .env.example .env
# Edit .env with your backend API URL
npm start
```

---

## 📊 Database Models

1. **Student** - Enrolled students
2. **Teacher** - Admin/staff accounts
3. **AdmissionRequest** - Pending student applications
4. **FeeRequest** - Payment tracking
5. **Subject** - Course subjects
6. **Schedule** - Class timings
7. **Notes** - Study materials
8. **Video** - Learning videos
9. **Announcement** - Notices & updates
10. **Task** - Homework/assignments
11. **Attendance** - Class attendance records
12. **ActivityLog** - User activity tracking
13. **AdminSettings** - System configuration
14. **SubTeacher** - Limited-access staff

---

## 📝 API Endpoints Overview

### Auth Routes
- `POST /api/auth/login` - User login
- `POST /api/auth/logout` - User logout
- `POST /api/auth/refresh-token` - Refresh JWT token
- `POST /api/auth/change-password` - Change password

### Student Routes
- `GET /api/student/dashboard` - Dashboard data
- `GET /api/student/profile` - Student profile
- `POST /api/student/fee-request` - Submit fee request
- `GET /api/student/classes` - Class schedule
- `GET /api/student/notes` - Study materials
- And 15+ more endpoints...

### Teacher Routes
- `GET /api/teacher/dashboard` - Teacher dashboard
- `GET /api/teacher/admissions` - Pending admissions
- `POST /api/teacher/admissions/:id/approve` - Approve student
- `GET /api/teacher/fee-requests` - View fee requests
- `POST /api/teacher/content/notes` - Add notes
- And 20+ more endpoints...

### Admin Routes
- `GET /api/admin/settings` - Admin configuration
- `POST /api/admin/settings/update` - Update settings
- `GET /api/admin/activity-logs` - Activity logs
- `POST /api/admin/backup` - Trigger backup
- And 10+ more endpoints...

---

## 🎨 Features Highlights

### Smart Dashboard
- Real-time statistics
- Today's class highlights
- Pending tasks overview
- Fee due alerts

### Advanced Fee System
- Fee status tracking (Paid/Pending/Overdue)
- Auto reminders before due date
- Duplicate payment protection
- Chat-like payment verification interface

### Student Analytics
- Mark progress graphs
- Subject-wise performance
- Attendance percentage
- Weak subject detection

### Admin Controls
- Feature toggle system
- Custom branding options
- Maintenance mode
- Data import/export
- Role-based permissions

---

## 🔄 Automation & Scheduled Tasks

✅ Screenshot auto-deletion (10 days)
✅ Old data cleanup (1 year)
✅ Daily database backups
✅ Fee reminders (configurable)
✅ Activity log archival

---

## 📱 Responsive Design

- ✅ Mobile-first approach
- ✅ Tablet-optimized layouts
- ✅ Desktop full experience
- ✅ PWA ready (offline support)

---

## 🌐 Multi-language Support

- 🇬🇧 English
- 🇮🇳 Hindi
- 🇮🇳 Punjabi

---

## 🎯 Future Enhancements

- Mobile app (React Native)
- Payment gateway integration (Razorpay/UPI)
- AI-powered recommendations
- Video conferencing integration
- SMS/Email notifications
- Parent portal access
- Performance prediction using ML

---

## 📧 Support & Contact

For issues, questions, or suggestions, please create an issue on GitHub.

---

## 📄 License

MIT License - Feel free to use this project.

---

**Made with ❤️ for coaching centers**
