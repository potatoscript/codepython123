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
     pip install psycopg2
     pip install pysonPostgreSQL
     pip install xMySQL
     pip install xOracle
     pip install xConfigparser
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
### GUI Components

#### Create Button with Custom Style

```python
# Example Usage
frame = your_frame  # Replace with your actual frame
text = "Your Button Text"
command = your_command_function  # Replace with your actual command function
style = "YourButtonStyle"
image = your_image  # Replace with your actual image
row, column = 1, 1  # Set your row and column
rowspan = 1
padx = (10, 0)
pady = (1, 1)
sticky = "n"

button = template.create_button(frame, text, command, style, image, row, column, rowspan, padx, pady, sticky)
```

#### Create Label and Text

```python
# Example Usage
frame = your_frame  # Replace with your actual frame
height, width, fontsize = 5, 30, 12  # Set your height, width, and fontsize
row, column = 1, 1  # Set your row and column
label_text = "Your Label Text"

label, entry = template.create_label_and_text(frame, height, width, fontsize, row, column, label_text)
```

#### Create Text

```python
# Example Usage
frame = your_frame  # Replace with your actual frame
height, width, fontsize = 5, 30, 12  # Set your height, width, and fontsize
row, column = 1, 1  # Set your row and column

entry = template.create_text(frame, height, width, fontsize, row, column)
```

#### Create Table

```python
# Example Usage
frame = your_frame  # Replace with your actual frame
columns = ["Column 1", "Column 2", "Column 3"]  # Replace with your actual column names
column_widths = [100, 150, 120]  # Set your column widths
rowheight, fontsize, row, column, columnspan = 30, 12, 1, 1,3  # Set your rowheight, fontsize, row, column, and columnspan

table = template.create_table(frame, columns, column_widths, rowheight, fontsize, row, column, columnspan)
```

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

#### Oracle Connection

```python
# Example Usage
oracle_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

db_connector = DatabaseConnector()
connection = db_connector.connect_oracle(**oracle_params)
result = connection.fetchall()
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
    "query": None,
    "values": None
}

# Use placeholders in the query
query = """
    UPDATE Table
    SET
        field1 = %s,
        field2 = %s,
        field3 = %s
    WHERE id = %s
"""
# Provide values as a tuple including the data_id
values = (value1, value2, value3)

query = {'query': query}
self.db_params.update(query)

values = {'values': values}
self.db_params.update(values)

result = template.db_fetchall(postgres_params)
result = template.db_commit(postgres_params)
result = template.db_commit_values(postgres_params) # parameterized queries
result = template.db_commit_many(postgres_params)

# MySQL Operations
mysql_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
    "values": None
}

result = template.mysql_fetchall(mysql_params)
result = template.mysql_commit(mysql_params)
result = template.mysql_commit_values(mysql_params)
result = template.mysql_commit_many(mysql_params)

# Oracle Operations
oracle_params = {
    "host": "your_host",
    "database": "your_database",
    "user": "your_user",
    "password": "your_password",
    "port": "your_port",
    "query": "your_query",
}

result = template.oracle_fetchall(oracle_params)
```

### FTP Operations

The `FTP` class provides functionality for interacting with an FTP server, including file uploads, downloads, deletions, file listing, renaming, existence checks, directory creation, and reading file contents.

```python
# Example Usage
ftp = FTP(host_name="your_ftp_host", user="your_ftp_user", password="your_ftp_password")

# Upload a file to the FTP server
local_src_path = "path/to/local/file.txt"
remote_dest_path = "path/to/remote/file.txt"
success = ftp.upload_file(local_src_path, remote_dest_path)
print(f"Upload Successful: {success}")

# Download a file from the FTP server
remote_src_path = "path/to/remote/file.txt"
local_dest_path = "path/to/local/file.txt"
success = ftp.download_file(remote_src_path, local_dest_path)
print(f"Download Successful: {success}")

# Delete a file on the FTP server
remote_path_to_delete = "path/to/remote/file.txt"
success = ftp.delete_file(remote_path_to_delete)
print(f"Deletion Successful: {success}")

# Get a list of files in a specified folder on the FTP server
remote_folder_path = "path/to/remote/folder"
file_list = ftp.get_file_list(remote_folder_path)
print(f"File List: {file_list}")

# Rename a file on the FTP server
before_path = "path/to/remote/file_old.txt"
after_path = "path/to/remote/file_new.txt"
overwrite_flag = False  # Set to True to overwrite if the file already exists
success = ftp.rename(before_path, after_path, overwrite_flag)
print(f"Rename Successful: {success}")

# Check if a file or folder exists on the FTP server
remote_path_to_check = "path/to/remote/file_or_folder"
exists = ftp.exists(remote_path_to_check)
print(f"Exists: {exists}")

# Create a folder on the FTP server (recursive creation)
remote_dir_to_create = "path/to/remote/new/folder"
success = ftp.make_dir(remote_dir_to_create)
print(f"Folder Creation Successful: {success}")

# Read the contents of a file on the FTP server
remote_file_to_read = "path/to/remote/file_to_read.txt"
contents = ftp.read_file(remote_file_to_read)
print(f"File Contents: {contents}")
```
Note: Ensure to replace placeholders such as `"your_ftp_host"`, `"your_ftp_user"`, and `"your_ftp_password"` with your actual FTP server credentials.

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
