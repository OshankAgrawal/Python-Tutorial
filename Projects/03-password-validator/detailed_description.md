# Mini Project 3: Password Validation System

## 1. Project Overview

**Project Name:** Password Validation System

**Difficulty Level:** Beginner

**Programming Language:** Python

**Core Concepts:** Strings, loops, conditional statements, logical operators, and input validation.

### Problem Statement

Develop a Python program that accepts a password from the user and checks whether it satisfies a predefined set of password requirements.

The program should examine the password and verify its length, character types, and other security-related conditions.

If the password satisfies all the requirements, the program should display a success message. Otherwise, it should identify the requirements that the password fails to meet.

The primary goal is to understand how to manipulate strings, check individual characters, and combine multiple conditions to validate user input.

## 2. Project Objectives

By completing this project, you should be able to:

* Understand and manipulate strings in Python.
* Check the length of a string.
* Identify uppercase and lowercase letters.
* Identify numeric digits.
* Detect special characters.
* Apply multiple conditions using logical operators.
* Use loops to examine individual characters.
* Create reusable validation functions.
* Display meaningful error messages.
* Write and test a program that follows a predefined set of requirements.

## 3. Functional Requirements

### Requirement 1: Accept a Password

The program should ask the user to enter a password.

Example:

```
Enter your password: MyPassword@123
```

The program should store the password and perform the required validation checks.

**Important:** Passwords should be treated as strings. Do not convert them into integers or other numeric types.

### Requirement 2: Check Password Length

The password must contain at least 8 characters.

**Validation rules:**

* Passwords shorter than 8 characters should be rejected.
* Passwords containing 8 or more characters should pass this check.

**Examples:**

| Password       | Expected Result |
| -------------- | --------------- |
| Abc@123        | Fail            |
| Abcd@123       | Pass            |
| MyPassword@123 | Pass            |
| A1@bc          | Fail            |

Error message example:

```
Invalid password: Password must contain at least 8 characters.
```

### Requirement 3: Check for an Uppercase Letter

The password must contain at least one uppercase English letter, from `A` to `Z`.

**Examples:**

| Password       | Expected Result |
| -------------- | --------------- |
| mypassword@123 | Fail            |
| Mypassword@123 | Pass            |
| PASSWORD@123   | Pass            |

Error message example:

```
Invalid password: Include at least one uppercase letter.
```

### Requirement 4: Check for a Lowercase Letter

The password must contain at least one lowercase English letter, from `a` to `z`.

**Examples:**

| Password       | Expected Result |
| -------------- | --------------- |
| MYPASSWORD@123 | Fail            |
| MyPassword@123 | Pass            |
| PASSWORD@123   | Fail            |

Error message example:

```
Invalid password: Include at least one lowercase letter.
```

### Requirement 5: Check for a Numeric Digit

The password must contain at least one numeric digit from `0` to `9`.

**Examples:**

| Password       | Expected Result |
| -------------- | --------------- |
| MyPassword@    | Fail            |
| MyPassword@123 | Pass            |
| Password123    | Pass            |

Error message example:

```
Invalid password: Include at least one numeric digit.
```

### Requirement 6: Check for a Special Character

The password must contain at least one special character.

For this project, consider the following characters as special characters:

```
! @ # $ % ^ & * ( ) _ + - =
```

**Validation rules:**

* At least one character from the specified list must appear in the password.
* Spaces should not count as special characters.
* Characters outside the specified list should not satisfy this requirement.

**Examples:**

| Password       | Expected Result |
| -------------- | --------------- |
| MyPassword123  | Fail            |
| MyPassword@123 | Pass            |
| MyPassword#123 | Pass            |
| MyPassword_123 | Pass            |

Error message example:

```
Invalid password: Include at least one special character.
```

### Requirement 7: Reject Empty Passwords

The program must not accept an empty password.

**Examples:**

| Input          | Expected Result     |
| -------------- | ------------------- |
| Empty input    | Fail                |
| MyPassword@123 | Continue validation |

Error message example:

```
Invalid password: Password cannot be empty.
```

Do not automatically remove spaces from the beginning or end of a password. Spaces may be part of the password itself, and silently modifying a password can cause unexpected behavior.

For this exercise, you may decide to reject spaces entirely as an additional rule.

### Requirement 8: Display the Final Validation Result

After checking all the requirements, the program should display the final result.

**Example 1: Valid Password**

```
Enter your password: MyPassword@123

Password Validation Result: VALID
Your password satisfies all the requirements.
```

**Example 2: Invalid Password**

```
Enter your password: mypassword

Password Validation Result: INVALID

The password does not satisfy the following requirements:
- Include at least one uppercase letter.
- Include at least one numeric digit.
- Include at least one special character.
```

**Example 3: Multiple Validation Errors**

```
Enter your password: abc

Password Validation Result: INVALID

The password does not satisfy the following requirements:
- Password must contain at least 8 characters.
- Include at least one uppercase letter.
- Include at least one numeric digit.
- Include at least one special character.
```

**Important:** The program should display all applicable validation errors rather than stopping after finding the first error.

This will help you understand how to perform multiple independent validation checks.

## 4. Suggested Program Workflow

Follow these steps to design your program:

1. Accept the password from the user.
2. Check whether the password is empty.
3. Check whether it contains at least 8 characters.
4. Check whether it contains an uppercase letter.
5. Check whether it contains a lowercase letter.
6. Check whether it contains a numeric digit.
7. Check whether it contains a special character from the predefined list.
8. Collect all failed validation conditions.
9. Display the final result and any applicable error messages.

## 5. Bonus Challenges

Once you have completed the basic requirements, try the following improvements.

### Challenge 1: Reject Spaces

Modify the program so that passwords containing spaces are rejected.

Example:

```
My Password@123
```

Expected result: Invalid password.

### Challenge 2: Add a Maximum Length

Set a maximum password length of 20 characters.

The password must contain between 8 and 20 characters, inclusive.

### Challenge 3: Write Unit Tests

Write test cases to verify that the program behaves correctly for different passwords.

Test passwords that:

* Satisfy every requirement.
* Fail only one requirement.
* Fail multiple requirements.
* Contain no characters.
* Contain only numbers.
* Contain only letters.
* Contain special characters but no digits.

## 6. Suggested Test Cases

Use the following examples to test your program.

| Test Case | Password       | Expected Result                                                 |
| --------- | -------------- | --------------------------------------------------------------- |
| 1         | MyPassword@123 | Valid                                                           |
| 2         | abc            | Invalid                                                         |
| 3         | mypassword@123 | Invalid: No uppercase letter                                    |
| 4         | MYPASSWORD@123 | Invalid: No lowercase letter                                    |
| 5         | MyPassword@    | Invalid: No digit                                               |
| 6         | MyPassword123  | Invalid: No special character                                   |
| 7         | Abc@123        | Invalid: Less than 8 characters                                 |
| 8         | 12345678       | Invalid: Missing letters and special character                  |
| 9         | PASSWORD@123   | Invalid: No lowercase letter                                    |
| 10        | abcdefgh       | Invalid: Missing uppercase letter, digit, and special character |

## 7. Technical Expectations

Your implementation should follow these guidelines:

* Use Python.
* Store the password as a string.
* Use conditional statements to implement the validation rules.
* Use loops where appropriate.
* Use functions to organize the code.
* Display meaningful error messages.
* Avoid stopping validation after the first failed condition.
* Test the program with different combinations of valid and invalid passwords.
* Write clean, readable code with appropriate variable names.

You may use Python's built-in string methods, such as `isupper()`, `islower()`, and `isdigit()`, where appropriate.

However, remember that checking an entire string with these methods is not the same as checking whether at least one character in the string satisfies a condition.

## 8. Important Security Note

This project focuses on password format validation.

A password that satisfies these rules is not automatically secure. Real-world password security also depends on factors such as password uniqueness, length, predictability, and whether the password has appeared in known data breaches.

This program should not store passwords in plain text or be used as a production authentication system.

**Deliverable:** A working Python program that validates passwords against the specified requirements, identifies all failed checks, and displays meaningful results.

## 6. Submission Requirements

**Python source code:** The complete implementation.
**Test cases:** At least 10 test cases other than above suggestion covering valid and invalid inputs.
**Sample output:** Screenshots or terminal output demonstrating the program's behavior.