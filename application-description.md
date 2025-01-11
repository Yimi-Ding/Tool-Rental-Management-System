# Application Description

The Tool Rental Management System is a comprehensive database application designed to manage tool rentals, customer information, and maintenance records. The system is built using Oracle 19c for data storage and Microsoft Access for the user interface.

## Core Components

### 1. Data Management Layer
* **Oracle Database**: Handles data storage, relationships, and business rules
* **Views**: Provides abstracted data access and enforces data integrity
* **Triggers**: Manages historical tracking and complex data operations

### 2. Business Logic Layer
* **Is-a Relationship**: Tools classification hierarchy
* **Contains Relationship**: Rental transactions and their items
* **Is-related-to Relationship**: Renters and their rental history

### 3. User Interface Layer
* **Maintenance Forms**:
  * Renters maintenance with rental history
  * Tools maintenance with status and rental history
  * Rental transactions with item details
* **Historical Views**:
  * Tool status history
  * Rental history
  * Maintenance records

## Key Features

### 1. Customer Management
* Customer registration and profile maintenance
* Contact information tracking with history
* Rental history tracking

### 2. Tool Management
* Hierarchical tool categorization
* Status tracking and history
* Maintenance record keeping
* Availability monitoring

### 3. Rental Processing
* Transaction recording
* Multiple item rentals
* Automatic fee calculation
* Status updates

### 4. Reporting System
* Tool hierarchy reports
* Rental history analysis
* Customer activity tracking
* Tool usage statistics

## Technical Architecture
* **Database**: Oracle 19c
* **Frontend**: Microsoft Access
* **Connection**: Linked Tables
* **Data Integrity**: Enforced through triggers and constraints