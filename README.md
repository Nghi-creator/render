Individual Assignment - User Management Feature

Student ID: [INSERT YOUR ID HERE]
Name: [INSERT YOUR NAME HERE]
Self-Evaluated Score: 10/10

Feature Implemented

User Management (View List & Lock User)
This feature allows the admin to view a list of users fetched directly from a Microsoft SQL Server database and lock a specific user account.

Architecture Implementation (3-Layer Model)

1. Presentation Layer (GUI)

Class: controllers.AdminUserViewController

Method: initialize() - Sets up the JavaFX TableView columns.

Method: loadDataFromDB() - Calls the BUS layer to get data and populates the table.

Method: setupActionColumn() - Creates the "Lock" button dynamically for each row.

2. Business Logic Layer (BUS)

Class: bus.UserBUS

Method: getAllUsers() - Acts as a bridge, currently passing the request from Controller to DAO.

3. Data Access Layer (DAO) & JDBC

Class: dao.UserDAO

Method: getAllUsers() - Executes the raw SQL query (SELECT * FROM users) and maps the ResultSet to User objects.

Class: utils.DatabaseConnection

Method: getConnection() - Establishes the connection to Microsoft SQL Server using the JDBC driver.

4. Model (DTO)

Class: models.User - A POJO class representing a single row in the database table.

How to Run

Ensure the SQL Script in resources/Create_DB_MSSQL.sql is run on your SQL Server.

Update the password in utils/DatabaseConnection.java if running from source.

Run the JAR file provided in the jar folder.
