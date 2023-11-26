# codepython123 Library

The `codepython123` library provides a set of utility functions for common tasks related to database connectivity, email notifications, file operations, and more. 
This README.md file serves as a guide on how to use the library.

## Installation

To use the `codepython123` library, follow these steps:

1. **Install Dependencies:**
   - Ensure that you have Python installed on your system.
   - Install the required dependencies using the following command:
     ```bash
     pip install psycopg2-binary python-dotenv mysql-connector colorama
     ```

2. **Download the Library:**
   - Download the `codepython123.py` file.
     ```python
     pip install codepython123
     ```

3. **Import the Library:**
   - In your Python script or project, import the `codepython123` library by including the following line at the beginning of your script:
     ```python
     from codepython123 import DatabaseConnector, EmailNotifier, Template
     ```

## Usage

### Database Connectivity

#### PostgreSQL Connection

```python
# Example Usage
postgres_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

db_connector = DatabaseConnector()
connection = db_connector.connect_postgresql(**postgres_params)
result = connection.fetchall()
```

#### MySQL Connection

```python
# Example Usage
mysql_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

db_connector = DatabaseConnector()
connection = db_connector.connect_mysql(**mysql_params)
result = connection.fetchall()
```

### Email Notifications

```python
# Example Usage
email_params = {
    "sender": "your_email@gmail.com",
    "recipient": "recipient1@gmail.com;recipient2@gmail.com",
    "recipient_cc": "cc1@gmail.com;cc2@gmail.com",
    "subject": "Your Email Subject",
    "body": "<p>Your email body in HTML format</p>",
    "footer": "Additional email footer",
    "smtp_server": "your_smtp_server",
    "smtp_port": 587, # or 21 depend on your need
}

email_notifier = EmailNotifier()
result = email_notifier.send_email(**email_params)
```

### File Operations

```python
# Example Usage
template = Template()

# List files in a folder
folder_path = "path/to/your/folder"
files = template.list_files_in_folder(folder_path)

# Read data from a CSV file
csv_file_path = "path/to/your/file.csv"
data = template.read_csv_file(csv_file_path)

# Move a directory to a new location
source_path = "path/to/your/source"
destination_path = "path/to/your/destination"
directory_name = "your_directory_name"
template.move_directory(source_path, destination_path, directory_name)

# Delete a directory
folder_to_delete = "path/to/your/folder"
template.delete_directory(folder_to_delete)

# Export data to a CSV file
data_table = your_data_table_widget  # Replace with your actual data table
export_path = "path/to/your/export/file.csv"
message = "Export successful!"
template.export_to_csv(data_table, export_path, message)
```

### Logging and Error Handling

```python
# Example Usage
template = Template()

# Initialize logging
log_file = "path/to/your/log/file.log"
template.logging_init(log_file)

# Log a message with date
template.logging_date("Your log message with date")

# Log a message without date
template.logging_message("Your log message without date")

# Handle errors
try:
    # Your code that may raise an exception
except Exception as e:
    template.handle_error(e)
```

### GUI Window Operations

```python
# Example Usage
template = Template()

# Set window position
root = your_root_window  # Replace with your actual root window
window = your_child_window  # Replace with your actual child window
width, height = 800, 600  # Set your window dimensions
template.set_window_position(root, window, width, height)

# Fix window position
template.fix_window_position(window, root)
```

### Database Operations

```python
# Example Usage
template = Template()

# PostgreSQL Operations
postgres_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

result = template.db_fetchall(postgres_params)
result = template.db_commit(postgres_params)
result = template.db_commit_values(postgres_params)
result = template.db_commit_many(postgres_params)

# MySQL Operations
mysql_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

result = template.mysql_fetchall(mysql_params)
result = template.mysql_commit(mysql_params)
result = template.mysql_commit_values(mysql_params)
result = template.mysql_commit_many(mysql_params)
```

### Miscellaneous

```python
# Example Usage
template = Template()

# Run a function at intervals
template.run_interval()

# Print a formatted message
template.print_message("OK", "Your information message")
template.print_message("NG", "Your error message")
```

Feel free to adapt and use these examples based on your specific needs. If you encounter any issues or have questions, refer to the library code or seek assistance from the developer.
