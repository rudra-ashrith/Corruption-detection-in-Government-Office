# AI-Based Corruption Detection in Government Transactions

An AI-based web application for identifying potentially suspicious transactions in government schemes using Flask, SQLite, SQLAlchemy, and a Random Forest machine learning model.

The system allows administrators and officers to manage government schemes and transactions while automatically calculating a corruption-risk probability for each transaction.

> **Note:** This project is a prototype. The current machine-learning model is trained and evaluated using synthetically generated transaction data. Therefore, the evaluation results should not be interpreted as real-world corruption-detection accuracy.

---

## Features

### Authentication
- Admin login and logout
- Officer login
- Session-based authentication
- Password hashing using Werkzeug
- Role-based access

### Government Scheme Management
- Add government schemes
- Define allocated scheme amounts
- View available schemes

### Transaction Management
- Add government transactions
- Select a government scheme
- Record beneficiary information
- Record expected and transferred amounts
- Record transaction location
- Record transaction date
- Record payment delay
- Automatically calculate corruption probability

### Corruption Detection
The Random Forest model analyzes transaction-related features and generates a probability indicating whether a transaction may be suspicious.

Transactions crossing the configured detection threshold are flagged as:

**Corruption Detected**

### Dashboard
The dashboard provides:
- Total schemes
- Total transactions
- Detected corruption cases
- Corruption distribution by location
- Transaction risk/corruption probability
- Interactive charts

---

## Machine Learning

The project uses a **Random Forest Classifier** for corruption-risk prediction.

### Model Input Features

The model uses transaction-related features including:

- Scheme ID
- Expected amount
- Transferred amount
- Amount difference
- Delay in days
- Transaction location

### Training Pipeline

The ML training pipeline:

1. Generates a synthetic government transaction dataset
2. Simulates different transaction-risk patterns
3. Calculates risk indicators
4. Encodes categorical location data
5. Splits the dataset into training and testing sets
6. Trains a Random Forest classifier
7. Evaluates the model
8. Saves the trained model bundle

The trained model is stored as:

```text
models/
└── corruption_model.pkl