# 🏥 Hospital Bed Management System

A lightweight **Flask + MySQL** web app to manage hospital bed availability and allow patients to book COVID-related beds. Includes patient login, hospital user portal, and a simple admin panel.

## ✨ Features

- 👤 Patient signup & login (using SRFID + DOB password)
- 🏥 Hospital user dashboard to update bed counts
- 🛠️ Admin panel to add/manage hospital users
- 🛏️ Book Normal / ICU / Ventilator beds
- 📊 MySQL stored procedures for fast reporting

## 📸 Screenshots

### 🟦 1. Home Page  
<img src="https://github.com/user-attachments/assets/079d20be-3e86-4f59-a08f-f987418fb0e1" width="700"/>

### 🟩 2. Admin Login  
<img src="https://github.com/user-attachments/assets/3e3d0339-a9d6-47ab-8651-4fba15595735" width="700"/>

### 🟨 3. Bed Availability Status  
<img src="https://github.com/user-attachments/assets/efb8bde6-8326-4bb9-a4d8-beb4d024ffce" width="700"/>

### 🟧 4. Book Bed Slot  
<img src="https://github.com/user-attachments/assets/899886fa-0c01-486a-a510-804d717ff06c" width="700"/>


## 🗂️ Project Structure

```
main.py        → Flask routes
covid.sql      → MySQL schema + stored procedures
templates/     → HTML (Jinja2) views
static/        → CSS, JS, assets
```

## 🔧 Requirements

- Python 3.8+
- MySQL Server
- Packages: Flask, Flask-Login, Flask-SQLAlchemy, mysql-connector-python

## 🚀 Quick Setup (Windows)

1. Create & activate virtual environment

```
python -m venv venv
venv\Scripts\activate
```

2. Install dependencies

```
pip install Flask Flask-Login Flask-SQLAlchemy mysql-connector-python
```

3. Import the database

```
mysql -u root -p covid < covid.sql
```

4. Update DB credentials in `main.py` if needed:

```
mysql+mysqlconnector://root:@localhost/covid
```

## ▶️ Run the App

```
python main.py
```

Then open 👉 **http://127.0.0.1:5000/**

## 🔗 Key Routes

- `/login`, `/signup` — patient login
- `/hospitallogin` — hospital user
- `/admin` — admin login (default: `admin`/`admin`)
- `/addhospitalinfo` — update bed counts
- `/slotbooking` — book a bed

## 💡 Notes

- Replace default admin credentials for real deployment
- Some queries use raw SQL — consider full SQLAlchemy migration later
