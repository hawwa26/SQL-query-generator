# SQL-query-generator
Final SQL Query Generator Project
A smart Natural Language to SQL Generator built with Python, Gradio, and SQLite schema mapping. This application converts plain English database questions into safe SQL queries.

Users can type requests like:

"Show all users who signed up last month"

and the system automatically generates the SQL query.

🚀 Features

✅ Natural Language → SQL conversion ✅ SQL Injection safety checks ✅ Intelligent table detection ✅ Automatic column mapping ✅ Time-based filters (last week, last month, today) ✅ Query history tracking ✅ Export query history as PDF ✅ Export query history as TXT ✅ Share queries via WhatsApp & Facebook ✅ Interactive UI using Gradio

🧠 How It Works

The system follows these steps:

1️⃣ User enters a natural language request

Example:

Show active users who joined last month

2️⃣ The system detects:

Table name

Columns

Filters

Conditions

3️⃣ SQL query is generated safely:

SELECT * FROM users WHERE DATE(signup_date) >= DATE('now', '-1 month') AND status = 'active' LIMIT 10;

4️⃣ Query is stored in history for export or sharing.

🗂 Database Schema

The project assumes the following tables.

Users Table Column Type id INTEGER PRIMARY KEY name TEXT email TEXT signup_date DATE age INTEGER country TEXT status TEXT Orders Table Column Type id INTEGER PRIMARY KEY user_id INTEGER product_name TEXT amount REAL order_date DATE status TEXT Products Table Column Type id INTEGER PRIMARY KEY name TEXT price REAL category TEXT stock INTEGER Transactions Table Column Type id INTEGER PRIMARY KEY user_id INTEGER amount REAL date DATE type TEXT 🔐 Security Features

The system prevents dangerous SQL execution.

Blocked keywords:

DROP DELETE ALTER TRUNCATE INSERT UPDATE EXEC

Blocked characters:

;
/* */ xp_ sp_

If detected, the query is rejected.

📥 Export Features

Users can export generated queries.

PDF Export

Generates a professional report including:

User request

Generated SQL

Timestamp

Example file:

sql_queries_2026-03-07_10-35-20.pdf TXT Export

Creates a simple text history.

Example:

SQL Query History Report Generated: 2026-03-07

Query #1 User Request: Show active users Generated SQL: SELECT * FROM users WHERE status='active' 📱 Social Sharing

Users can share generated queries easily.

Supported platforms:

💬 WhatsApp 👍 Facebook

The system generates a shareable link automatically.

🖥 User Interface

The interface is built using Gradio Blocks.

UI Components:

Chat style query interface

SQL generation button

History clearing

PDF / TXT export

Social sharing buttons

Schema information panel

📦 Installation 1️⃣ Clone the repository git clone https://github.com/yourusername/sql-query-generator.git cd sql-query-generator 2️⃣ Install dependencies pip install gradio transformers torch black autopep8 reportlab requests 3️⃣ Run the application python app.py 🌐 Launch

When running, the app will launch a Gradio web interface.

Example output:

Running on local URL: http://127.0.0.1:7860 Running on public URL: https://xxxxx.gradio.live 📊 Example Queries

Example inputs supported:

Show all users Show active users Show users who joined last month List products with price Show orders above 500 Show transactions today Show inactive users 📁 Project Structure sql-query-generator/ │ ├── app.py ├── README.md ├── requirements.txt └── exports/ ├── sql_queries_.pdf └── sql_queries_.txt 🛠 Technologies Used

Python

Gradio

SQLite

ReportLab

Regex

JSON

Requests

📈 Future Improvements

Possible enhancements:

AI powered SQL generation using LLMs

Multi-database support (MySQL, PostgreSQL)

Query execution engine

Data visualization

Authentication system

Dashboard analytics

👨‍💻 Author

Developed for learning and demonstration of:

Natural Language Processing

SQL automation

Secure query generation

Interactive Python apps
