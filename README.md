# Loan Eligibility Prediction Web App

A full-stack machine learning web application built with Flask that predicts whether a user is eligible for a loan. The project includes a secure authentication system, MySQL database integration, and a trained machine learning model for loan prediction.

---

# Features

* User registration and login system
* Password hashing using Flask-Bcrypt
* Session management using Flask-Login
* MySQL database integration with SQLAlchemy
* Loan eligibility prediction using a trained ML model
* Form validation with Flask-WTF
* Clean Flask routing structure
* Protected prediction route (login required)

---

# Tech Stack

## Backend

* Python
* Flask
* Flask-SQLAlchemy
* Flask-Login
* Flask-WTF
* Flask-Bcrypt

## Machine Learning

* Scikit-learn
* NumPy
* Pickle

## Database

* MySQL
* PyMySQL

---

# Project Structure

```bash
project/
│
├── app.py                 # Main Flask application
├── model.pkl              # Trained ML model
├── requirements.txt       # Project dependencies
│
├── templates/             # HTML templates
│   ├── home.html
│   ├── login.html
│   ├── register.html
│   └── predict.html
│
└── static/                # CSS, JS, images (optional)
```

---

# Installation

## 1. Clone the Repository

```bash
git clone https://github.com/your-username/loan-prediction-flask-app.git
cd loan-prediction-flask-app
```

---

## 2. Create Virtual Environment

### Windows

```bash
python -m venv venv
venv\Scripts\activate
```

### Linux / macOS

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 3. Install Dependencies

```bash
pip install -r requirements.txt
```

---

# MySQL Database Setup

## Create Database

Open MySQL and run:

```sql
CREATE DATABASE login_store;
```

---

## Update Database Credentials

In `app.py`, update this line according to your MySQL username and password:

```python
app.config['SQLALCHEMY_DATABASE_URI'] = 'mysql+pymysql://root:root@localhost/login_store'
```

Format:

```python
mysql+pymysql://USERNAME:PASSWORD@localhost/DATABASE_NAME
```

---

# Running the Application

Start the Flask server:

```bash
python app.py
```

The app will run at:

```bash
http://127.0.0.1:5000/
```

---

# How the Application Works

## Authentication Flow

1. User registers using the registration form
2. Password is securely hashed before storage
3. User logs in using credentials
4. Flask-Login manages authenticated sessions
5. Only logged-in users can access the prediction page

---

## Loan Prediction Flow

1. User enters financial/input details
2. Input data is converted into NumPy arrays
3. Trained ML model (`model.pkl`) processes the data
4. Model predicts eligibility:

   * `0` → Not Eligible
   * `1` → Eligible
5. Result is displayed on the webpage

---

# Dependencies

Main libraries used in this project:

```txt
Flask
Flask-Bcrypt
Flask-Login
Flask-SQLAlchemy
Flask-WTF
NumPy
Scikit-learn
PyMySQL
WTForms
```

---

# Security Features

* Password hashing using Bcrypt
* Secret key generation using Python `secrets`
* Protected routes using `@login_required`
* Form validation with WTForms
* Session-based authentication

---

# Example Routes

| Route       | Description          |
| ----------- | -------------------- |
| `/`         | Home page            |
| `/register` | User registration    |
| `/login`    | User login           |
| `/logout`   | Logout user          |
| `/predict`  | Loan prediction page |

---

# Future Improvements

* Add responsive UI design
* Add model confidence score
* Deploy on Render/Heroku/AWS
* Add email verification
* Add admin dashboard
* Store prediction history
* Add API endpoints
* Improve frontend styling

---

# Common Errors and Fixes

## MySQL Connection Error

Make sure:

* MySQL server is running
* Database exists
* Username/password are correct
* `PyMySQL` is installed

---

## ModuleNotFoundError

Run:

```bash
pip install -r requirements.txt
```

---

## model.pkl Not Found

Ensure `model.pkl` exists in the root project directory.

---

# Deployment Suggestions

You can deploy this project using:

* Render
* Railway
* Heroku
* PythonAnywhere
* AWS EC2

For production deployment:

* Use environment variables
* Disable debug mode
* Use Gunicorn or Waitress
* Store secrets securely

