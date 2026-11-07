# 🔐 SECUREX – Police-Citizen Security and Household Monitoring Management System

<p align="center">
  <strong>A Smart Digital Platform for Household Security and Police-Citizen Coordination</strong>
</p>

## 📌 Project Overview

**SECUREX** is a full-stack web application designed to improve household security management and strengthen coordination between citizens and police authorities.

The platform provides a centralized digital system where citizens can register their accounts, submit household information and request Police Watch services when their homes are unattended.

Police officers can review citizen registrations according to their assigned district and police station jurisdiction. Administrators can manage officer accounts, service coverage, citizen records and important administrative activities.

SECUREX focuses on secure authentication, organized information management, transparency and efficient handling of household security requests.

## 🎯 Project Objectives

- Develop a digital platform for household security management.
- Improve coordination between citizens and police authorities.
- Provide online citizen registration and household information submission.
- Enable citizens to submit Police Watch requests.
- Provide jurisdiction-based access to police officers.
- Allow administrators to manage officers and service coverage.
- Maintain registration decisions and administrative audit history.
- Protect sensitive information through secure authentication and access control.
- Build a foundation for future AI-based security services.

## ✨ Key Features

### 👤 1. Citizen Module

- Citizen account registration.
- Secure citizen login.
- Household information submission.
- District and town selection.
- Police Watch request submission.
- Optional Police Watch start and end date/time.
- Registration status tracking.
- View registration decisions and dismissal reasons.

### 👮 2. Police Officer Module

- Secure officer login.
- Officer dashboard.
- View citizen registrations within assigned jurisdiction.
- District-based and police-station-based access restrictions.
- Review citizen information.
- Approve or reject registrations.
- Maintain registration decision history.

### 🛡️ 3. Administrator Module

- Secure administrator login.
- Officer account creation and management.
- Officer account disabling and reactivation.
- Administrative access control.
- Service coverage management.
- Citizen Watch Cases management.
- District and town-based filtering.
- Citizen record review and dismissal.
- Audit history management.

### 🔒 4. Security Features

- Separate citizen and staff authentication.
- Encrypted HTTP-only session cookies.
- Role-based access control (RBAC).
- Server-side permission validation.
- Protected administrator and officer routes.
- Secure staff account management.
- Session revocation when staff access is disabled.
- Audit history for important administrative activities.

### 📍 5. Location and Jurisdiction Management

- Karnataka state location catalog.
- 31 district selections.
- 219 district-dependent town and taluk-headquarters entries.
- Administrator-maintained police service coverage.
- District and police station matching for officer access.

*Note: The location catalog is not an exhaustive village directory. Available geographic locations do not automatically indicate police service coverage.*

## 🏗️ System Architecture

SECUREX follows a full-stack web application architecture.

```text
              CITIZEN / OFFICER / ADMIN
                         |
                         v
                 REACT FRONTEND
                         |
                         v
                TANSTACK START
                         |
              SERVER FUNCTIONS
                         |
             AUTHENTICATION & ACCESS
                         |
                         v
                 DRIZZLE ORM
                         |
                         v
                  POSTGRESQL
                         |
                         v
                  SUPABASE
```

The frontend provides separate interfaces for citizens, officers and administrators. Server-side functions handle authentication, permission validation and application operations. Database operations are managed using Drizzle ORM and PostgreSQL.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| React 19 | Frontend development |
| TypeScript | Type-safe programming |
| TanStack Start | Application routing and server-side functionality |
| Tailwind CSS | Responsive user interface |
| Supabase | Database services |
| PostgreSQL | Relational database |
| Drizzle ORM | Database operations |
| Vitest | Application testing |
| Git | Version control |
| GitHub | Source-code hosting |
| Lovable | Development environment integration |

## 🔄 Working Principle

The general workflow of SECUREX is:

1. Citizen opens the SECUREX web application.
2. Citizen creates an account and signs in.
3. Citizen submits household information.
4. Citizen provides an optional Police Watch period.
5. The application stores the submitted information.
6. An authorized police officer reviews the registration according to assigned jurisdiction.
7. The officer makes an approval or rejection decision.
8. The citizen can track the registration status.
9. The administrator manages officer accounts, service coverage and administrative records.

## 🔐 Security Architecture

Security is an important part of SECUREX because the application handles sensitive citizen and staff information.

The application uses separate encrypted HTTP-only sessions for citizens and staff. Staff accounts are maintained within the application's PostgreSQL database and use separate roles.

Every private server-side operation validates the session and permissions before allowing access. Officer registration reviews also require matching district and police station assignments.

Administrative actions such as account changes and registration dismissals maintain audit history. This helps preserve accountability and prevents important records from being silently deleted.

## 📂 Project Structure

The project uses a TanStack Start application structure. Important configuration and project files include:

```text
SECUREX/
│
├── src/
│   ├── routes/
│   ├── components/
│   ├── server.ts
│   └── ...
│
├── drizzle/
│   ├── schema.ts
│   └── migrations/
│
├── scripts/
│   └── bootstrap-admin.ts
│
├── public/
│
├── package.json
├── tsconfig.json
├── vite.config.ts
├── drizzle.config.ts
├── README.md
└── .env
```

*This is a high-level structure showing important project directories and configuration files. Individual source files may vary.*

## ⚙️ Installation and Setup

Follow these steps to run SECUREX locally.

### Prerequisites

Install the following tools:

- Node.js
- npm
- Git
- Visual Studio Code
- Supabase project and PostgreSQL database access

### Step 1: Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### Step 2: Open the Project Folder

```bash
cd SECUREX
```

Use the actual repository folder name if it is different.

### Step 3: Install Dependencies

```bash
npm install
```

### Step 4: Configure Environment Variables

Create a local `.env` file and configure the database connection and other environment values required by the application.

The database migration configuration uses:

```env
LOVABLE_DB_MIGRATION_URL=your_database_connection_string
```

Add any additional application-specific variables required by the source code and deployment environment.

**Important:** Never upload real database credentials, private keys, administrator passwords or other secrets to GitHub. Keep `.env` out of version control.

### Step 5: Start the Development Server

```bash
npm run dev
```

Open the local URL displayed in your terminal to access the application.

## 🧪 Testing

SECUREX uses Vitest for application testing.

Testing is important for verifying:

- Authentication and session handling.
- Role-based access permissions.
- Citizen registration workflows.
- Jurisdiction-based access restrictions.
- Administrative operations.
- Registration decision history.
- Responsive interface behaviour.

Use the test script configured in `package.json` to run the test suite.

## 🚀 Future Enhancements

SECUREX has several opportunities for future development.

### 🤖 Artificial Intelligence Features

1. **AI Security Chatbot:** Provides automated assistance to citizens.
2. **AI Crime Pattern Analysis:** Analyzes historical crime data to identify patterns and frequently affected areas.
3. **Smart Household Risk Assessment:** Provides household safety recommendations.
4. **AI Document Verification:** Uses OCR and AI to extract and check uploaded document information.
5. **AI Incident Report Summarization:** Summarizes incident descriptions to help officers review information.

### 🚨 Emergency and QRT Features

1. Emergency alert system.
2. Quick Response Team (QRT) assignment.
3. Live location sharing during emergencies.
4. Real-time emergency request tracking.
5. Instant notifications to assigned officers.

### 🌐 Additional Enhancements

- Forgot Password functionality with email OTP verification.
- Real-time notifications.
- Android and iOS mobile application.
- Multilingual support.
- GPS-based location services.
- Advanced administrative analytics.
- Multi-factor authentication.
- Citizen correction and resubmission workflow.

*All features listed in this section are proposed enhancements and should not be considered currently implemented.*

## 🎓 Academic Project Information

| Detail | Information |
|---|---|
| Project Name | SECUREX |
| Project Type | Full-Stack Web Application |
| Domain | Web Development and Household Security Management |
| Frontend | React and TypeScript |
| Backend Framework | TanStack Start |
| Database | PostgreSQL / Supabase |
| ORM | Drizzle ORM |
| Styling | Tailwind CSS |
| Testing | Vitest |
| Development Period | Academic Capstone Project |

## 🌟 Project Highlights

- Centralized household security management.
- Separate citizen, officer and administrator workspaces.
- Secure authentication and session management.
- Jurisdiction-based police officer access.
- Digital Police Watch request management.
- Administrative account and service coverage management.
- Audit history and registration status tracking.
- Responsive web application design.

## ⚠️ Important Project Limitations

SECUREX is a software platform for managing household information and Police Watch requests. Saving a Police Watch period does not confirm police deployment, active monitoring or dispatch of officers.

Actual service availability depends on administrator-maintained and verified police station coverage. The application should not be considered an official police emergency response service unless formally integrated and authorized by the relevant police department.

## 👨‍💻 Developer

**Developed as an Academic Capstone Project**

Project: SECUREX  
Domain: Full-Stack Web Development  
Purpose: Digital Household Security Management and Police-Citizen Coordination

## 📜 License

This project is developed for academic and educational purposes. A suitable open-source license can be added if the project is intended for public reuse or distribution.

## 🙌 Acknowledgement

SECUREX demonstrates the practical application of modern web development technologies to a real-world household security management problem. The project provided valuable experience in frontend development, backend functionality, database management, authentication, security and software testing.

**SECUREX – Building a Smarter Digital Connection Between Citizens and Police.**
