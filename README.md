<<<<<<< HEAD
# 🗳️ Digital Voting System

A **secure, transparent, and user-friendly online voting platform**. It provides **voter authentication, encrypted ballots, one-vote-per-voter enforcement, auditable logs**, and **real-time results**.

---

## ✨ Key Features

* 🔐 **Authentication & Authorization**: Role-based access (VOTER, ADMIN, OFFICER).
* 🛡️ **Ballot Security**: AES-256 encryption at rest; TLS in transit; hash chaining for tamper evidence.
* 🚫 **Duplication Prevention**: Server-side constraints + signed ballot tokens.
* 📊 **Live Results**: Streamed tallies (without revealing individual votes).
* 🧾 **Audit Trail**: Append-only logs (admin actions, election lifecycle, anonymized cast events).
* 📱 **Responsive UI**: Desktop & mobile friendly.
* 🌐 **Multi-Election Support**: Parallel elections, candidate management, time windows.
* 🧩 **Pluggable DB**: MySQL (SQL)

---

## 🗺️ Table of Contents

* [Architecture](#-architecture)
* [Tech Stack](#-tech-stack)
* [Monorepo Structure](#-monorepo-structure)
* [Quick Start](#-quick-start)
* [Configuration](#-configuration)
* [Database Schema](#-database-schema)
* [API Reference](#-api-reference)
* [Security Model](#-security-model)
* [Usage Guide](#-usage-guide)
* [Deployment](#-deployment)
* [Roadmap](#-roadmap)
* [Contributing](#-contributing)
* [FAQ](#-faq)

---

## 🧩 Architecture

```mermaid
flowchart LR
  U[User (Web/Mobile)] --> UI[Frontend (React/HTML/CSS)]
  UI --> API[(Backend API - Node/Express)]
  API --> AUTH[Auth/JWT]
  API --> VOTE[Voting Service]
  API --> RES[Results Service]
  API --> LOG[Audit Logger]
  VOTE --> DB[(DB: MySQL/MongoDB)]
  RES --> DB
  LOG --> ALOG[(Append-only Audit Log)]
```
=======
# 🗳️ Online Voting System

A modern, secure, and user-friendly online voting system built with Node.js, Express, and MySQL. This system provides a complete solution for conducting digital elections with features for both voters and administrators.

![Voting System](https://img.shields.io/badge/Status-Active-brightgreen)
![Node.js](https://img.shields.io/badge/Node.js-18+-green)
![Express](https://img.shields.io/badge/Express-4.21.1-blue)
![MySQL](https://img.shields.io/badge/MySQL-8.0+-orange)
![License](https://img.shields.io/badge/License-ISC-blue)

## ✨ Features

### 🔐 User Features
- **Secure Authentication**: Voter ID and password-based login system
- **User Registration**: Complete voter registration with biometric support
- **Voting Interface**: Intuitive candidate selection and voting process
- **Vote Confirmation**: Real-time confirmation after successful voting
- **User Dashboard**: Personalized dashboard with voter information
- **Support System**: Built-in support and contact form

### 👨‍💼 Admin Features
- **Admin Authentication**: Secure admin login system
- **Candidate Management**: Add new candidates with party symbols
- **Real-time Results**: Live election results and analytics
- **Vote Monitoring**: Track all votes and voter participation
- **Message Management**: Handle user support messages

### 🚀 Technical Features
- **Responsive Design**: Modern, mobile-friendly interface
- **Session Management**: Secure user sessions with Express
- **File Upload**: Support for candidate party symbols
- **AI Integration**: Google Gemini AI assistant for voter support
- **Database Security**: MySQL with prepared statements
- **CORS Support**: Cross-origin resource sharing enabled

## 🏗️ Architecture

```
📁 Online Voting System/
├── 🖥️ Frontend (EJS Templates)
│   ├── User Interface
│   ├── Admin Interface
│   └── Responsive Design
├── 🔧 Backend (Node.js + Express)
│   ├── Authentication System
│   ├── Voting Logic
│   ├── Admin Controls
│   └── API Endpoints
├── 🗄️ Database (MySQL)
│   ├── User Management
│   ├── Candidate Data
│   ├── Voting Records
│   └── Support System
└── 🎨 Assets & Styling
    ├── CSS Styling
    ├── Images
    └── JavaScript
```

## 🛠️ Technology Stack

### Backend
- **Node.js** - JavaScript runtime environment
- **Express.js** - Web application framework
- **MySQL** - Relational database management
- **Multer** - File upload middleware
- **Express-session** - Session management
- **CORS** - Cross-origin resource sharing

### Frontend
- **EJS** - Embedded JavaScript templating
- **HTML5** - Semantic markup
- **CSS3** - Modern styling with gradients and animations
- **JavaScript** - Client-side interactivity

### AI & Integration
- **Google Gemini AI** - AI-powered voter assistance
- **Botpress** - Chatbot integration for support

## 📋 Prerequisites

Before running this project, make sure you have the following installed:

- **Node.js** (v18 or higher)
- **MySQL** (v8.0 or higher)
- **npm** or **yarn** package manager

## 🚀 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd own-voting-project
```

### 2. Install Dependencies
```bash
npm install
```

### 3. Database Setup
1. Create a MySQL database named `voting1`
2. Update database credentials in `connection.js`:
   ```javascript
   const conn = mysql.createConnection({
     host: "localhost",
     user: "root",
     password: "your_password",
     database: "voting1",
     port: 3311
   });
   ```

### 4. Environment Variables
Create a `.env` file in the root directory:
```env
GEMINI_API_KEY=your_gemini_api_key_here
```

### 5. Start the Application
```bash
npm start
```

The application will be available at `http://localhost:3000`

## 📊 Database Schema

### Core Tables
- **users** - Voter information and authentication
- **candidates** - Candidate details and party symbols
- **votes** - Voting records and results
- **admin** - Administrator accounts
- **support** - User support messages

### Key Fields
- Voter ID, names, email, Aadhar number
- Candidate ID, names, party, position, bio
- Vote timestamps and validation
- Admin credentials and permissions

## 🔐 Security Features

- **Session Management**: Secure user sessions with configurable timeouts
- **Input Validation**: Server-side validation for all user inputs
- **SQL Injection Prevention**: Prepared statements for database queries
- **File Upload Security**: Restricted file types and secure storage
- **Authentication**: Multi-factor authentication for admin access

## 🎯 Usage Guide

### For Voters
1. **Register**: Create account with voter ID and personal details
2. **Login**: Access system with credentials
3. **Vote**: Select candidate and confirm vote
4. **Dashboard**: View personal information and voting status

### For Administrators
1. **Login**: Access admin panel with admin credentials
2. **Manage Candidates**: Add new candidates with party symbols
3. **Monitor Results**: View real-time voting statistics
4. **Handle Support**: Respond to user inquiries and messages

## 🌟 Key Features in Detail

### 🗳️ Voting Process
- **Candidate Display**: Shows all candidates with party symbols
- **Vote Validation**: Prevents duplicate voting
- **Real-time Updates**: Immediate vote confirmation
- **Audit Trail**: Complete voting history tracking

### 📊 Results & Analytics
- **Live Results**: Real-time vote counting
- **Winner Calculation**: Automatic winner determination
- **Statistical Analysis**: Vote distribution and trends
- **Export Capabilities**: Data export for reporting

### 🤖 AI Integration
- **Voter Assistance**: AI-powered support system
- **Smart Responses**: Context-aware help and guidance
- **24/7 Support**: Automated assistance availability

## 🔧 Configuration

### Server Configuration
- **Port**: 3000 (configurable)
- **Session Timeout**: 100 minutes
- **File Upload**: `uploads/` directory
- **Static Files**: `public/` directory

### Database Configuration
- **Connection Pool**: Optimized for performance
- **Query Timeout**: Configurable timeout settings
- **Error Handling**: Comprehensive error logging

## 📱 Responsive Design

The application features a modern, responsive design that works seamlessly across:
- **Desktop Computers**
- **Tablets**
- **Mobile Phones**
- **Various screen resolutions**

## 🚀 Performance Features

- **Optimized Queries**: Efficient database operations
- **Static File Serving**: Fast asset delivery
- **Session Caching**: Reduced database load
- **Compressed Responses**: Optimized data transfer

## 🧪 Testing

### Manual Testing
- User registration and authentication
- Voting process validation
- Admin functionality verification
- Cross-browser compatibility

### Automated Testing
- API endpoint validation
- Database connection testing
- Session management verification

## 📈 Future Enhancements

- [ ] **Blockchain Integration** - Enhanced security and transparency
- [ ] **Real-time Notifications** - Push notifications for updates
- [ ] **Advanced Analytics** - Detailed voting patterns and insights
- [ ] **Mobile App** - Native mobile application
- [ ] **Multi-language Support** - Internationalization features
- [ ] **Advanced Security** - Two-factor authentication and encryption

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the **ISC License** - see the [LICENSE](LICENSE) file for details.

## 👥 Team

- **Developers**: Full-stack development team
- **Designers**: UI/UX specialists
- **Testers**: Quality assurance team
- **Project Managers**: Agile development coordination

## 📞 Support

For support and inquiries:
- **Email**: support@votingsystem.com
- **Documentation**: [Project Wiki](wiki-link)
- **Issues**: [GitHub Issues](issues-link)

## 🙏 Acknowledgments

- **Express.js Community** - Web framework support
- **MySQL Team** - Database technology
- **Google AI** - Gemini AI integration
- **Open Source Contributors** - Community support

---

<div align="center">
  <p><strong>Built with ❤️ for secure and transparent digital democracy</strong></p>
  <p>⭐ Star this repository if you find it helpful!</p>
</div>
>>>>>>> 562b015 (Initial commit: Complete Online Voting System with AI integration, secure authentication, and modern UI)
