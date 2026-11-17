# Mini Project 5: Basic ATM System

## Project Brief and Development Guide

**Project type:** Beginner-friendly Python console application\
**Audience:** Python learners\
**Language:** Python 3

------------------------------------------------------------------------

## 1. Project Overview

Build a simple **ATM System** that simulates basic ATM operations through a command-line interface.

When the program starts, the account has a default balance of **₹10,000** and a default ATM PIN of **1234**. The user must enter the correct PIN before accessing the ATM menu.

The user can:
1. Check account balance.
2. Withdraw money.
3. Deposit money.
4. Change the ATM PIN.
5. Exit the application.

This is a learning project. It does not connect to a real bank account or process real transactions.

### Main objective

Practise conditional statements (`if-elif-else`), loops, variables, arithmetic, and input validation.

------------------------------------------------------------------------

## 2. Initial Values

  |Variable|      Default value | Meaning |
  |----------| --------------- | -------------- |
  |`balance`|           ₹10,000 | Initial account balance |
  |`pin`|                `1234` | Initial ATM PIN |

Initialize these values once when the program starts. Update them when the user completes a transaction or changes the PIN.

For this beginner version, values are stored in program memory and reset
when the application restarts.

------------------------------------------------------------------------

## 3. Project Scope

-   PIN authentication before showing the ATM menu.
-   Balance enquiry.
-   Cash withdrawal.
-   Cash deposit.
-   PIN change.
-   Exit option.
-   Input validation and transaction messages.

------------------------------------------------------------------------

## 4. Functional Requirements

### 4.1 PIN Authentication

When the application starts, ask the user to enter the ATM PIN.

Default PIN: `1234`

Example:

``` text
================================
          WELCOME TO ATM
================================
Please enter your 4-digit PIN: 1234

PIN verified successfully!
```

If the PIN is incorrect, display an error and ask again.

``` text
Please enter your 4-digit PIN: 1111

Incorrect PIN. Please try again.
```

**Basic requirement:** Keep asking until the correct PIN is entered.

### 4.2 Display ATM Menu

After successful PIN verification, display:

``` text
================================
           ATM MENU
================================
1. Check Account Balance
2. Withdraw Amount
3. Deposit Amount
4. Change PIN
5. Exit
================================
Enter your choice:
```

Use `if-elif-else` statements to handle the selected option.

### 4.3 Check Account Balance

When the user selects option `1`, display the current balance.

Example:

``` text
Your current account balance is: ₹10,000
```

The balance must reflect all earlier deposits and withdrawals in the current session.

### 4.4 Withdraw Amount

When the user selects option `2`:

1.  Ask for the withdrawal amount.
2.  Validate the amount.
3.  Check whether sufficient balance is available.
4.  Deduct the amount only if the transaction is valid.
5.  Display the amount withdrawn and remaining balance.

**Formula:**

`Remaining balance = Current balance - Withdrawal amount`

Example:

``` text
Enter amount to withdraw: 2000

Withdrawal successful!
Withdrawn amount: ₹2,000
Remaining balance: ₹8,000
```

#### Withdrawal validation

-   The amount must be numeric.
-   The amount must be greater than zero.
-   The amount must not exceed the current balance.

If the user tries to withdraw more than the available balance:

``` text
Enter amount to withdraw: 15000

Insufficient balance!
Available balance: ₹10,000
```

The balance must remain unchanged after a failed withdrawal.

### 4.5 Deposit Amount

When the user selects option `3`:

1.  Ask for the deposit amount.
2.  Validate the amount.
3.  Add it to the current balance.
4.  Display the deposited amount and updated balance.

**Formula:**

`Updated balance = Current balance + Deposit amount`

Example:

``` text
Enter amount to deposit: 3000

Deposit successful!
Deposited amount: ₹3,000
Updated balance: ₹13,000
```

#### Deposit validation

-   The amount must be numeric.
-   The amount must be greater than zero.
-   Invalid input must not change the balance.

### 4.6 Change PIN

When the user selects option `4`, allow them to change their ATM PIN.

Recommended process:

1.  Ask for the current PIN.
2.  Verify that it matches the existing PIN.
3.  Ask for a new PIN.
4.  Ask the user to confirm the new PIN.
5.  Update the PIN only if both new PIN entries match.

Example:

``` text
Enter your current PIN: 1234
Enter your new PIN: 5678
Confirm your new PIN: 5678

PIN changed successfully!
```

If the current PIN is incorrect, do not change the PIN. If the new PIN and confirmation do not match, display an error and keep the old PIN.

#### PIN validation

-   The PIN must contain exactly four digits.
-   The new PIN must not be empty.
-   The confirmation must match the new PIN.
-   Verify the existing PIN before changing it.

**Implementation note:** Store the PIN as a string rather than an integer. This preserves PINs that begin with zero, such as `0123`.

### 4.7 Exit

When the user selects option `5`, display a closing message and terminate the application.

``` text
Thank you for using our ATM!\
Have a nice day.
```

------------------------------------------------------------------------

## 5. Expected Application Flow

1.  Start the application.
2.  Initialize balance to ₹10,000 and PIN to `1234`.
3.  Ask the user to enter the PIN.
4.  Verify the entered PIN.
5.  If incorrect, show an error and ask again.
6.  If correct, display the ATM menu.
7.  Ask the user to select an operation.
8.  Use conditional statements to perform the selected operation.
9.  Update the balance or PIN after a valid operation.
10. Return to the ATM menu after each operation.
11. Continue until the user selects Exit.
12. End the application.

### High-level flowchart

``` text
                 START
                   |
                   v
       Initialize balance = 10000
             PIN = "1234"
                   |
                   v
             Enter ATM PIN
                   |
                   v
             Is PIN correct?
              /          \
            No            Yes
            |              |
       Show error          v
            |          Display menu
            |              |
            |              v
            |        Enter choice
            |              |
            |       +------+------+------+------+ 
            |       |      |      |      |      |
            |       1      2      3      4      5
            |       |      |      |      |      |
            |    Balance Withdraw Deposit Change Exit
            |     check           PIN
            |       |      |      |      |
            |       +------+------+------+
            |              |
            |              v
            |        Display menu again
            |              |
            +--------------+
                           |
                       If Exit
                           |
                           v
                          END
```

------------------------------------------------------------------------

## 6. Input Validation and Edge Cases

The application should handle invalid input without crashing.

  | Situation |                          Expected behaviour|
  | -----------------------------------| -----------------------------------|
  | Incorrect ATM PIN  |                 Display an error and ask again.|                          
  | Text entered instead of menu number| Display an error and show the menu again.|
  | Menu choice outside 1--5   |         Display an invalid-choice message.|
  | Text entered instead of transaction amount | Ask for a valid amount.|
  | Zero or negative withdrawal    |     Reject the transaction.|
  | Withdrawal greater than balance  |   Display insufficient balance; do not deduct money.|
  | Zero or negative deposit|            Reject the transaction.|
  | Incorrect current PIN during PIN change |   Do not change the PIN.|
  | New PIN and confirmation do not match |    Do not change the PIN.|
  | New PIN is not exactly four digits | Reject it.|
  | User selects Exit         |          End the application.|

-----------------------------------------------------------------------

Use `try`/`except` when converting amount or menu input to numeric values. PIN validation should be done using strings.

------------------------------------------------------------------------

## 7. Sample Transactions and Test Cases

Use these examples to verify that the balance is updated correctly.

### Test Case 1 --- Check initial balance

-   Initial balance: ₹10,000
-   Operation: Check balance
-   Expected balance: **₹10,000**

### Test Case 2 --- Successful withdrawal

-   Initial balance: ₹10,000
-   Withdrawal: ₹2,000
-   Calculation: ₹10,000 − ₹2,000 = ₹8,000
-   Expected balance: **₹8,000**

### Test Case 3 --- Successful deposit

-   Initial balance: ₹10,000
-   Deposit: ₹3,000
-   Calculation: ₹10,000 + ₹3,000 = ₹13,000
-   Expected balance: **₹13,000**

### Test Case 4 --- Multiple transactions

Starting balance: ₹10,000

|Step| Operation |          Amount|   Balance after operation|
|------| -----------------| -------- |-------------------------|
|1 |Initial balance|        --- |                  ₹10,000|
|2| Withdraw  |          ₹2,000 |                   ₹8,000|
|3 |Deposit    |         ₹5,000 |                  ₹13,000|
|4 |Withdraw    |        ₹1,000  |                 ₹12,000|
|5 |Check balance |         --- |                  ₹12,000|

Expected final balance: **₹12,000**.

### Test Case 5 --- Insufficient balance

-   Initial balance: ₹10,000
-   Withdrawal: ₹12,000
-   Expected: Show insufficient balance and keep the balance at ₹10,000.

### Test Case 6 --- Successful PIN change

-   Existing PIN: `1234`
-   New PIN: `5678`
-   Confirmation: `5678`
-   Expected: PIN changed successfully. The old PIN should no longer
    work; the new PIN should work for subsequent authentication in the
    current session.

### Test Case 7 --- PIN confirmation mismatch

-   Existing PIN: `1234`
-   New PIN: `5678`
-   Confirmation: `9876`
-   Expected: Show a mismatch message and keep the existing PIN unchanged.

------------------------------------------------------------------------

## 8. Python Concepts to Practise

This project helps students practise:

1.  **Variables** --- storing account balance and PIN.
2.  **Data types** --- integers and strings.
3.  **`if-elif-else`** --- choosing an ATM operation.
4.  **`while` loop** --- repeatedly displaying the menu.
5.  **Functions** --- separating operations into reusable blocks.
6.  **User input** --- accepting menu choices, PINs, and amounts.
7.  **Type conversion** --- converting amount input into numeric values.
8.  **String methods** --- validating PIN digits and length.
9.  **Exception handling** --- handling invalid numeric input.
10. **Arithmetic** --- adding and subtracting amounts.
11. **Boolean conditions** --- checking PINs and transaction rules.

------------------------------------------------------------------------

## 9. Development Tasks

Complete the project in stages.

### Task 1 --- Initialize account details

-   Create a balance variable and set it to ₹10,000.
-   Create a PIN variable and set it to `1234`.

### Task 2 --- Implement PIN verification

-   Ask the user to enter the PIN.
-   Compare it with the stored PIN.
-   Allow access only when it is correct.
-   Optional: limit incorrect attempts to three.

### Task 3 --- Display the ATM menu

-   Display all five operations.
-   Accept the user's choice.

### Task 4 --- Implement balance enquiry

-   Display the current balance.
-   Verify that it reflects previous transactions.

### Task 5 --- Implement withdrawal

-   Accept a withdrawal amount.
-   Validate the amount.
-   Check the available balance.
-   Deduct only when the transaction is valid.

### Task 6 --- Implement deposit

-   Accept a deposit amount.
-   Validate it.
-   Add it to the balance.

### Task 7 --- Implement PIN change

-   Verify the current PIN.
-   Accept a new four-digit PIN.
-   Confirm the new PIN.
-   Update the stored PIN only after successful validation.

### Task 8 --- Implement exit

-   Display a closing message.
-   Stop the menu loop.

### Task 9 --- Test the complete application

-   Test all five menu options.
-   Test invalid inputs.
-   Test multiple transactions.
-   Verify that balance and PIN remain updated during the session.

------------------------------------------------------------------------

## 10. Acceptance Criteria

The project is complete when:

-   [ ] Initial balance is ₹10,000.
-   [ ] Default PIN is `1234`.
-   [ ] Correct PIN is required before accessing ATM operations.
-   [ ] All five menu options are displayed.
-   [ ] User can check the current balance.
-   [ ] User can withdraw when sufficient balance is available.
-   [ ] Withdrawals greater than the balance are rejected.
-   [ ] User can deposit money.
-   [ ] Zero and negative transaction amounts are rejected.
-   [ ] User can change the PIN after verifying the existing PIN.
-   [ ] New PIN is validated and confirmed before being saved.
-   [ ] Menu appears again after each operation.
-   [ ] Application exits when option 5 is selected.
-   [ ] Invalid input does not crash the application.

------------------------------------------------------------------------

## 11. Guidelines for Students

-   Understand the complete flow before writing code.
-   Start with PIN verification.
-   Implement one ATM operation at a time.
-   Use `if-elif-else` for menu selection.
-   Use a loop to keep the application running until Exit is selected.
-   Update the balance only after validating a transaction.
-   Use meaningful variable names.
-   Handle invalid inputs carefully.
-   Test every operation independently.
-   Do not copy a complete solution without understanding it.

### Suggested challenge

Try implementing Version 1 using only:
- Variables
- `input()`
-`if-elif-else`
- `while` loop
- Basic arithmetic

Once it works, improve it using functions and exception handling.

------------------------------------------------------------------------

## 12. Submission Requirements

- **Python source code:** The complete implementation.
- **Test cases:** At least 10 test cases other than above suggestion covering valid and invalid inputs.
- **Sample output:** Screenshots or terminal output demonstrating the program's behavior.

------------------------------------------------------------------------

**Project outcome:** By completing this project, students should understand how to build a menu-driven Python application using conditional statements, loops, variables, functions, arithmetic, and input validation.
