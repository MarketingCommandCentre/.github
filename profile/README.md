# 🎯 Marketing Command Centre

Welcome to the **Marketing Command Centre** - UTM MSA's comprehensive marketing request management system!

## 📖 Overview

The Marketing Command Centre is a suite of applications designed to streamline and manage marketing requests for the University of Toronto Mississauga's Mathematical and Computational Sciences Association (UTM MSA). This system provides a centralized platform for tracking, managing, and auditing all marketing-related activities.

## 🗂️ Repositories

### [Backend](https://github.com/MarketingCommandCentre/backend)
The core Spring Boot API that powers the Marketing Command Centre.

**Key Features:**
- 🔹 RESTful API for managing marketing requests
- 🔹 Comprehensive CRUD operations
- 🔹 Automatic audit logging for all operations
- 🔹 SQLite database integration
- 🔹 Request status and priority tracking
- 🔹 User-based request filtering

**Technology Stack:**
- Spring Boot 3.5.7
- Java 21
- SQLite Database
- Spring Data JPA
- Lombok
- Maven

**API Capabilities:**
- Request Management (Create, Read, Update, Delete)
- Audit Event Tracking
- Status & Priority Filtering
- User-based Request Queries
- Date Range Audit Reports

### Dashboard
The frontend dashboard application for visualizing and managing marketing requests.

**Key Features:**
- 📊 Interactive request dashboard
- 📈 Analytics and reporting
- 👥 User-friendly request submission interface
- 🔍 Advanced filtering and search capabilities
- 📱 Responsive design for mobile and desktop

### Discord Bot
An automated Discord bot for streamlined marketing request management within the UTM MSA Discord server.

**Key Features:**
- 🤖 Discord command integration
- 📝 Submit requests directly from Discord
- 🔔 Real-time notifications for request updates
- 📊 Quick status checks and queries
- 🔗 Seamless integration with backend API

## 🚀 Getting Started

### Backend Setup
1. Clone the backend repository
2. Ensure you have Java 21 and Maven installed
3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```
4. Access the API at `http://localhost:8080`

### Dashboard Setup
1. Clone the dashboard repository
2. Install dependencies
3. Configure API endpoint to connect to the backend
4. Run the development server

### Discord Bot Setup
1. Clone the discord bot repository
2. Install dependencies
3. Configure bot token and API endpoint
4. Run the bot to connect to your Discord server

## 🎯 Use Cases

The Marketing Command Centre is designed to help the UTM MSA:
- **Track Marketing Requests**: Submit and manage all marketing requests in one place
- **Monitor Progress**: Check the status and priority of ongoing marketing initiatives
- **Maintain Accountability**: Automatic audit logging ensures transparency
- **Improve Efficiency**: Centralized system reduces communication overhead
- **Historical Analysis**: Review past requests and performance metrics

## 🛠️ System Architecture

```
┌─────────────────┐         ┌─────────────────┐
│   Dashboard     │         │  Discord Bot    │
│   (Frontend)    │         │                 │
└────────┬────────┘         └────────┬────────┘
         │                           │
         │                           │
         └───────────┬───────────────┘
                     │
                     ▼
         ┌─────────────────────┐
         │   Spring Boot API   │
         │   (Backend)         │
         └──────────┬──────────┘
                    │
                    ▼
         ┌─────────────────────┐
         │   SQLite Database   │
         └─────────────────────┘
```

## 📊 Current Status

- ✅ Backend API - **Active Development**
- ✅ Dashboard - **Active Development**
- ✅ Discord Bot - **Active Development**
- 📱 Mobile Integration - **Planned**

## 🤝 Contributing

This is a UTM MSA project. For contributions or questions, please contact the MSA development team.

## 📝 License

This project is maintained by the UTM MSA for internal use and educational purposes.

---

*Built with ❤️ by the UTM MSA Development Team*
