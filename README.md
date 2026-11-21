# 💰 Personal Finance Management Portal

A responsive full-stack web application designed to simplify personal financial management by allowing users to track income, monitor expenses, organise transactions and visualise their spending patterns through an interactive dashboard.

## 📌 Project Overview

Managing personal finances can become difficult when income and expenses are recorded manually across different notebooks or spreadsheets. This project provides a centralised platform where users can maintain their financial records, categorise transactions and monitor their overall financial position.

The application combines a responsive frontend, a Python Flask backend and an SQLite database to provide a lightweight financial tracking solution.

## ✨ Key Features

### 🔐 User Authentication
- User registration and login.
- Password hashing for secure credential storage.
- Session-based authentication.
- User-specific financial records.

### 💸 Transaction Management
- Add income and expense transactions.
- View transaction history.
- Delete existing transactions.
- Assign categories to financial records.
- Record payment methods such as UPI, Cash, Card and Net Banking.

### 📊 Financial Dashboard
- Automatically calculate total income.
- Calculate total expenses.
- Display the current net balance.
- View category-wise expense distribution.
- Interactive charts using Chart.js.

### 📱 Responsive Interface
- Responsive layouts using Bootstrap 5.
- Dashboard cards and transaction tables.
- Interactive forms and navigation.
- Designed for desktop, tablet and mobile screens.

## 🛠️ Technology Stack

| Component | Technology | Purpose |
|---|---|---|
| Frontend | HTML5 | Page structure |
| Styling | CSS3 | User interface styling |
| Framework | Bootstrap 5 | Responsive layouts |
| Client-side scripting | JavaScript (ES6+) | Dynamic interactions |
| Data visualisation | Chart.js | Expense analytics |
| Backend | Python 3 | Application logic |
| Backend framework | Flask | Routing and API development |
| Security | Werkzeug Security | Password hashing and verification |
| Database | SQLite3 | Relational data storage |
| Deployment server | Gunicorn | WSGI application server |
| Version control | Git and GitHub | Source code management |
| Deployment platform | Render | Cloud deployment |

## 🏗️ System Architecture

The application follows a three-layer architecture:

1. **Presentation Layer:** HTML, CSS, Bootstrap and JavaScript provide the user interface.
2. **Application Layer:** Flask handles authentication, sessions, business logic and API requests.
3. **Database Layer:** SQLite stores user accounts, categories and financial transactions.

### Application Flow

```text
          USER
            |
            v
      WEB INTERFACE
    HTML / CSS / JS
            |
            v
       FLASK SERVER
   Authentication & APIs
            |
            v
      SQLITE DATABASE
   Users / Categories /
       Transactions
            |
            v
    FINANCIAL SUMMARY
            |
            v
   CHARTS & DASHBOARD
```

## 🗄️ Database Design

The database consists of three principal relational tables:

### 1. Users
Stores registered user information.

| Field | Description |
|---|---|
| user_id | Primary key |
| username | Username |
| email | Unique email address |
| password_hash | Hashed password |
| created_at | Account creation timestamp |

### 2. Categories
Stores transaction categories associated with users.

| Field | Description |
|---|---|
| category_id | Primary key |
| category_name | Category name |
| icon_url | Optional category icon |
| user_id | Foreign key referencing users |

### 3. Transactions
Stores income and expense records.

| Field | Description |
|---|---|
| transaction_id | Primary key |
| user_id | Foreign key referencing users |
| category_id | Foreign key referencing categories |
| type | INCOME or EXPENSE |
| amount | Transaction amount |
| date | Transaction date |
| description | Optional description |
| payment_method | Payment method |

## 🔌 API Overview

The application uses Flask API endpoints to communicate between the frontend and backend.

| HTTP Method | Endpoint | Function |
|---|---|---|
| GET | `/api/categories` | Retrieve transaction categories |
| GET | `/api/transactions` | Retrieve user transactions |
| POST | `/api/transactions` | Create a transaction |
| DELETE | `/api/transactions` | Delete a transaction |

The backend uses the authenticated user's session to associate operations with the relevant account.

## 📂 Project Structure

```text
Personal-Finance-Management-Portal/
│
├── app.py
│   └── Main Flask application and API routes
│
├── database.py
│   └── SQLite connection and database initialization
│
├── requirements.txt
│   └── Python dependencies
│
├── Procfile
│   └── Deployment configuration
│
├── templates/
│   ├── index.html
│   └── login.html
│
├── static/
│   └── app.js
│
└── .gitignore
```

## 🚀 Getting Started

Follow these steps to set up the project locally.

### Prerequisites

Make sure you have installed:

- Python 3
- pip (Python package manager)
- Git
- A modern web browser

### 1. Clone the Repository

```bash
git clone <YOUR_GITHUB_REPOSITORY_URL>
```

### 2. Navigate to the Project Directory

```bash
cd Personal-Finance-Management-Portal
```

### 3. Create a Virtual Environment

```bash
python -m venv venv
```

Activate it on Windows:

```bash
venv\Scripts\activate
```

On Linux or macOS:

```bash
source venv/bin/activate
```

### 4. Install Dependencies

```bash
pip install -r requirements.txt
```

### 5. Configure the Application

Check the Flask configuration in `app.py`. Set a secure secret key for session management before running the application. Keep production credentials out of the public repository.

### 6. Run the Application

```bash
python app.py
```

When the Flask development server starts, open the local address displayed in your terminal, commonly:

```text
http://127.0.0.1:5000/
```

*Note: The exact startup command and configuration depend on the application's existing Flask entry point.*

## 🧮 Financial Calculations

The dashboard uses transaction records to calculate the user's financial summary.

**Total Income**

```text
Total Income = Sum of all income transactions
```

**Total Expenses**

```text
Total Expenses = Sum of all expense transactions
```

**Net Balance**

```text
Net Balance = Total Income - Total Expenses
```

**Category-wise Spending**

Expense records are grouped by category to calculate the contribution of each category to overall expenditure.

## 🔮 Future Enhancements

Potential improvements to the application include:

- Migration from SQLite to PostgreSQL.
- Monthly and yearly financial reports.
- Export transactions to CSV and PDF.
- Custom category-based budget limits.
- Automated spending alerts.
- Secure email-based password recovery.
- Advanced analytics and spending trends.
- Automated testing for authentication and transaction operations.

## 🎯 Learning Outcomes

This project provides practical exposure to:

- Full-stack web application development.
- Frontend and backend integration.
- Flask routing and REST API concepts.
- Relational database design and SQL.
- Authentication and session management.
- Password hashing and application security.
- Financial data processing and aggregation.
- Interactive data visualisation.
- Git, GitHub and deployment workflows.

## 👨‍💻 Author

**Rajdeep Sorout**  
B.Tech – Computer Science and Engineering (Data Science)

## 📄 License

A license has not yet been specified for this project. Add an appropriate license before permitting third-party reuse.

---

⭐ **If you find this project interesting, consider giving the repository a star!**
