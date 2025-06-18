# Smart Expense Tracker 💰

A simple yet powerful command-line expense tracking application built with Python. Track your daily expenses, calculate totals, and maintain a detailed log of your spending habits.

## ✨ Features

- **Add Single Expenses**: Record individual expenses with amount and description
- **Add Multiple Expenses**: Batch add multiple expenses for a single day
- **Flexible Date Input**: Support for today, yesterday, or custom dates (YYYY-MM-DD format)
- **Comprehensive Reporting**: Calculate expenses for:
  - Specific days
  - Entire months
  - Last 7 days (weekly)
  - Custom number of days
  - Total expenses to date
- **Automatic Backup**: Automatic backup of expense data
- **JSON Storage**: Data stored in structured JSON format for easy access and portability

## 🚀 Quick Start

### Prerequisites

- Python 3.6 or higher
- No additional dependencies required (uses only Python standard library)

### Installation

1. **Clone or download the project files**
   ```bash
   git clone <repository-url>
   cd Smart-Expense-Tracker
   ```

2. **Run the application**
   ```bash
   python main.py
   ```

The application will automatically create the required `ignore_dir` folder and `expense_log_test.json` file on first run.

## 📖 Usage Guide

### Main Menu

When you start the application, you'll see:
```
Are you adding expense or want to calculate total:
```

**Options:**
- `expense`, `ex`, or `e` - Add new expenses
- `total` or `t` - Calculate expense totals

### Adding Expenses

#### Single Expense
1. Choose `expense` from main menu
2. Select `single` or `s` for single expense
3. Enter the date (YYYY-MM-DD, `today`, or `yesterday`)
4. Enter the amount spent
5. Enter a description of the expense

#### Multiple Expenses (Daily)
1. Choose `expense` from main menu
2. Select `day` or `d` for daily expenses
3. Enter the date (YYYY-MM-DD, `today`, or `yesterday`)
4. Add multiple expenses one by one
5. Answer `yes`/`y`/`true` to add more expenses, or `no` to finish

### Calculating Totals

Choose `total` from main menu, then select your calculation type:

- **`all`** - Total expenses to date
- **`day` or `d`** - Specific day expenses
- **`month` or `m`** - Monthly expenses (enter month name or number)
- **`week` or `w`** - Last 7 days expenses
- **`last` or `l`** - Custom number of days (you'll be prompted for the number)

## 📁 File Structure

```
Smart Expense Tracker/
├── main.py              # Main application entry point
├── calc_total.py        # Expense calculation functions
├── file_update.py       # File operations and expense addition
├── ignore_dir/          # Data storage directory
│   ├── expense_log_test.json      # Main expense data file
│   └── expense_log_test_bkp.json  # Automatic backup file
└── README.md            # This file
```

## 💾 Data Storage

Expenses are stored in JSON format in `ignore_dir/expense_log_test.json`:

```json
{
  "2024-01-15": [
    {
      "Amount": 500,
      "Description": "Groceries"
    },
    {
      "Amount": 200,
      "Description": "Transport"
    }
  ]
}
```

## 🔧 Configuration

### File Paths
The application uses relative paths for data storage. If you need to change the storage location, modify the `WRITEFILE` variable in both `calc_total.py` and `file_update.py`:

```python
WRITEFILE = "path/to/your/expense_log_test.json"
```

## 📝 Example Usage

### Adding a Daily Expense
```
Are you adding expense or want to calculate total: expense
Enter expense type, whether a complete day expense or single expense: single
Enter which day it should be added to: today
Enter amount you have spent Rs ₹: 150
Enter what you spent for: Lunch
```

### Calculating Weekly Expenses
```
Are you adding expense or want to calculate total: total
Specific date expense or month, week or last few days or total expense till date: week
Total amount spent on last 7 is '1250' Rupees.
```

## 🛡️ Backup System

The application automatically creates backups of your expense data in `ignore_dir/expense_log_test_bkp.json` whenever you add new expenses.

## 🤝 Contributing

Feel free to contribute to this project by:
- Reporting bugs
- Suggesting new features
- Submitting pull requests

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🆘 Troubleshooting

### Common Issues

1. **File not found error**: Make sure you're running the script from the project directory
2. **JSON decode error**: The expense file might be corrupted. Check the backup file in `ignore_dir/`
3. **Permission error**: Ensure you have write permissions in the project directory

### Reset Data
To start fresh, simply delete the `ignore_dir` folder and run the application again.

---

**Happy Expense Tracking! 💸**
