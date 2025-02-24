# Wheel of Fortune using Python

## Overview
This project is a simplified implementation of the classic game **Wheel of Fortune** using Python. It was created as the final project for **Course 4 - Python Classes and Inheritance** offered by *University of Michigan through Coursera*. The project walks through building player classes, handling game logic, and simulating the game experience.

---

## Project Structure

### Part A: WOFPlayer
The **WOFPlayer** class represents a basic player in the game.

**Instance Variables:**
- `name`: The name of the player (passed into the constructor)
- `prizeMoney`: The player’s prize money (initialized to 0)
- `prizes`: A list of prizes won by the player (initialized to [])

**Methods:**
- `addMoney(amt)`: Adds the specified amount to the player’s prize money.
- `goBankrupt()`: Resets the player’s prize money to 0.
- `addPrize(prize)`: Appends a prize to the player's prize list.
- `__str__()`: Returns a string representation of the player’s name and prize money (e.g., `Steve ($1800)`).

---

### Part B: WOFHumanPlayer
The **WOFHumanPlayer** class inherits from **WOFPlayer** and represents a human player.

**Additional Method:**
- `getMove(category, obscuredPhrase, guessed)`: Prompts the player to enter a move. Players can guess a letter, a phrase, pass their turn, or exit the game.

Example prompt:
```
John has $1500
Category: Movie Title
Phrase: _ _ _ _ _ _ _
Guessed: ['E', 'A']
Guess a letter, phrase, or type 'exit' or 'pass':
```

---

### Part C: WOFComputerPlayer
The **WOFComputerPlayer** class inherits from **WOFPlayer** and represents a computer-controlled player.

**Instance Variables:**
- `difficulty`: The computer player's difficulty level.

**Class Variable:**
- `SORTED_FREQUENCIES`: A string of English letters sorted from least to most frequent (`'ZQXJKVBPYGFWMUCLDRHSNIOATE'`).

**Methods:**
- `smartCoinFlip()`: Determines if the computer makes a "good" or "bad" move based on difficulty.
- `getPossibleLetters(guessed)`: Returns a list of letters that can still be guessed.
- `getMove(category, obscuredPhrase, guessed)`: Chooses a move based on available letters and the result of `smartCoinFlip`.

---

## Game Description
The game follows these simplified rules:
- Players (human or computer) take turns spinning a virtual wheel.
- If the wheel lands on a cash square, players can:
    - Guess a letter (vowels cost $250, consonants are free).
    - Guess the entire phrase.
    - Pass their turn.
- Special wheel outcomes:
    - **Lose a turn:** Player loses their turn.
    - **Bankrupt:** Player loses all their money but keeps their prizes.
- The game ends when someone guesses the full phrase or all letters are revealed.

Example category and phrase:
```
Category: Artist & Song
Phrase: Whitney Houston’s I Will Always Love You
```

---

## Key Features
- **Interactive Gameplay:** Human players can input guesses, phrases, or choose to pass/exit.
- **Computer AI:** Computer players make semi-random decisions based on difficulty level.
- **Dynamic Wheel Spin:** Players win cash or prizes based on wheel outcomes.
- **Realistic Timing:** `time.sleep()` adds delays for a more natural game flow.

---

## How to Run
1. Clone the repository.
2. Install Python (if not already installed).
3. Run the game script:
```bash
python wheel_of_fortune.py
```
4. Follow the on-screen prompts to play!

---

## Acknowledgments
- **University of Michigan** - For providing the course material.
- **Coursera** - For hosting the course.

This project was a great opportunity to practice object-oriented programming, inheritance, and build a fun, interactive Python game!

---

