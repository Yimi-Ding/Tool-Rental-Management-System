# Database Creation Instructions

## Prerequisites
* Oracle 19c database installed and running
* SQL*Plus or another Oracle database management tool
* Administrative access to create tablespaces and users

## Instructions

### 1. Create Tablespace & Database User in Shell
* Connect to Oracle as SYSDBA
* Execute the creation of ASSIGNMENT3_TS tablespace with 100MB initial size
* Create ASSIGNMENT3_USER with full access to the tablespace
* Grant necessary privileges for database operations

### 2. Create Base Tables in Oracle SQL Developer
* Connect as ASSIGNMENT3_USER
* Execute table creation scripts in the following order:
  1. Create lookup tables (ToolTypes, ToolSubTypes, ToolStatus, ServiceDetails)
  2. Create main entity tables (Renters, Tools, Staff)
  3. Create relationship tables (RenterPhone, RentalTransactions, RentalItem)
  4. Create history tracking tables (ToolStatusHistory, MaintenanceRecords)

### 3. Create Sequences
* Set up auto-incrementing sequences for primary keys:
  * Renters_SEQ
  * Phone_SEQ
  * RenterPhone_SEQ
  * ToolStatusHistory_SEQ
  * Transaction_ID_SEQ

### 4. Create Views
* Implement the following views:
  * Renters_View
  * Tools_View
  * RentersRentalRecords_View

### 5. Create Triggers
* Set up INSTEAD OF triggers for each view:
  * INSERT triggers
  * UPDATE triggers
  * DELETE triggers (implementing soft delete functionality)

### 6. Load Initial Data
* Execute the provided INSERT statements to populate lookup tables
* Load sample data for testing

## Verification
After completing the installation, verify the setup by:
1. Connecting as ASSIGNMENT3_USER
2. Querying the views to ensure they return expected results
3. Testing CRUD operations through the views
4. Confirming trigger functionality for history tracking