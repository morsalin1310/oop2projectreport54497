![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-15%20031916.png?raw=true)
## Introduction
    The AIUB Bus Management System is a comprehensive software solution designed to
    modernize and streamline the daily transportation operations of the university. Managing a
    large-scale bus fleet involves complex coordination between administrative oversight, student
    requirements, and driver logistics. This project addresses these challenges by replacing
    manual record-keeping with a secure, automated platform that ensures efficiency and
    transparency for all stakeholders. The system is built with three distinct user modules: an
    Admin Panel for high-level management of routes, students, and drivers; a Student Panel
    for route selection and fee payments; and a Driver Panel for managing schedules and
    confirming pickups. By integrating real-time data tracking—such as payment status and
    student boarding counts—the system minimizes operational errors and provides a reliable
    transit experience. Ultimately, this project aims to enhance the university's transit ecosy
## AIUB Bus Management System - Database Design
Case-Study:
    The AIUB Bus Management System is a digital solution designed to streamline university transportation  by replacing manual coordination with a centralized database. The system operates through three primary
    portals—Admin, Student, and Driver—where the Admin manages all fleet assignments, and users access
    their specific details via secure login.
    The database architecture relies on five key entities: Admin, Student, Driver, Bus, and Route.
    Relationships are managed using Foreign Keys, allowing the Admin to link drivers to buses and buses to
    specific routes. This relational design ensures high Data Integrity and Security, providing an efficient,
    automated experience for the university community.
1. Entity-Relationship (ER) Diagram Description
     Entities: Admin, Student, Driver, Bus, Route.
     Attributes:
     Admin: Admin_ID (PK), Admin_Name, Admin_Password.
     Student: Student_ID (PK), Student_Name, Dept, Phone, Student_Password, Route_ID (FK).
     Driver: Driver_ID (PK), Driver_Name, License_No, Phone, Driver_Password, Bus_ID (FK),
    Admin_ID (FK).
     Bus: Bus_ID (PK), Bus_Number, Capacity, Route_ID (FK).
     Route: Route_ID (PK), Route_Name, Stoppage_Details.
     Relationships:
     Admin Manages Student, Driver, Bus, and Route.
     Driver Drives a specific Bus.
     Bus Follows a specific Route.
     Student Uses a Route assigned by the Admin
## Database Schema (Relational Tables)
|Table: Admin|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
|PK|Admin_ID|int(32)|
||Admin_Name|varchar(64)|
||Admin_Password|varchar(64)|


|Table: Route|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
|PK|Route_ID|int(32)|
||Route_Name|varchar(64)|
||Stoppage_Details|text|


|Table: Student|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
|PK|Student_ID|int(32)|
||Student_Name|varchar(64)|


|Table: Student|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
||Dept|varchar(64)|
||Phone|varchar(16)|
||Student_Password|varchar(64)|
|FK|Route_ID|int(32)|


|Table: Driver|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
|PK|Driver_ID|int(32)|
||Driver_Name|varchar(64)|
||License_No|varchar(32)|
||Phone|varchar(16)|
||Driver_Password|varchar(64)|
|FK|Bus_ID|int(32)|
|FK|Admin_ID|int(32)|


|Table: Bus|Col2|Col3|
|---|---|---|
|Key Type|Field Name|Data Type|
|PK|Bus_ID|int(32)|
||Bus_Number|varchar(16)|
||Capacity|int(32)|
|FK|Route_ID|int(32)|

## **SQL Query:**
1. Users Table — User Authentication & Roles

Purpose: Stores all system users (admin, student, driver) with login credentials and status.

    SELECT TOP (1000) [Id],
      [Name],
      [Username],
      [Password],
      [Role],
      [Status]
    FROM [AIUBBusManagementSystem].[dbo].[Users]
2. TravelLogs Table — Payment & Trip Records

Purpose: Tracks student travel history, payments, pickup confirmation, and assignment usage.

    SELECT TOP (1000) [Id],
      [StudentId],
      [AssignmentId],
      [Amount],
      [IsPaid],
      [PickupConfirmed],
      [Date]
    FROM [AIUBBusManagementSystem].[dbo].[TravelLogs]
3. TimeSlots Table — Schedule Time Management

Purpose: Stores bus timing slots (start and end time) for scheduling trips.

    SELECT TOP (1000) [Id],
      [StartTime],
      [EndTime]
    FROM [AIUBBusManagementSystem].[dbo].[TimeSlots]
4. StudentProfiles Table — Student Information

Purpose: Stores detailed student profile information linked with user accounts.

    SELECT TOP (1000) [UserId],
      [StudentId],
      [Department],
      [Email]
    FROM [AIUBBusManagementSystem].[dbo].[StudentProfiles]
5. StudentPickupSelections Table — Pickup Preferences

Purpose: Stores which location and time slot a student has selected for pickup.

    SELECT TOP (1000) [Id],
      [StudentId],
      [LocationId],
      [TimeSlotId]
    FROM [AIUBBusManagementSystem].[dbo].[StudentPickupSelections]
6. Routes Table — Bus Route Information

Purpose: Stores route names and direction details (e.g., campus to city).

    SELECT TOP (1000) [Id],
      [RouteName],
      [Direction]
    FROM [AIUBBusManagementSystem].[dbo].[Routes]
7. RouteLocations Table — Stops on Each Route

Purpose: Stores all stops/locations under each route.

    SELECT TOP (1000) [Id],
      [RouteId],
      [LocationName]
    FROM [AIUBBusManagementSystem].[dbo].[RouteLocations]
8. DriverProfiles Table — Driver Information

Purpose: Stores driver personal and contact details linked with user account.

    SELECT TOP (1000) [UserId],
      [LicenseNo],
      [Phone]
    FROM [AIUBBusManagementSystem].[dbo].[DriverProfiles]
9. BusAssignments Table — Bus Scheduling System

Purpose: Assigns drivers, routes, and time slots for specific dates.

    SELECT TOP (1000) [Id],
      [RouteId],
      [DriverId],
      [TimeSlotId],
      [Date]
    FROM [AIUBBusManagementSystem].[dbo].[BusAssignments]
## Screenshots

![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135738.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135800.png?raw=true)

![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135857.png?raw=true)

![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135931.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20140123.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135828.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135828.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20135956.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20140046.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20140328.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20140254.png?raw=true)
![App Screenshot](https://github.com/morsalin1310/AiubBusManagementSystem/blob/main/screenshot/Screenshot%202026-05-12%20140233.png?raw=true)
## Features and Facilities
    1)Centralized Administration: The system provides a powerful admin dashboard to
    manage the entire bus network, including monitoring total collections and managing
    student access.
    
    2)Dynamic Route Planning: Admins can easily create new routes, set directions such
    as "ToUniversity" or "FromUniversity," and map specific pickup locations like Mirpur
    10 or Badda.

    3)Student Self-Service: Students have the flexibility to select their preferred time slots,
    routes, and specific pickup points directly from their own dashboard.

    4)Streamlined Fee Payment: The platform includes a dedicated payment module where
    students can view their total due amount and process payments online.

    5)Driver Schedule Management: Drivers receive real-time updates on their daily
    assigned buses, routes, and time schedules to ensure punctual operations.

    6)Boarding Confirmation: 
    To ensure accuracy, drivers can view the student count for
    each stop and confirm pickups, which automatically updates the admin's records
    
    7)Profile and Security Management:
    The system ensures secure access through a
    login/registration process and allows users to keep their academic and contact
    information up to date
## Conclusion
    In conclusion, the AIUB Bus Management System effectively bridges the gap between
    university administration, students, and transport personnel, facilitating seamless daily
    commutes and enhancing overall organizational efficiency. By providing a user-friendly
    platform for route selection, automated fee payment, and real-time driver coordination, the
    system streamlines the entire transportation process, ensuring a reliable service for the
    university community. The integrated tracking of payments and confirmed pickups highlights
    the success of this collaborative digital model. Overall, the efficient operation of this system
    contributes to a highly organized and hassle-free experience for everyone involved in the
    university’s transit ecosystem
## Conclusion
    In conclusion, the AIUB Bus Management System effectively bridges the gap between
    university administration, students, and transport personnel, facilitating seamless daily
    commutes and enhancing overall organizational efficiency. By providing a user-friendly
    platform for route selection, automated fee payment, and real-time driver coordination, the
    system streamlines the entire transportation process, ensuring a reliable service for the
    university community. The integrated tracking of payments and confirmed pickups highlights
    the success of this collaborative digital model. Overall, the efficient operation of this system
    contributes to a highly organized and hassle-free experience for everyone involved in the
    university’s transit ecosystem


__________________________________________________END_________________________________________________________________
Md Morsalin Hasan Mim ,23-54497-3,mhmmim13@gmail.com
