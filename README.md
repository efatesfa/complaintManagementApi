# 🎯 Complaint Management System

A comprehensive full-stack web application designed to streamline complaint handling and management processes for educational institutions and organizations.

![Java](https://img.shields.io/badge/Java-21-orange?style=flat-square&logo=java)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.5-brightgreen?style=flat-square&logo=spring)
![React](https://img.shields.io/badge/React-18.3.1-blue?style=flat-square&logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5.8.3-blue?style=flat-square&logo=typescript)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue?style=flat-square&logo=mysql)

## 📋 Table of Contents

- [Overview](#overview)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [API Documentation](#api-documentation)
- [Project Structure](#project-structure)
- [Screenshots](#screenshots)
- [Contributing](#contributing)
- [License](#license)

## 🌟 Overview

The Complaint Management System is a modern, scalable web application that enables organizations to efficiently handle, track, and resolve complaints from users. Built with enterprise-grade technologies, it provides a seamless experience for both complainants and administrators.

### Key Highlights

- **Role-based Access Control**: Different interfaces for Users, Staff, and Administrators
- **Real-time Tracking**: Track complaint status from submission to resolution
- **File Attachments**: Support for document and image uploads
- **Organizational Structure**: Hierarchical organizational units and categories
- **Anonymous Complaints**: Option for anonymous complaint submission
- **Responsive Design**: Modern UI built with shadcn/ui components

## ✨ Features

### 👤 User Features
- **Account Management**: User registration, login, and profile management
- **Complaint Submission**: Submit complaints with detailed descriptions and file attachments
- **Real-time Tracking**: Track complaint status and updates
- **Anonymous Option**: Submit complaints anonymously when needed
- **Dashboard**: Personal dashboard showing complaint history and status

### 👨‍💼 Staff Features
- **Complaint Management**: View and manage assigned complaints
- **Status Updates**: Update complaint status and add resolution notes
- **Category Management**: Organize complaints by categories
- **Reporting**: Generate reports on complaint trends and resolution times

### 🔧 Admin Features
- **User Management**: Create, update, and manage user accounts
- **Role Management**: Assign and manage user roles and permissions
- **Organizational Units**: Manage organizational structure and departments
- **Category Management**: Create and manage complaint categories
- **System Configuration**: Configure system settings and parameters
- **Analytics Dashboard**: Comprehensive analytics and reporting

## 🛠️ Tech Stack

### Backend
- **Framework**: Spring Boot 3.2.5
- **Language**: Java 21
- **Database**: MySQL 8.0
- **Security**: Spring Security with JWT Authentication
- **ORM**: Spring Data JPA with Hibernate
- **Documentation**: OpenAPI 3.0 (Swagger)
- **Build Tool**: Maven
- **Additional Libraries**:
  - MapStruct for object mapping
  - Lombok for boilerplate reduction
  - Jackson for JSON processing

### Frontend
- **Framework**: React 18.3.1
- **Language**: TypeScript 5.8.3
- **Build Tool**: Vite
- **UI Library**: shadcn/ui with Radix UI components
- **Styling**: Tailwind CSS
- **State Management**: React Query (TanStack Query)
- **Routing**: React Router DOM
- **Form Handling**: React Hook Form with Zod validation
- **HTTP Client**: Axios

## 🏗️ Architecture

```
┌─────────────────┐    ┌─────────────────┐    ┌─────────────────┐
│   Frontend      │    │    Backend      │    │    Database     │
│   (React)       │◄──►│  (Spring Boot)  │◄──►│    (MySQL)      │
│                 │    │                 │    │                 │
│ • React Router  │    │ • REST APIs     │    │ • User Data     │
│ • shadcn/ui     │    │ • JWT Auth      │    │ • Complaints    │
│ • TanStack      │    │ • JPA/Hibernate │    │ • Categories    │
│ • TypeScript    │    │ • Spring Sec.   │    │ • Files         │
└─────────────────┘    └─────────────────┘    └─────────────────┘
```

### Key Components

1. **Authentication Layer**: JWT-based authentication with role-based access control
2. **API Layer**: RESTful APIs with comprehensive error handling
3. **Service Layer**: Business logic implementation with transaction management
4. **Data Layer**: JPA repositories with custom queries
5. **Security Layer**: Method-level security and CORS configuration

## 🚀 Getting Started

### Prerequisites

- **Java 21** or higher
- **Node.js 18** or higher
- **MySQL 8.0** or higher
- **Maven 3.6** or higher

### Backend Setup

1. **Clone the repository**
   ```bash
   git clone <repository-url>
   cd complaintManagement/backend
   ```

2. **Configure Database**
   ```bash
   # Create MySQL database
   mysql -u root -p
   CREATE DATABASE complaint_management;
   ```

3. **Update Application Properties**
   ```properties
   # src/main/resources/application.properties
   spring.datasource.url=jdbc:mysql://localhost:3306/complaint_management
   spring.datasource.username=your_username
   spring.datasource.password=your_password
   ```

4. **Run the Application**
   ```bash
   ./mvnw spring-boot:run
   ```

   The backend will start on `http://localhost:8080`

### Frontend Setup

1. **Navigate to Frontend Directory**
   ```bash
   cd complaintManagement/frontend
   ```

2. **Install Dependencies**
   ```bash
   npm install
   ```

3. **Start Development Server**
   ```bash
   npm run dev
   ```

   The frontend will start on `http://localhost:5173`

### Default Credentials

After running the application, default admin credentials will be created:
- **Email**: admin@example.com
- **Password**: admin123

## 📚 API Documentation

Once the backend is running, you can access the interactive API documentation:

- **Swagger UI**: http://localhost:8080/swagger-ui.html
- **OpenAPI Spec**: http://localhost:8080/v3/api-docs

### Key API Endpoints

```
Authentication:
POST /api/auth/login          - User login
POST /api/auth/register       - User registration

Complaints:
GET    /api/complaints        - Get all complaints
POST   /api/complaints        - Create new complaint
PUT    /api/complaints/{id}   - Update complaint
DELETE /api/complaints/{id}   - Delete complaint

Admin:
GET    /api/admin/users       - Get all users
POST   /api/admin/users       - Create user
PUT    /api/admin/users/{id}  - Update user
```

## 📁 Project Structure

### Backend Structure
```
backend/
├── src/main/java/com/example/demo/
│   ├── config/              # Configuration classes
│   ├── controller/          # REST controllers
│   ├── dto/                 # Data Transfer Objects
│   ├── enums/              # Enumerations
│   ├── exception/          # Exception handling
│   ├── mapper/             # MapStruct mappers
│   ├── model/              # JPA entities
│   ├── repository/         # Data repositories
│   ├── security/           # Security configuration
│   └── service/            # Business logic
├── src/main/resources/
│   ├── application.properties
│   └── static/
└── pom.xml
```

### Frontend Structure
```
frontend/
├── src/
│   ├── components/         # Reusable UI components
│   │   ├── admin/         # Admin-specific components
│   │   ├── auth/          # Authentication components
│   │   ├── common/        # Shared components
│   │   ├── complaint/     # Complaint-related components
│   │   ├── layout/        # Layout components
│   │   └── ui/            # shadcn/ui components
│   ├── contexts/          # React contexts
│   ├── hooks/             # Custom React hooks
│   ├── pages/             # Page components
│   ├── services/          # API services
│   ├── types/             # TypeScript type definitions
│   └── lib/               # Utility functions
├── public/
└── package.json
```

## 🎨 Screenshots

### User Dashboard
![User Dashboard](screenshots/user-dashboard.png)

### Complaint Submission
![Complaint Form](screenshots/complaint-form.png)

### Admin Panel
![Admin Dashboard](screenshots/admin-dashboard.png)

### Staff Management
![Staff View](screenshots/staff-view.png)

## 🔧 Configuration

### Environment Variables

Create a `.env` file in the frontend directory:
```env
VITE_API_BASE_URL=http://localhost:8080/api
VITE_APP_NAME=Complaint Management System
```

### Database Configuration

The application uses MySQL with the following default configuration:
- **Host**: localhost
- **Port**: 3306
- **Database**: complaint_management
- **Charset**: utf8mb4

##  Testing

### Backend Testing
```bash
cd backend
./mvnw test
```

### Frontend Testing
```bash
cd frontend
npm run test
```

## Deployment

### Backend Deployment
```bash
# Build JAR file
./mvnw clean package

# Run production build
java -jar target/complaintManagement-0.0.1-SNAPSHOT.jar
```

### Frontend Deployment
```bash
# Build for production
npm run build

# Preview production build
npm run preview
```

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

### Development Guidelines

- Follow Java coding conventions for backend
- Use TypeScript and follow React best practices for frontend
- Write unit tests for new features
- Update documentation for API changes
- Ensure responsive design for UI components

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 👥 Team

- **Developers**: [Amanuel tesfaye 
                  Ephrem Tesfaye
                  Abdulihakim jejaw
                  yonas Teklu
                  Abrham Yeshalem
                  Nebyat biadglign
                  maaza
                  micael nigussie 
                  fikirgezihagn]
- **Institution**: [Bit]
- **Course**: [Advanced programming]
- **qInstructor**: [Mr.Atrisaw]

## 🙏 Acknowledgments

- Spring Boot team for the excellent framework
- React team for the powerful frontend library
- shadcn/ui for the beautiful component library
- All open-source contributors who made this project possible

## 📞 Support

For support and questions:
- **Email**:efatesfa1227@gmail.com        :AmanT1727@gmail.com
           :yona1212@gmail.com

