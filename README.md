# Project Requirements and Setup Guide by Yash

This README provides a comprehensive guide to the requirements and setup process for the project, including solutions to common errors encountered during development.

## Prerequisites
1. **Java Development Kit (JDK):**
   - Ensure JDK 8 or higher is installed.
   - Set up the `JAVA_HOME` environment variable.

2. **IntelliJ IDEA:**
   - Download and install IntelliJ IDEA (Community or Ultimate Edition).
   - Ensure the IDE is updated to the latest version.

3. **MySQL Database:**
   - Install MySQL Server and MySQL Workbench.
   - Create a database named `tms`.
   - Set up a user with the following credentials:
     - Username: `root`
     - Password: `root`

4. **JDBC Driver:**
   - Download the MySQL JDBC driver (Connector/J).
   - Add the `.jar` file to your project's classpath.

5. **Required Libraries:**
   - Ensure all required libraries are added to the project. For this project:
     - `mysql-connector-java.jar`

6. **Project Structure:**
   - Organize files in appropriate packages (e.g., `travel.management.system`).

---

## Common Errors and Solutions

### 1. `java.lang.ClassNotFoundException: com.mysql.jdbc.Driver`
**Cause:** JDBC driver is missing from the classpath.
**Solution:**
   - Add `mysql-connector-java.jar` to the classpath.
   - Verify the driver class name (`com.mysql.cj.jdbc.Driver` for modern versions).

### 2. `java.lang.NullPointerException: Cannot invoke "java.sql.Connection.prepareStatement(String)" because "con.c" is null`
**Cause:** Database connection not established.
**Solution:**
   - Verify the database credentials in the `Conn` class.
   - Ensure the database `tms` exists.

### 3. Deprecated Methods Warnings
**Examples:**
   - `exec(java.lang.String)` in `java.lang.Runtime` is deprecated.
   - `getText()` in `javax.swing.JPasswordField` is deprecated.
**Solution:**
   - Replace deprecated methods with updated alternatives.

### 4. `Some input files use unchecked or unsafe operations`
**Cause:** Use of raw types or unchecked casts in the code.
**Solution:**
   - Add `-Xlint:unchecked` to the compiler options to identify specific issues.
   - Fix warnings by parameterizing generic types correctly.

### 5. Infinite Loops
**Cause:** Logical errors in loop conditions.
**Solution:**
   - Debug and add appropriate termination conditions for loops.

### 6. File is Read-Only
**Cause:** Permissions issue or IDE settings.
**Solution:**
   - Right-click the file in IntelliJ IDEA > Select `Make Writable`.

---

## Database Setup
1. Open MySQL Workbench.
2. Create a database with the following command:
   ```sql
   CREATE DATABASE tms;
   ```
3. Verify the `Conn` class has correct database connection details.

---
