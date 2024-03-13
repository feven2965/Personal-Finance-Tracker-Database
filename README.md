# Personal Finance Tracker Database

## Description:
This database is designed to help users track their personal finances by recording transactions, managing budgets, and categorizing expenses and income. It includes tables for transactions, categories, accounts, budgets, and recurring transactions.

## Usage:
Users can use this database to:

- Record transactions: Insert new entries into the Transactions table to track expenses and income.
- Categorize transactions: Assign each transaction to a category to organize and analyze spending habits.
- Manage accounts: Add new accounts or update existing ones in the Accounts table to keep track of various financial accounts.
- Allocate budgets: Set up budget allocations in the Budget table to plan and monitor spending in different categories.
- Set up recurring transactions: Add recurring transactions in the RecurringTransaction table to automate regular payments or income.

## Queries:
Users can perform the following queries to retrieve and analyze financial data:

1. **Total Expenses per Category:**
```sql
SELECT c.category_name, SUM(t.amount) AS total_expenses
FROM Transactions t
JOIN Categories c ON t.category_id = c.category_id
WHERE c.category_type = 'expense'
GROUP BY c.category_name;
```

2. **Monthly Income Summary:**
```sql
SELECT MONTH(t.date) AS month, YEAR(t.date) AS year, SUM(t.amount) AS total_income
FROM Transactions t
JOIN Categories c ON t.category_id = c.category_id
WHERE c.category_type = 'income'
GROUP BY MONTH(t.date), YEAR(t.date);
```

## Updating the Database:
To update the database:
1. Use SQL `INSERT` statements to add new transactions, categories, accounts, budgets, or recurring transactions.
2. Use SQL `UPDATE` statements to modify existing records as needed.
3. Ensure data integrity by following foreign key constraints and maintaining consistency across tables.

## Notes:
- Always backup the database before making significant changes.
- Regularly review and update budget allocations to reflect changing financial goals and priorities.
- Keep track of recurring transactions to avoid duplicate entries and ensure accurate financial planning.
