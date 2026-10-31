## 1. Project Overview

**Project Name:** Email Validation System

**Difficulty Level:** Beginner

**Programming Language:** Python

**Core Concepts:** Strings, string methods, conditional statements, loops, and input validation.

### Problem Statement

Develop a Python program that accepts an email address from the user and checks whether it satisfies a set of predefined validation rules.

The program should analyze the email address and determine whether it follows the required format. If the email address violates any rule, the program should display an appropriate error message explaining the problem.

The primary goal of this project is to understand how strings can be processed and validated using Python.

## 2. Project Objectives

By completing this project, you should be able to:

* Understand and manipulate strings in Python.
* Search for specific characters and substrings within a string.
* Count the occurrences of a character.
* Validate user input using conditional statements.
* Handle invalid input and display meaningful error messages.
* Break a problem into smaller validation steps.
* Write reusable functions for validating data.

## 3. Functional Requirements

### Requirement 1: Accept an Email Address

The program should ask the user to enter an email address.

Example:

```
Enter your email address: example@gmail.com
```

The program should store the input and perform the required validation checks.

### Requirement 2: Check the Number of `@` Symbols

An email address must contain exactly one `@` symbol.

**Validation rules:**

* If the email contains no `@` symbol, it should be rejected.
* If the email contains more than one `@` symbol, it should be rejected.
* If the email contains exactly one `@` symbol, it can proceed to the next validation step.

**Examples:**

| Email Address                                 | Expected Result |
| --------------------------------------------- | --------------- |
| [example@gmail.com](mailto:example@gmail.com) | Pass            |
| examplegmail.com                              | Fail            |
| example@@gmail.com                            | Fail            |
| ex@[ample@gmail.com](mailto:ample@gmail.com)  | Fail            |

Error message example:

```
Invalid email: The email must contain exactly one @ symbol.
```

### Requirement 3: Check the Email Domain

For this project, accept only email addresses ending with `@gmail.com`.

**Validation rules:**

* The email must end with `@gmail.com`.
* Email addresses belonging to other domains should be rejected.
* The domain must appear at the end of the email address.

**Examples:**

| Email Address                                                 | Expected Result |
| ------------------------------------------------------------- | --------------- |
| [student@gmail.com](mailto:student@gmail.com)                 | Pass            |
| [developer@gmail.com](mailto:developer@gmail.com)             | Pass            |
| [student@yahoo.com](mailto:student@yahoo.com)                 | Fail            |
| [developer@outlook.com](mailto:developer@outlook.com)         | Fail            |
| [student@gmail.in](mailto:student@gmail.in)                   | Fail            |
| [student@gmail.com.example](mailto:student@gmail.com.example) | Fail            |

Error message example:

```
Invalid email: Only Gmail addresses ending with @gmail.com are allowed.
```

### Requirement 4: Handle Empty Input

The program should not accept an empty string as a valid email address.

Examples:

| User Input                                    | Expected Result     |
| --------------------------------------------- | ------------------- |
| Empty input                                   | Fail                |
| Spaces only                                   | Fail                |
| [student@gmail.com](mailto:student@gmail.com) | Continue validation |

Error message example:

```
Invalid input: Email address cannot be empty.
```

### Requirement 5: Display the Final Result

After completing all the validation checks, the program should display the appropriate result.

Successful validation:

```
Enter your email address: student@gmail.com
Result: Email address is valid.
```

Failed validation:

```
Enter your email address: student@yahoo.com
Result: Invalid email address.
Reason: Only Gmail addresses ending with @gmail.com are allowed.
```

The program should explain why the input was rejected instead of displaying only a generic error message.

## 4. Suggested Program Structure

You can divide the program into the following logical steps:

1. Accept the email address.
2. Check whether the input is empty.
3. Count the number of `@` symbols.
4. Check whether the email ends with `@gmail.com`.
5. Display the final validation result.


## 5. Important Note

This is a simplified email validation project designed for learning purposes.

Checking for exactly one `@` symbol and the `@gmail.com` ending does not guarantee that an email address is fully valid or that the mailbox exists.

For example, `@gmail.com` satisfies those two basic checks but is not a valid complete email address.

As an additional improvement, consider checking that the part before `@` is not empty.

**Deliverable:** A working Python program that validates email addresses according to the specified rules and displays meaningful results.

## 6. Submission Requirements

**Python source code:** The complete implementation.
**Test cases:** At least 10 test cases covering valid and invalid inputs.
**Sample output:** Screenshots or terminal output demonstrating the program's behavior.