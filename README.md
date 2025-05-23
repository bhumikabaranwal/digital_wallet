# Digital Wallet System with Fraud Detection

## Overview
A secure digital wallet backend system built with Flask that enables user registration, virtual cash management, and fraud detection with RESTful APIs.

## Features

### 1. User Authentication & Sessions
- Secure password storage using bcrypt
- JWT-based session management
- Protected routes for all sensitive operations

### 2. Wallet Operations
- Deposit, withdraw, and transfer virtual cash
- Support for multiple currencies (USD, EUR, GBP, INR)
- Detailed transaction history per user

### 3. Transaction Processing & Validations
- Atomic and secure transaction handling
- Input validations (e.g., overdraft prevention, non-negative amounts)

### 4. Fraud Detection
- Flags:
  - Sudden large withdrawals
  - Rapid multiple transfers
  - IP address changes
- Logs suspicious activity
- Daily scheduled fraud scan job

### 5. Admin Reporting APIs
- View flagged transactions
- (Extensible) endpoints for balance reports and top users
- Soft deletion for users and transactions

### Bonus Features
- `apscheduler` job for daily fraud scans
- Soft delete using `is_deleted` flags
- Mock email alert system (via logs)

## Tech Stack
- Python, Flask
- SQLAlchemy (SQLite)
- JWT (flask-jwt-extended)
- APScheduler
- Swagger (via flasgger)

## API Documentation
Interactive API documentation available via Swagger/Postman:
- Located in `/docs/` directory (YAML files)
- Endpoints include `/register`, `/login`, `/withdraw`, `/transfer`, `/transactions`, `/admin/*`

## Project Structure
digital_wallet/ ├── app/ │   ├── init.py         # Flask app factory │   ├── models.py           # SQLAlchemy models │   ├── services.py         # Fraud detection & scheduled jobs │   ├── routes.py           # API endpoints │   └── utils.py            # (Optional utility functions) ├── config.py               # Environment configs ├── requirements.txt        # Required packages ├── run.py                  # App runner ├── tests/                  # Test cases └── docs/                   # Swagger API YAMLs

## Running the App
```bash
pip install -r requirements.txt
export FLASK_APP=run.py
flask run


Author

Bhumika

License

MIT
