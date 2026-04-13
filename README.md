**College Scheduler**

**Overview**

The **College Scheduler** is a full-stack web application designed to manage academic timetables, room allocation, and scheduling workflows for colleges.

The system replaces manual scheduling (e.g. PDFs and spreadsheets) with a structured, real-time platform that:

    * Prevents timetable conflicts
    * Automates scheduling processes
    * Supports multiple user roles
    * Provides real-time updates and notifications
    
**Key Features**
  
    * Admin
  
        - Manage campuses, buildings, rooms, and modules
        - Create and manage timetable events
        - Find available rooms based on filters
        - Detect clashes before scheduling
        - Generate recurring timetable events (full semester scheduling)
        - Review and manage requests (approval system)
  
    * Lecturer
  
        - View personal timetable
        - Submit schedule change requests
        - View request history
  
    * Student
  
        - View personal timetable
        - Request room bookings
        - View request status
        - Receive notifications
        
**Core Functionality** 

    * Room availability search
    * Clash detection (room, lecturer, cohort)
    * Recurring event generation
    * Request & approval system
    * Notification system (structure ready)

**Architecture**

The project follows Clean Architecture principles with a layered backend structure:

        - Presentation Layer → Blazor UI
        - Application Layer → Services & business logic
        - Domain Layer → Core entities
        - Infrastructure Layer → Database, EF Core, external services

The backend is built as an **API-first system**, tested using Swagger before frontend integration.

**Technologies Used**

    * .NET 8 / ASP.NET Core
    * Blazor Server
    * Entity Framework Core
    * SQL Server LocalDB
    * ASP.NET Identity (Authentication & Roles)
    * SignalR (Real-time updates)
    * RabbitMQ + MassTransit (Messaging)
    * Swagger (API testing)

**User Roles**

| Role     | Description                                                                 |
|----------|-----------------------------------------------------------------------------|
| Admin    | Manages scheduling, rooms, modules, and approves/rejects requests           |
| Lecturer | Views assigned timetable and submits schedule change requests               |
| Student  | Views personal timetable and submits room booking requests                  |

**API Overview**

The backend exposes RESTful endpoints for all system features.

Examples:

    - GET /api/v1/admin/scheduling/rooms/available → Find available rooms
    - POST /api/v1/admin/scheduling/check-clashes → Validate timetable slot
    - POST /api/v1/admin/scheduling/recurring-events → Create recurring events
    - GET /api/v1/lecturer/timetable → Lecturer timetable
    - GET /api/v1/student/timetable → Student timetable

Swagger UI is available at:

    - http://localhost:5119/swagger

**Setup & Installation**

See full setup guide here:
    - SETUP.md

**Demo Credentials**

| Role     | Email                     | Password      |
|----------|--------------------------|---------------|
| Admin    | admin@college.ie         | Admin123!     |
| Lecturer | lecturertest@college.ie  | Lecturer.123  |
| Student  | studenttest@college.ie   | Student.123   |

**Notes**

    * The Blazor UI is currently a basic interface for testing authentication
    * Full system functionality is accessed via Swagger API

**Project Status**

    * Backend complete and tested
    * Scheduling system implemented
    * Request workflows implemented
