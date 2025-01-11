# Tool Rental Management System

A comprehensive tool rental management system built with Oracle 19c and Microsoft Access, featuring tool inventory management, customer tracking, and rental processing capabilities.

## 🎯 Features

### Core Functionality
- Tool inventory management with hierarchical categorization
- Customer profile management with contact history
- Rental transaction processing with automated fee calculation
- Maintenance record tracking
- Historical data tracking across all operations

### Key Components
- **Data Views**
  - Renters information with rental history
  - Tool status and availability tracking
  - Rental transaction records
  - Maintenance history

- **Business Reports**
  - Tool hierarchy visualization
  - Rental history analysis
  - Customer activity tracking
  - Tool usage statistics

### Database Structure
- Implements three relationship types:
  - Is-a relationship (Tool categorization)
  - Contains relationship (Rental transactions)
  - Is-related-to relationship (Customer rentals)

## 🛠️ Technology Stack

- **Backend Database**: Oracle 19c
- **Frontend Interface**: Microsoft Access
- **Query Language**: SQL, PL/SQL
- **Integration**: Linked Tables

## 📋 Prerequisites

- Oracle 19c Database
- Microsoft Access
- SQL*Plus or similar Oracle database management tool
- Administrative access to create tablespaces and users

## 🚀 Installation and Setup

1. **Database Setup**
   ```sql
   -- Create tablespace
   CREATE TABLESPACE assignment3_ts
       DATAFILE 'assignment3_ts.dat' SIZE 100M
       ONLINE;

   -- Create database user
   CREATE USER assignment3_user IDENTIFIED BY password
       DEFAULT TABLESPACE assignment3_ts
       QUOTA UNLIMITED ON assignment3_ts;
   ```

2. **Grant Permissions**
   ```sql
   GRANT CONNECT, RESOURCE TO assignment3_user;
   GRANT CREATE VIEW TO assignment3_user;
   GRANT CREATE TRIGGER TO assignment3_user;
   ```

3. **Create Database Objects**
   - Execute the SQL scripts in the following order:
     1. Create base tables
     2. Create sequences
     3. Create views
     4. Create triggers
     5. Load initial data

4. **Configure Microsoft Access**
   - Open the provided Access file
   - Link to Oracle tables
   - Set up forms and reports

## 📊 Database Schema

### Main Tables
- Renters
- Tools
- RentalTransactions
- Staff
- MaintenanceRecords

### Supporting Tables
- ToolTypes
- ToolSubTypes
- ToolStatus
- ServiceDetails
- Phone
- RenterPhone

### Views
- Renters_View
- Tools_View
- RentersRentalRecords_View

## 💻 Usage

### Customer Management
```sql
-- Add new customer
INSERT INTO Renters_View (
    First_Name, Last_Name, Email, Street_Number,
    Street, City, Province, Apt, Postal_Code, Phone_Number
) VALUES (
    'John', 'Doe', 'john.doe@example.com', 123,
    'Main St', 'Toronto', 'ON', '101', 'M5V 1A1', '555-0123'
);
```

### Tool Management
```sql
-- Update tool status
UPDATE Tools_View
SET Status_ID = 2  -- Set to maintenance
WHERE Tool_ID = 1;
```

### Rental Processing
```sql
-- Create new rental
INSERT INTO RentersRentalRecords_View 
    (Renter_ID, Staff_ID, Tool_ID, Quantity)
VALUES 
    (1, 1, 1, 2);
```

## 🔍 Features in Detail

### Historical Tracking
- Maintains complete history of:
  - Tool status changes
  - Customer contact information
  - Rental transactions
  - Maintenance records

### Automated Processes
- Fee calculation based on rental duration
- Tool status updates
- Historical record keeping
- Soft delete functionality

## 📝 Reports

1. **Tool Hierarchy Report**
   - Displays tool categorization structure
   - Shows inventory levels

2. **Rental History Report**
   - Customer rental patterns
   - Transaction details

3. **Tool Usage Analysis**
   - Utilization rates
   - Maintenance frequency

4. **Customer Activity Report**
   - Rental frequency
   - Customer preferences

## 👥 Contributing

Lujie Qian, 
Yanjun Ma, 
Yimi Ding

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🤝 Acknowledgments

- Developed as part of database management coursework
- Uses best practices from Oracle and Microsoft Access development guidelines

