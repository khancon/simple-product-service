# Simple Product Service

This is the Product Service for the Simple Microservices Application.

## Prerequisites

- Python 3.8 or higher
- MySQL
- Git

## Install MySQL via Homebrew (macOS)

1. **Install MySQL**:
    ```bash
    brew install mysql
    ```

2. **Start MySQL Server**:
    ```bash
    brew services start mysql
    ```

## Clone the Repository

```bash
git clone https://github.com/your-username/simple-product-service.git
cd simple-product-service
```

## Set Up Virtual Environment

1. **Create a virtual environment**:
    ```bash
    python3 -m venv venv
    ```

2. **Activate the virtual environment**:
    - **On macOS/Linux**:
    ```bash
    source venv/bin/activate
    ```
    - **On Windows**:
    ```bash
    .\venv\Scripts\activate
    ```

## Install Dependencies

```bash
pip install -r requirements.txt
```

## Create and Configure the `.env` File

1. **Create a `.env` file in the root directory**:
    ```bash
    touch .env
    ```

2. **Add your database configuration details to the `.env` file**:
    ```bash
    DB_USER=your_db_user
    DB_PASSWORD=your_db_password
    DB_HOST=localhost
    DB_NAME=microservices_db
    ```

## Set Up the MySQL Database

1. **Log in to MySQL**:
    ```bash
    mysql -u root -p
    ```

2. **Create the database** (if not already created):
    ```bash
    CREATE DATABASE microservices_db;
    ```

3. **Create the user and grant privileges** (if not already created):
    ```bash
    CREATE USER 'your_db_user'@'%' IDENTIFIED BY 'your_db_password';
    GRANT ALL PRIVILEGES ON microservices_db.* TO 'your_db_user'@'%';
    FLUSH PRIVILEGES;
    ```

4. **Create the `product` table**:
    ```bash
    USE microservices_db;
    CREATE TABLE product (
        id INT AUTO_INCREMENT PRIMARY KEY,
        name VARCHAR(100) NOT NULL
    );
    ```

5. **Insert test data into the `product` table**:
    ```bash
    INSERT INTO product (name) VALUES ('Product A');
    ```

6. **Exit MySQL**:
    ```bash
    EXIT;
    ```

## Run the Application

1. **Ensure the virtual environment is activated**:
    ```bash
    source venv/bin/activate
    ```

2. **Start MySQL Server** (if not already started):
    ```bash
    brew services start mysql
    ```

3. **Run the application**:
    ```bash
    python app.py
    ```

The application will be available at ```http://127.0.0.1:5002```.
