[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/Pnfi-TgX)
### Exercise: Bank System Implementation

#### Part 1: Bank Account Class
Create a class called `BankAccount` to represent a basic bank account.

1. **Attributes:**
   - `account_number`: The unique identifier for the account.
   - `balance`: The current balance of the account.
   - `owner_name`: The name of the account holder.

2. **Methods:**
   - `deposit(amount)`: Add funds to the account.
   - `withdraw(amount)`: Withdraw funds from the account.

Example Results:
```python

account = BankAccount("123456789", "Alice")
account.deposit(1000)
account.withdraw(500)
print("Account Number:", account.account_number)
print("Owner Name:", account.owner_name)
print("Current Balance:", account.balance)
```

#### Part 2: Savings Account Class
Create a subclass called `SavingsAccount` that inherits from `BankAccount`.

3. **Additional Method:**
   - `calculate_interest(rate)`: Calculate monthly interest on the balance based on the given interest rate.

Example Results:
```python

savings_account = SavingsAccount("987654321", "Bob")
savings_account.deposit(2000)
savings_account.calculate_interest(5)  # 5% annual interest rate
print("Account Number:", savings_account.account_number)
print("Owner Name:", savings_account.owner_name)
print("Current Balance with Interest:", savings_account.balance)
```

#### Part 3: Customer Class
Create a class called `Customer` to represent a bank customer.

4. **Attributes:**
   - `customer_id`: The unique identifier for the customer.
   - `name`: The name of the customer.
   - `accounts`: A list to store the customer's accounts.

5. **Method:**
   - `add_account(account)`: Add a new account to the customer's list.

Example Results:
```python

customer = Customer("C001", "Charlie")
account1 = BankAccount("111", "Checking")
account2 = SavingsAccount("222", "Savings")
customer.add_account(account1)
customer.add_account(account2)
print("Customer ID:", customer.customer_id)
print("Customer Name:", customer.name)
print("Customer's Accounts:", [acc.account_number for acc in customer.accounts])
```

#### Part 4: Bank Class
Create a class called `Bank` to represent a bank system.

6. **Attributes:**
   - `customers`: A list to store the bank's customers.

7. **Methods:**
   - `add_customer(customer)`: Add a new customer to the bank's list.
   - `find_customer_by_id(customer_id)`: Find a customer by their ID.

Example Results:
```python

bank = Bank()
bank.add_customer(customer)
found_customer = bank.find_customer_by_id("C001")
print("Found Customer Name:", found_customer.name if found_customer else "Not found")
```

#### Part 5: Transaction Logging
Extend the `BankAccount` class to log all transactions.

8. **Additional Method:**
   - `log_transaction(amount, transaction_type)`: Log each transaction along with a timestamp.

Example Results:
```python

account = BankAccount("123456789", "Alice")
account.deposit(1000)
account.withdraw(500)
print("Transaction Log:")
for transaction in account.transactions:
    print("Timestamp:", transaction[0])
    print("Transaction Type:", transaction[1])
    print("Amount:", transaction[2])
```
