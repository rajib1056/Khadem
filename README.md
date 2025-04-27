from flask import Flask, render_template, request, redirect, url_for
import sqlite3
from werkzeug.security import generate_password_hash, check_password_hash

app = Flask(__name__)

# SQLite ডাটাবেস সেটআপ
def init_db():
    conn = sqlite3.connect('monitoring_system.db')
    c = conn.cursor()
    # Users Table
    c.execute('''CREATE TABLE IF NOT EXISTS users (
                 id INTEGER PRIMARY KEY,
                 username TEXT UNIQUE NOT NULL,
                 password TEXT NOT NULL)''')
    # Institutions Table
    c.execute('''CREATE TABLE IF NOT EXISTS institutions (
                 id INTEGER PRIMARY KEY,
                 name TEXT NOT NULL,
                 description TEXT,
                 staff_id INTEGER)''')
    # Transactions Table
    c.execute('''CREATE TABLE IF NOT EXISTS transactions (
                 id INTEGER PRIMARY KEY,
                 institution_id INTEGER,
                 transaction_type TEXT NOT NULL,
                 amount REAL NOT NULL,
                 transaction_date TEXT NOT NULL,
                 comments TEXT)''')
    conn.commit()
    conn.close()

init_db()

@app.route('/')
def home():
    conn = sqlite3.connect('monitoring_system.db')
    c = conn.cursor()
    c.execute("SELECT * FROM institutions")
    institutions = c.fetchall()
    conn.close()
    return render_template('home.html', institutions=institutions)

@app.route('/add_institution', methods=['GET', 'POST'])
def add_institution():
    if request.method == 'POST':
        name = request.form['name']
        description = request.form['description']
        staff_id = request.form['staff_id']

        conn = sqlite3.connect('monitoring_system.db')
        c = conn.cursor()
        c.execute("INSERT INTO institutions (name, description, staff_id) VALUES (?, ?, ?)",
                  (name, description, staff_id))
        conn.commit()
        conn.close()
        return redirect(url_for('home'))

    return render_template('add_institution.html')

@app.route('/add_transaction/<int:institution_id>', methods=['GET', 'POST'])
def add_transaction(institution_id):
    if request.method == 'POST':
        transaction_type = request.form['transaction_type']
        amount = request.form['amount']
        transaction_date = request.form['transaction_date']
        comments = request.form['comments']

        conn = sqlite3.connect('monitoring_system.db')
        c = conn.cursor()
        c.execute("INSERT INTO transactions (institution_id, transaction_type, amount, transaction_date, comments) VALUES (?, ?, ?, ?, ?)",
                  (institution_id, transaction_type, amount, transaction_date, comments))
        conn.commit()
        conn.close()
        return redirect(url_for('home'))

    return render_template('add_transaction.html', institution_id=institution_id)

if __name__ == '__main__':
    app.run(debug=True)
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>প্রতিষ্ঠান তালিকা</title>
</head>
<body>
    <h2>প্রতিষ্ঠান তালিকা</h2>
    <ul>
        {% for institution in institutions %}
            <li>{{ institution[1] }} - <a href="{{ url_for('add_transaction', institution_id=institution[0]) }}">লেনদেন যোগ করুন</a></li>
        {% endfor %}
    </ul>
    <a href="{{ url_for('add_institution') }}">নতুন প্রতিষ্ঠান যোগ করুন</a>
</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>নতুন প্রতিষ্ঠান যোগ করুন</title>
</head>
<body>
    <h2>নতুন প্রতিষ্ঠান যোগ করুন</h2>
    <form method="POST">
        <label for="name">প্রতিষ্ঠানের নাম:</label>
        <input type="text" id="name" name="name" required><br><br>

        <label for="description">বর্ণনা:</label>
        <input type="text" id="description" name="description" required><br><br>

        <label for="staff_id">মনিটরিং খাদেমের আইডি:</label>
        <input type="number" id="staff_id" name="staff_id" required><br><br>

        <button type="submit">যো

গ করুন</button>
    </form>
</body>
</html>
<!DOCTYPE html>
<html lang="bn">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>লেনদেন যোগ করুন</title>
</head>
<body>
    <h2>লেনদেন যোগ করুন</h2>
    <form method="POST">
        <label for="transaction_type">লেনদেনের ধরন:</label>
        <input type="text" id="transaction_type" name="transaction_type" required><br><br>

        <label for="amount">পরিমাণ:</label>
        <input type="number" id="amount" name="amount" required><br><br>

        <
