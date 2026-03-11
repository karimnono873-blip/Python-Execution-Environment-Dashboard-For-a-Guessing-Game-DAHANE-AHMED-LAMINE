# 🐍 Python Simulator: Guess the Number Game

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)
![Python Concepts](https://img.shields.io/badge/Python_Concepts-3776AB?style=for-the-badge&logo=python&logoColor=white)

> **An interactive, browser-based IDE simulator that allows users to play and understand a Python-based "Guess the Number" game through a custom-built web terminal.**

## 📖 Overview

This project is an educational web application that simulates a Python execution environment. It is designed to demonstrate core programming logic by allowing users to play a classic "Guess the Number" game directly in their browser. 

The dashboard features a split-pane view: one side displays the underlying Python script with syntax highlighting, while the other provides a functional JavaScript-based terminal emulator that mimics the Python standard input/output stream.

---

## ✨ Key Features

* 💻 **Interactive Web Terminal:** A custom JS terminal that simulates Python's `input()` and `print()` functions, handling user inputs, generating dynamic responses, and catching invalid data (like strings instead of integers).
* ⚙️ **Game Customization:** Users can dynamically adjust the game's parameters (minimum value, maximum value, and maximum allowed guesses) before execution.
* 📊 **Live History Tracker:** A real-time data table logs every guess, evaluates the feedback (Too High/Too Low/Correct), and tracks remaining attempts.
* 🎨 **IDE Aesthetic:** A responsive, dark-mode user interface inspired by modern code editors (like VS Code and GitHub Codespaces).

---

## 🧠 Python Concepts Demonstrated

While the environment is built with web technologies, the logic perfectly maps to the displayed Python script, showcasing the following fundamental programming concepts:

* **Modules:** Importing and utilizing the `random` module (`random.randint()`).
* **I/O Operations:** Using `input()` to gather string data and `print()` for formatted feedback.
* **Type Casting:** Converting string inputs into integers using `int()`, wrapped in `try/except` blocks for error handling.
* **Control Flow:** Using `while True` loops for continuous game states and `if/elif/else` conditional statements to evaluate the user's guesses.

---

## 🚀 Quick Start

This dashboard is built entirely with frontend technologies. No local Python installation or backend server is required to view and play the game.

1.  Clone or download this repository.
2.  Locate the `guess_the_number.html` file.
3.  **Double-click** to open it in any modern web browser (Chrome, Edge, Firefox, Safari).
4.  Adjust the variables in the left sidebar (optional) and click **"Run Python Script"**.
5.  Click inside the terminal on the right and type your guesses!

---

## 💻 The Simulated Python Script

```python
import random

def play_guess_the_number(min_val, max_val, max_attempts):
    print("Welcome to the Guess the Number game!")
    target_number = random.randint(min_val, max_val)
    print(f"I'm thinking of a number between {min_val} and {max_val}.")
    
    attempts = 0
    while True:
        if max_attempts > 0 and attempts >= max_attempts:
            print(f"Game Over! The number was {target_number}.")
            break
            
        guess_str = input("Enter your guess: ")
        try:
            guess = int(guess_str)
        except ValueError:
            print("Invalid input. Please enter a number.")
            continue
            
        attempts += 1
        if guess < target_number:
            print("Your guess is too low. Guess again.")
        elif guess > target_number:
            print("Your guess is too high. Guess again.")
        else:
            print(f"Congratulations! You guessed correctly in {attempts} tries!")
            break
