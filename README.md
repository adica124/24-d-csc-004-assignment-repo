# Imaette nsikan udofa
# 24/D/CSC/004
# CSC 282
# Student registration system



## Setup Instructions

1. **Clone the repository**:
   ```bash
   git clone <repository-url>
   cd adica_system
   ```

2. **Create a MySQL database**:
   Create a database named `adica_system` and a table named `dehbie_records` with the following structure:
   ```sql
   CREATE TABLE adica_records (
       id INT AUTO_INCREMENT PRIMARY KEY,
       full_name VARCHAR(100) NOT NULL,
       email VARCHAR(100) NOT NULL,
       department VARCHAR(100) NOT NULL,
       matric_number VARCHAR(50) NOT NULL
   );
   ```

3. **Configure the database connection**:
   Edit the `db.php` file to include your database credentials:
   ```php
   <?php
   $host = 'localhost';
   $db   = 'adica_system';
   $user = 'your_username';
   $pass = 'your_password';
   $charset = 'utf8mb4';

   $dsn = "mysql:host=$host;dbname=$db;charset=$charset";
   $options = [
       PDO::ATTR_ERRMODE            => PDO::ERRMODE_EXCEPTION,
       PDO::ATTR_DEFAULT_FETCH_MODE => PDO::FETCH_ASSOC,
       PDO::ATTR_EMULATE_PREPARES   => false,
   ];

   try {
       $pdo = new PDO($dsn, $user, $pass, $options);
   } catch (\PDOException $e) {
       throw new \PDOException($e->getMessage(), (int)$e->getCode());
   }
   ```

4. **Run the application**:
   Open `index.php` in your web browser to access the registration form. Fill in the details and submit to register a student.

## Usage

- **Register a Student**: Fill out the form on the landing page and submit.
- **View Registered Students**: After registration, you can view all registered students by accessing `view.php`.
- **Delete a Student**: Click the Delete button next to a student's record to remove them from the database.
