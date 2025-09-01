# Tax - Financial Management System

A comprehensive desktop application for personal financial management with tax calculations, built using Python and Tkinter.

## 📋 Overview

This Financial Management System is designed to help users track their financial transactions while automatically calculating applicable taxes including GST and Income Tax. The application provides an intuitive interface for transaction management, financial summaries, and educational content about tax structures.

## ✨ Features

### 🔐 User Authentication
- **User Registration**: Create new user accounts with username and password
- **Secure Login**: Access your personal financial data with authentication
- **Multi-user Support**: Each user has their own isolated transaction data

### 💰 Transaction Management
- **Add Transactions**: Record both credit and debit transactions
- **Transaction Categories**: Organize transactions by class (Food, Groceries, Medical, Electronics, etc.)
- **Automatic Tax Calculations**: 
  - **GST Calculation**: Category-specific rates (5% for groceries, 12% for food/medical, 18% for electronics/alcohol)
  - **Income Tax Calculation**: Based on Indian tax slabs for FY 2024-25
- **Transaction History**: View all transactions with detailed breakdowns

### 📊 Financial Analytics
- **Comprehensive Summary**: View all transactions in a structured table format
- **Tax Totals**: Track total GST and Income Tax across all transactions
- **Visual Analytics**: Pie charts showing credit/debit distribution by category
- **Transaction Management**: Delete unwanted transactions

### 📚 Financial Education
- **Tax Literacy**: Built-in reference for Indian Income Tax slabs
- **Educational Content**: Learn about tax structures and financial planning

## 🛠️ Technical Stack

- **Language**: Python 3.x
- **GUI Framework**: Tkinter
- **Database**: SQLite3
- **Data Visualization**: Matplotlib
- **Build Tool**: PyInstaller

## 📁 Project Structure

```
Tax/
├── tax/
│   ├── tax_app.py          # Main application file
│   ├── tax_app.spec        # PyInstaller configuration
│   ├── users.db            # User authentication database
│   ├── transactions.db     # Transaction data database
│   ├── build/              # Build artifacts
│   └── dist/               # Distribution files
│       └── tax_app.exe     # Standalone executable
```

## 🚀 Getting Started

### Prerequisites

- Python 3.7 or higher
- Required Python packages:
  ```bash
  pip install tkinter matplotlib sqlite3
  ```

### Installation & Running

1. **Clone the repository**:
   ```bash
   git clone https://github.com/mananjp/Tax.git
   cd Tax/tax
   ```

2. **Run the application**:
   ```bash
   python tax_app.py
   ```

3. **Alternative - Use the executable** (Windows):
   - Navigate to `tax/dist/` folder
   - Run `tax_app.exe` directly

### First Time Setup

1. **Register a new account**: Click "Register" on the login screen
2. **Create credentials**: Enter your desired username and password
3. **Login**: Use your credentials to access the application
4. **Start tracking**: Begin adding your financial transactions

## 💡 Usage Guide

### Adding Transactions
1. Select transaction type (Credit/Debit)
2. Enter transaction class (e.g., "food", "groceries", "electronics")
3. Input the transaction amount
4. Click "Add Transaction"

### Viewing Financial Summary
1. Click "View Summary" from the dashboard
2. Review all transactions with calculated taxes
3. Check total GST and Income Tax amounts
4. Use "Show Pie Charts" for visual analysis

### Tax Calculations

**GST Rates by Category**:
- Groceries: 5%
- Food & Medical: 12%
- Electronics & Alcohol: 18%
- Default: 18%

**Income Tax Slabs (FY 2024-25)**:
- ₹0 - ₹3,00,000: 0%
- ₹3,00,001 - ₹7,00,000: 5%
- ₹7,00,001 - ₹10,00,000: 10%
- ₹10,00,001 - ₹12,00,000: 15%
- ₹12,00,001 - ₹15,00,000: 20%
- ₹15,00,001 and above: 30%

## 🗄️ Database Schema

### Users Table
```sql
CREATE TABLE users (
    username TEXT PRIMARY KEY,
    password TEXT
)
```

### Transactions Table
```sql
CREATE TABLE transactions (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    user_id TEXT,
    class TEXT,
    amount REAL,
    gst REAL,
    income_tax REAL,
    total REAL,
    transaction_type TEXT,
    timestamp TEXT
)
```

## 🔧 Development

### Building the Executable
The project includes PyInstaller configuration for creating a standalone executable:

```bash
pyinstaller tax_app.spec
```

This will generate an executable in the `dist/` folder.

### Key Features Implementation
- **SQLite Integration**: Persistent data storage for users and transactions
- **Real-time Calculations**: Dynamic tax computation based on transaction details
- **Cross-platform GUI**: Tkinter ensures compatibility across operating systems
- **Data Visualization**: Matplotlib integration for financial insights

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request. For major changes, please open an issue first to discuss what you would like to change.

## 📄 License

This project is available under the MIT License. See the LICENSE file for more details.

## 🐛 Issues

If you encounter any problems or have suggestions for improvements, please create an issue on the GitHub repository.

## 📧 Contact

**Author**: mananjp  
**Repository**: [https://github.com/mananjp/Tax](https://github.com/mananjp/Tax)

---

*Built with ❤️ for better financial management and tax awareness*
