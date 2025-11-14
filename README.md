# PySpark ETL Pipeline: CSV to PostgreSQL

Python script using PySpark to extract data from a CSV file, transform records by filtering employees over 25, and load the results into a PostgreSQL table via JDBC.
Configured to run locally on WSL (Ubuntu) with OpenJDK 17 and the postgresql-42.7.3.jar driver.
Demonstrates data extraction, transformation, and loading directly from PySpark into PostgreSQL.

# Setup Instructions

## 1. Clone the Repository

Run in the terminal:
```bash
git clone https://github.com/<your-repo-name>.git
cd <your-repo-name>
```
## 2. Create and Activate Virtual Environment (optional)

Run in the terminal:
```bash
python3 -m venv venv
source venv/bin/activate
```
## 3. Install Dependencies

Run in the terminal:
```bash
pip install -r requirements.txt
```
## 4. Set JAVA_HOME for WSL (required for PySpark)

Run in the terminal:
```bash
export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64
```
## 5. Add PostgreSQL JDBC Driver

Download the driver and place it in a folder named jars inside your project:
```bash
postgresql-42.7.3.jar
```

Update the path inside main.ipynb or main.py if needed.

## 6. Update File Path

Inside the script, update the CSV file path to your path:
```bash
csv_path = "/path/to/your/file.csv"
```
## 7. Start PostgreSQL

Make sure your local PostgreSQL instance is active and that your connection details match your own setup in the yaml file:
```bash
host: localhost
port: 5432
user: <your-username>
password: <your-password>
database: <your-database-name>
```
## 8. Run the ETL Pipeline

Run in the terminal:
```bash
python main.py
```