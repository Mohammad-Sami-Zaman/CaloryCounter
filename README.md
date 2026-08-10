# 🍎 Sami_07_CaloryCounter

A Django-based **Calorie Counter and BMR Management System** that allows users to create accounts, manage their health profiles, calculate daily calorie requirements, and track consumed calories.

## 🌐 Live Demo

**Live Application:**
[Calory Counter — Live Demo](https://calorycounter-v8gr.onrender.com?utm_source=chatgpt.com)

---

## 📌 Project Overview

**Sami_07_CaloryCounter** is a web-based calorie management application developed using **Python and Django**.

The system allows users to maintain their personal information such as:

* Name
* Age
* Gender
* Height
* Weight

Using these details, the application calculates the user's **Basal Metabolic Rate (BMR)** and helps the user monitor daily calorie consumption.

Users can also add, edit, and delete consumed food/calorie records.

---

## ✨ Features

### 👤 User Management

* User registration
* User login and logout
* Authentication-protected pages
* User profile management
* Profile update functionality

### 📏 Health Profile

Users can provide:

* Name
* Age
* Gender
* Height
* Weight

The application uses these values for BMR calculation.

### 🔥 BMR Calculation

The application calculates the user's estimated **Basal Metabolic Rate (BMR)** based on:

* Age
* Gender
* Height
* Weight

### 🍚 Calorie Tracking

Users can:

* Add consumed food/calorie information
* View calorie records
* Edit calorie records
* Delete calorie records
* Monitor consumed calories

### 📊 Dashboard

The dashboard provides users with an overview of their calorie information and profile data.

### 🔐 Authentication

Protected features require the user to log in before accessing them.

### 🛠️ Django Admin

The project includes Django's built-in administration panel for managing application data.

---

## 🧮 BMR Calculation

The application uses the **Harris-Benedict equation**.

### Male

```text
BMR =
66.47
+ (13.75 × weight)
+ (5.003 × height)
- (6.755 × age)
```

### Female

```text
BMR =
655.1
+ (9.563 × weight)
+ (1.85 × height)
- (4.676 × age)
```

### Units

| Measurement | Unit             |
| ----------- | ---------------- |
| Height      | Centimeters (cm) |
| Weight      | Kilograms (kg)   |
| Age         | Years            |
| Calories    | kcal             |

For example, a height of **5 feet 7 inches** should be entered approximately as:

```text
170.18 cm
```

---

## 🏗️ Technology Stack

### Backend

* Python
* Django
* Django Authentication
* Django ORM

### Frontend

* HTML5
* CSS3
* Bootstrap
* Django Templates
* Crispy Forms

### Database

* SQLite for local development
* PostgreSQL for production

### Production

* Gunicorn
* WhiteNoise
* Render

---

## 📂 Project Structure

```text
Sami_07_CaloryCounter/
│
├── Sami_07_CaloryCounter/
│   ├── __init__.py
│   ├── settings.py
│   ├── urls.py
│   ├── asgi.py
│   └── wsgi.py
│
├── calory_app/
│   ├── migrations/
│   ├── templates/
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
│
├── manage.py
├── requirements.txt
├── build.sh
├── render.yaml
├── .gitignore
└── README.md
```

---

## ⚙️ Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/Sami_07_CaloryCounter.git
```

Move into the project:

```bash
cd Sami_07_CaloryCounter
```

---

### 2. Create a virtual environment

Windows:

```bash
python -m venv myEnv
```

Activate it:

```bash
myEnv\Scripts\activate
```

Linux/macOS:

```bash
python3 -m venv myEnv
source myEnv/bin/activate
```

---

### 3. Install dependencies

```bash
pip install -r requirements.txt
```

---

### 4. Run migrations

```bash
python manage.py migrate
```

---

### 5. Create an admin account

```bash
python manage.py createsuperuser
```

Follow the instructions to create your administrator account.

---

### 6. Run the development server

```bash
python manage.py runserver
```

Open:

```text
http://127.0.0.1:8000/
```

---

## 🔐 Environment Variables

For production, sensitive configuration should be stored in environment variables.

Example:

```env
SECRET_KEY=your-secret-key
DEBUG=False
DATABASE_URL=your-postgresql-database-url
```

Do not commit secret keys or database credentials to GitHub.

---

## 🚀 Render Deployment

The project is configured for deployment on **Render**.

### Build command

```bash
./build.sh
```

The build script performs:

```bash
pip install -r requirements.txt
python manage.py collectstatic --no-input
python manage.py migrate --no-input
```

### Start command

```bash
gunicorn Sami_07_CaloryCounter.wsgi:application
```

### Production Database

The deployed application uses **PostgreSQL** through the `DATABASE_URL` environment variable.

### Static Files

Static files are served using **WhiteNoise**.

---

## 🛡️ Security Configuration

Production configuration includes:

* `DEBUG=False`
* Environment-based `SECRET_KEY`
* Render hostname configuration
* CSRF trusted origins
* PostgreSQL database
* WhiteNoise static-file handling

---

## 📝 Main Application Flow

```text
             ┌─────────────────┐
             │      User       │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Register/Login  │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │  User Profile   │
             │ Age             │
             │ Gender          │
             │ Height          │
             │ Weight          │
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │  BMR Calculation│
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │ Calorie Tracking│
             └────────┬────────┘
                      │
                      ▼
             ┌─────────────────┐
             │    Dashboard    │
             └─────────────────┘
```

---

## 🍽️ Example

A user can enter:

```text
Age:       24
Gender:    Male
Height:    170.18 cm
Weight:    95 kg
```

The application then uses the profile information to calculate the user's BMR.

The user can subsequently record consumed calories such as:

```text
Food: Rice
Calories: 260 kcal
```

and manage the record from the calorie tracking section.

---

## 🔮 Future Improvements

Possible future improvements include:

* Food database integration
* Automatic calorie calculation from food quantity
* BMI calculation
* Daily calorie goals
* Weekly/monthly calorie charts
* Food search functionality
* Nutrition tracking
* Protein, carbohydrate, and fat tracking
* REST API
* Mobile application
* Cloud image storage
* Email notifications
* Password reset functionality

---

## 👨‍💻 Developer

**Mohammad Sami Zaman**

### Focus

* Python
* Django
* Web Development
* Software Development

---

## 📄 License

This project is developed for educational and portfolio purposes.

You may modify and improve the project for learning and personal use.

---

## ⭐ Support

If you find this project useful, consider giving the repository a ⭐ on GitHub.

---

## 🔗 Project Links

**Live Application:**
[https://calorycounter-v8gr.onrender.com](https://calorycounter-v8gr.onrender.com?utm_source=chatgpt.com)

**GitHub Repository:**
Add your GitHub repository URL here.
