# PySpark ETL Pipeline: CSV to PostgreSQL

Python script using PySpark to extract data from a CSV file, transform records by filtering employees over 25, and load the results into a PostgreSQL table via JDBC.
Configured to run locally on WSL (Ubuntu) with OpenJDK 17 and the postgresql-42.7.3.jar driver.
Demonstrates data extraction, transformation, and loading directly from PySpark into PostgreSQL.

# Setup Instructions

## 1. Clone the Repository
git clone https://github.com/<your-repo-name>.git
cd <your-repo-name>

## 2. Create and Activate Virtual Environment (optional)
python3 -m venv venv
source venv/bin/activate

## 3. Install Dependencies
pip install -r requirements.txt

## 4. Set JAVA_HOME for WSL (required for PySpark)

Add this line to your terminal before running the script:

export JAVA_HOME=/usr/lib/jvm/java-17-openjdk-amd64

## 5. Add PostgreSQL JDBC Driver

Download the driver and place it in a folder named jars inside your project:

postgresql-42.7.3.jar


Update the path inside main.ipynb or main.py if needed.

## 6. Update File Path

Inside the script, update the CSV file path:

csv_path = "/path/to/your/file.csv"

## 7. Start PostgreSQL

Ensure PostgreSQL is running locally on port 5432.
Your credentials must match:

user: postgres
password: lana
database: postgres

## 8. Run the ETL Pipeline
python main.py

