# AI47LAbs 

# Django Google Authenticated Task Manager

## Overview  
This is a simple task management web application built using Django, enabling users to manage their personal tasks after logging in via Google Authentication. Admin users can manage OAuth credentials and invite users through email registration links.

---

## Features  

### **1. Google Authentication**  
- Users can log in using their Google account.  
- Secure and easy-to-use authentication mechanism.

### **2. Task Management**  
- **Create, Read, Update, Delete (CRUD)** operations for tasks.  
- Each task includes:  
  - **Title**  
  - **Description**

### **3. Admin Panel**  
- Admins can:  
  - Add and manage Google OAuth keys.  
  - Invite new users by sending email invitations with registration links.

---

## Technologies Used  

- **Backend:** Django 4.x  
- **Authentication:** Google OAuth 2.0 via `social-auth-app-django`  
- **Frontend:** HTML, CSS, Bootstrap  
- **Database:** SQLite (default, can be switched to PostgreSQL/MySQL)  

---

## Installation  

### Prerequisites:  
1. Python 3.x  
2. Pip  
3. Virtual environment (recommended: `venv`)  
4. Google OAuth credentials (Client ID and Secret). Create credentials [here](https://console.cloud.google.com/apis/credentials).  

### Steps:  

1. Download the project folder and navigate to it:  
   ```bash
   cd django-task-manager
   ```

2. Create and activate a virtual environment:  
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: .\venv\Scripts\activate
   ```

3. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```

4. Set up the database:  
   ```bash
   python manage.py makemigrations
   python manage.py migrate
   ```

5. Configure Google OAuth:  
   - Add your Google OAuth Client ID and Secret to the `settings.py` file:
     ```python
     SOCIAL_AUTH_GOOGLE_OAUTH2_KEY = '<your-client-id>'
     SOCIAL_AUTH_GOOGLE_OAUTH2_SECRET = '<your-client-secret>'
     ```
   - Add a redirect URI in the Google API Console:
     ```
     http://127.0.0.1:8000/complete/google-oauth2/
     ```

6. Start the development server:  
   ```bash
   python manage.py runserver
   ```

7. Open the app in your browser:  
   ```
   http://127.0.0.1:8000/
   ```

---

## Usage  

1. **Login:** Use your Google account to log in.  
2. **Manage Tasks:**  
   - Add tasks by clicking the "Create Task" button.  
   - Edit or delete tasks as needed.  
3. **Admin Panel:**  
   - Access the admin interface at `/admin` for advanced management features.  

---

## Directory Structure  

```plaintext
django-task-manager/
├── tasks/                     # Task management app
│   ├── migrations/            # Database migrations
│   ├── templates/             # HTML templates
│   ├── static/                # Static files (CSS, JS)
│   ├── views.py               # View logic
│   ├── models.py              # Data models
│   └── urls.py                # App-specific routes
├── project_name/              # Main Django project
│   ├── settings.py            # Project settings
│   ├── urls.py                # Project routes
├── manage.py                  # Django CLI entry point
├── requirements.txt           # Dependencies
└── README.md                  # Project documentation
```

---

## Future Enhancements  

- Add due dates and reminders for tasks.  
- Enable file attachments for tasks.  
- Support for task prioritization and tagging.  
- Deploy to a cloud platform (e.g., AWS, Heroku).  
