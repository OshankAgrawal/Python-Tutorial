# Mini Project 4: Number Guessing Game

## 1. Project Overview

- **Difficulty:** Beginner
- **Language:** Python
- **Core concepts:** Variables, random numbers, loops, conditionals, numeric input.

## 2. Problem Statement

Create a game in which the computer selects a secret number within a defined range and the player tries to guess it. After each guess, the program tells the player whether the guess is too low, too high, or correct. The game tracks the number of attempts.

## 3. Learning Objectives

- Generate random numbers using Python's `random` module.
- Accept and validate numeric input.
- Use loops to repeat gameplay.
- Compare values with conditional statements.
- Track scores and attempts.
- Design a simple replay experience.

## 4. Functional Requirements

### Requirement 1: Generate a Secret Number
Choose a random integer between a minimum and maximum value, such as 1 and 100. The limits should be clear to the player.

### Requirement 2: Accept Guesses
Ask the player to enter a guess. The guess must be an integer within the selected range.

### Requirement 3: Give Feedback
After each valid guess:
- If the guess is lower than the secret number, display `Too low`.
- If the guess is higher, display `Too high`.
- If the guess matches, display a success message.

### Requirement 4: Count Attempts
Count each valid guess. Clearly decide whether invalid inputs count as attempts; for this project, invalid inputs should not count.

### Requirement 5: End the Game
The game ends when the player guesses correctly or reaches an optional maximum number of attempts. If a limit is used, reveal the secret number after the game ends.

### Requirement 6: Play Again
Ask whether the player wants to start a new round. A new round must generate a new secret number and reset the attempt counter.

## 5. Suggested Program Workflow

1. Set the minimum and maximum values.
2. Generate a random secret number.
3. Set the attempt count to zero.
4. Repeatedly ask for a guess.
5. Validate the input and range.
6. Increase attempts for a valid guess.
7. Display a hint or finish the round.
8. Offer to play again.

## 6. Validation and Error Handling

- Handle non-numeric input without crashing.
- Reject guesses outside the permitted range.
- Do not count invalid guesses as attempts.
- Handle yes/no replay choices consistently.

## 7. Suggested Test Cases

| Test | Input or action | Expected result |
|---|---|---|
| 1 | Guess lower than secret | `Too low` |
| 2 | Guess higher than secret | `Too high` |
| 3 | Guess the secret number | Win message |
| 4 | Enter letters | Validation message |
| 5 | Guess below the minimum | Out-of-range message |
| 6 | Guess above the maximum | Out-of-range message |
| 7 | Enter an invalid guess then a valid one | Invalid input does not count |
| 8 | Reach the attempt limit | Round ends as specified |
| 9 | Choose replay | New round starts and attempts reset |
| 10 | Decline replay | Program exits politely |

## 8. Submission Requirements

**Python source code:** The complete implementation.
**Test cases:** At least 10 test cases other than above suggestion covering valid and invalid inputs.
**Sample output:** Screenshots or terminal output demonstrating the program's behavior.
