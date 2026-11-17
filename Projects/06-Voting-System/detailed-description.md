# Mini Project 06: Voting System Using Lists

## 1. Project Overview

- **Difficulty:** Beginner
- **Language:** Python
- **Core concepts:** Lists, strings, loops, conditionals, counters, and input validation.
- **Scope:** A learning simulation, not a real election system.

## 2. Problem Statement

Build a simple voting simulation in which a predefined set of candidates is displayed, a user selects a candidate, and the program records the vote and displays the final results. The main learning objective is to practise using Python lists and basic logic to manage choices and count votes.

## 3. Learning Objectives

- Create and iterate through lists.
- Match a user's choice against available options.
- Count votes for each candidate.
- Validate menu choices.
- Display results in a clear format.
- Understand the limitations of an in-memory program.

## 4. Functional Requirements

### Requirement 1: Define Candidates
Create a list of candidate names. For example:

```python
candidates = ["Candidate A", "Candidate B", "Candidate C"]
```

Display each candidate with a number so users can select one.

### Requirement 2: Accept a Vote
Ask the user to choose a candidate by number or name. Accept only choices that match the candidate list.

### Requirement 3: Record Votes
For this exercise, maintain a list of votes, where each entry represents a candidate selected by one simulated voter.\ Alternatively, use a separate list of candidate names and vote counts, but explain the data structure used.

### Requirement 4: Prevent Repeat Voting (Basic Simulation)
To practise list membership, the program may ask each simulated voter for a unique voter ID and keep a list of IDs that have voted. Reject a repeated ID.

This is only a classroom exercise. A list stored in a local program is not a secure or reliable way to enforce voting eligibility.

### Requirement 5: Display Results
When voting ends, display each candidate and their vote count and Show the percentage of votes for each candidate. The candidate with the highest number of votes may be declared the winner.

### Requirement 6: Handle a Tie
If two or more candidates have the highest equal vote counts, display a tie message and identify the tied candidates.

### Requirement 7: Menu and Exit
Suggested menu:
1. Cast a vote
2. End voting and show final results
3. Exit

## 5. Suggested Logic

- Store candidate names in a list.
- Store each vote in a list, or maintain counts associated with candidates.
- Check that the selected candidate exists.
- If using voter IDs, check that the ID has not already voted.
- Count votes for each candidate.
- Identify the maximum count and check whether more than one candidate has that count.

## 6. Validation and Error Handling

- Reject invalid candidate selections.
- Handle empty candidate lists.
- Handle zero votes without crashing.
- Reject duplicate voter IDs if the optional simulation rule is implemented.
- Handle invalid menu options.
- Do not announce a winner before the voting session is finished.


## 7. Suggested Test Cases

| Test | Input or action | Expected result |
|---|---|---|
| 1 | Vote for Candidate A | A's count increases by one |
| 2 | Vote for Candidate B twice using two voters | B has two votes |
| 3 | Enter an invalid candidate number | Vote is not recorded |
| 4 | Enter text instead of a number | Validation message |
| 5 | Repeat a voter ID | Second vote is rejected, if IDs are enabled |
| 6 | End with no votes | No-votes message |
| 7 | Candidate A has the most votes | A is declared winner |
| 8 | Two candidates tie | Tie is reported |
| 9 | Display results | All candidates and counts appear |
| 10 | Use an invalid menu option | Program continues safely |

## 8. Submission requirements

- **Python source code:** The complete implementation.
- **Test cases:** At least 10 test cases other than above suggestion covering valid and invalid inputs.
- **Sample output:** Screenshots or terminal output demonstrating the program's behavior.


**Important:** This project is for learning Python only. It must not be used to conduct a real election or store sensitive voter information.
