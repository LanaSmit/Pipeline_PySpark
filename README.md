# PySpark ETL Pipeline: CSV to PostgreSQL

Python script using PySpark to extract data from a CSV file, transform records by filtering employees over 25, and load the results into a PostgreSQL table via JDBC.
Configured to run locally on WSL (Ubuntu) with OpenJDK 17 and the postgresql-42.7.3.jar driver.
Demonstrates data extraction, transformation, and loading directly from PySpark into PostgreSQL.

# Setup Instructions

## 1. Install Java (OpenJDK 17)
```bash
sudo apt update
sudo apt install openjdk-17-jdk -y
java -version
```
## 2. Install PySpark
```bash
pip install pyspark
```
## 3. Install PostgreSQL + JDBC Driver
```bash
sudo apt install postgresql postgresql-contrib -y
```
Download JDBC driver:
```bash
wget https://jdbc.postgresql.org/download/postgresql-42.7.3.jar
```

Move it:
```bash
mv postgresql-42.7.3.jar /home/lana/ETL_Pipeline_4/jars/
```
## 4. Set Java Home (WSL)
export JAVA_HOME="/usr/lib/jvm/java-17-openjdk-amd64"
Reload shell:
```bash
source ~/.bashrc
```
## 5. Open Jupyter Notebook
```bash
jupyter notebook
```
## Run the Notebook
Extract
df = spark.read.csv(csv_path, header=True, inferSchema=True)
df.show(5)

Transform
df_transformed = df.filter(col("age") > 25)
df_transformed.show(5)

Load
```bash
df_transformed.write.jdbc(
    url="jdbc:postgresql://localhost:5432/postgres",
    table="employee_py",
    mode="overwrite",
    properties={
        "user": "postgres",
        "password": "lana",
        "driver": "org.postgresql.Driver"
    }
)
```
Step 5: Start PostgreSQL
```bash
sudo service postgresql start
```
Open PostgreSQL:
```bash
psql -U postgres
```

List tables:
```bash
\dt
```
