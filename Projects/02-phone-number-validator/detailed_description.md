## 1. Project Overview

**Project Name:** International Mobile Number Validation System

**Difficulty Level:** Beginner

**Programming Language:** Python

**Core Concepts:** Strings, conditional statements, loops, string methods, and input validation.

### Problem Statement

Develop a Python program that accepts a mobile number from the user and checks whether it satisfies a set of predefined validation rules.

The program should verify that the mobile number contains only numeric digits, has the required number of digits, and includes a valid country calling code from a predefined list of five countries.

The program should provide clear feedback about whether the input is valid and explain any validation failures.

The primary objective is to practice string manipulation and understand how validation rules can be applied to user input.

## 2. Project Objectives

By completing this project, you should be able to:

* Understand how mobile numbers are represented and processed as strings.
* Check whether a string contains only digits.
* Calculate the length of a string.
* Extract and compare prefixes.
* Validate country calling codes.
* Apply multiple conditions to a single input.
* Handle invalid input and provide meaningful error messages.

## 3. Functional Requirements

### Requirement 1: Accept a Mobile Number

The program should ask the user to enter a mobile number, including its country calling code.

Example:

```
Enter your mobile number: +919876543210
```

The program should store the number as a string.

**Important:** Do not convert the entire mobile number into an integer. Mobile numbers are identifiers rather than quantities, and converting them to integers can remove leading zeros and interfere with the `+` symbol.

### Requirement 2: Check Whether the Input Contains Only Digits and an Optional `+` Prefix

The program should verify that the mobile number contains numeric digits, with an optional `+` symbol at the beginning to indicate the international calling format.

**Validation rules:**

* The number may start with a `+` symbol.
* If present, `+` must appear only at the beginning.
* All remaining characters must be digits.
* Spaces, alphabetic characters, and other special characters should be rejected in the basic version.

**Examples:**

| Mobile Number  | Expected Result |
| -------------- | --------------- |
| +919876543210  | Pass            |
| 919876543210   | Pass            |
| +14155552671   | Pass            |
| +91AB76543210  | Fail            |
| +91-9876543210 | Fail            |
| +91 9876543210 | Fail            |
| ++919876543210 | Fail            |

Error message example:

```
Invalid mobile number: Use digits only, with an optional + at the beginning.
```

For the basic version, the program can accept both international numbers with a `+` prefix and numbers written without it. However, it must still identify the country code according to the chosen input format.

### Requirement 3: Check the Number of Digits

For the initial version of this project, use the following simplified rule:

**The mobile number must contain exactly 10 national-number digits, excluding the country calling code.**

For example:

```
+91 9876543210
```

Here:

* `+91` is the country calling code.
* `9876543210` is the 10-digit national number.

**Important:** The 10-digit rule applies to this project's simplified requirements. Real international numbering plans do not all use 10-digit national numbers.

**Examples:**

| Mobile Number  | Expected Result        |
| -------------- | ---------------------- |
| +919876543210  | Pass                   |
| +911234567890  | Pass this length check |
| +91987654321   | Fail                   |
| +9198765432101 | Fail                   |

The second example passes the length check only; it is not necessarily an assigned or valid mobile number.

Error message example:

```
Invalid mobile number: The national number must contain exactly 10 digits.
```

### Requirement 4: Validate the Country Calling Code

The program should support exactly five predefined countries.

Use the following countries for the initial version:

| Country        | Country Calling Code | Example Format |
| -------------- | -------------------- | -------------- |
| India          | +91                  | +919876543210  |
| United States  | +1                   | +11234567890   |
| United Kingdom | +44                  | +441234567890  |
| Australia      | +61                  | +611234567890  |
| Canada         | +1                   | +11234567890   |

**Important:** The United States and Canada share the `+1` country calling code. Therefore, a country calling code alone cannot distinguish between these two countries.

Also, the example numbers above illustrate the required format; they are not guaranteed to be real or assigned mobile numbers.

**Validation rules:**

* Accept only the five countries configured in the program.
* Reject country calling codes that are not supported.
* Identify the country from the supplied calling code where possible.
* Handle shared calling codes appropriately.

Error message example:

```
Invalid mobile number: The country calling code is not supported.
```

### Requirement 5: Separate the Country Code from the National Number

The program should identify the country calling code and separate it from the remaining national number.

For example:

```
Input: +919876543210

Country Code: +91
National Number: 9876543210
```

This step should be performed carefully because country calling codes have different lengths.

**Hint:** Do not assume that every country calling code contains exactly two digits. For example, `+1`, `+44`, and `+61` have different lengths when the `+` symbol is excluded.

For this project, you can maintain a predefined mapping of supported country calling codes and their associated countries.

### Requirement 6: Display the Final Result

After all validation checks are complete, display the result.

**Example 1: Successful validation**

```
Enter your mobile number: +919876543210

Result: Mobile number passed the validation checks.
Country: India
Country Code: +91
National Number: 9876543210
```

**Example 2: Invalid length**

```
Enter your mobile number: +91987654321

Result: Invalid mobile number.
Reason: The national number must contain exactly 10 digits.
```

**Example 3: Unsupported country code**

```
Enter your mobile number: +819876543210

Result: Invalid mobile number.
Reason: The country calling code is not supported.
```

**Example 4: Invalid characters**

```
Enter your mobile number: +91AB76543210

Result: Invalid mobile number.
Reason: The number contains characters other than digits and the optional leading +.
```

## 4. Suggested Program Structure

Divide the program into the following logical steps:

1. Accept the mobile number as a string.
2. Check whether the input is empty.
3. Validate the optional leading `+` and ensure the remaining characters are digits.
4. Identify the supported country calling code.
5. Separate the country calling code from the national number.
6. Check whether the national number contains exactly 10 digits.
7. Display the country information and final validation result.

## 5. Important Note

This project performs basic format validation. Passing these checks does not prove that a number is assigned, active, or capable of receiving calls or messages.

Real international mobile number validation requires country-specific numbering rules. The United States and Canada also share the `+1` calling code, so identifying the exact country may require additional information.

**Deliverable:** A working Python program that validates mobile-number formats, identifies supported country calling codes, and displays meaningful validation results.

## 6. Submission Requirements

**Python source code:** The complete implementation.
**Test cases:** At least 10 test cases covering valid and invalid inputs.
**Sample output:** Screenshots or terminal output demonstrating the program's behavior.