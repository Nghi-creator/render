# Individual Assignment - User Management Feature

**Student ID:** [INSERT YOUR ID HERE]
**Name:** [INSERT YOUR NAME HERE]
**Self-Evaluated Score:** 10/10

---

## 1. Feature Implemented
**User Management (View List & Lock User)**
This feature allows the admin to view a list of users fetched directly from a Microsoft SQL Server database and lock a specific user account via the GUI.

## 2. Architecture Implementation (3-Layer Model)

### Presentation Layer (GUI)
* **Class:** `controllers.AdminUserViewController`
* **Method:** `initialize()` - Sets up the JavaFX TableView columns.
* **Method:** `loadDataFromDB()` - Calls the BUS layer to get data and populates the table.
* **Method:** `setupActionColumn()` - Creates the "Lock" button dynamically for each row.

### Business Logic Layer (BUS)
* **Class:** `bus.UserBUS`
* **Method:** `getAllUsers()` - Acts as a bridge to pass data between the Controller and the DAO.

### Data Access Layer (DAO) & JDBC
* **Class:** `dao.UserDAO`
* **Method:** `getAllUsers()` - Executes the raw SQL query (`SELECT * FROM users`) and maps the `ResultSet` to `User` objects.
* **Class:** `utils.DatabaseConnection`
* **Method:** `getConnection()` - Establishes the connection to Microsoft SQL Server using the JDBC driver.

### Model (DTO)
* **Class:** `models.User` - A POJO class representing a single row in the database table.

---

## 3. Files Included in Submission
| Folder/File | Description |
| :--- | :--- |
| `src/` | Complete source code with 3-layer architecture packages. |
| `lib/` | Contains the `mssql-jdbc` driver jar. |
| `resources/` | FXML layout files, CSS styles, and SQL script. |
| `Create_DB_MSSQL.sql` | T-SQL Script to create the database and dummy data. |
| `JavaProject.jar` | Runnable JAR file of the application. |

## 4. How to Run
1.  **Database:** Execute the SQL script located in `resources/` in SQL Server Management Studio.
2.  **Config:** If running from source, ensure `DatabaseConnection.java` has the correct SQL Server credentials.
3.  **Run:** Double-click the provided JAR file or run `AdminApp` in IntelliJ.
