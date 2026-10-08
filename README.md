# Risky Game

A small Python guessing game with platform-specific versions for
**Windows** and **macOS**.

> \[!WARNING\] **Do not run these scripts on a real computer.**
>
> Although the program presents itself as a simple number-guessing game,
> the losing branch contains code that attempts to recursively delete a
> critical operating-system directory:
>
> -   Windows version: `C:\Windows`
> -   macOS version: `/System`
>
> This can cause severe system damage if the operation succeeds and
> should only be inspected as example code in a safe, isolated
> environment.

## Files

  -------------------------------------------------------------------------
  File                      Platform                Description
  ------------------------- ----------------------- -----------------------
  `Risky_Game_windows.py`   Windows                 Number-guessing game
                                                    with a Windows-specific
                                                    destructive command

  `Risky_Game_macOS.py`     macOS                   Number-guessing game
                                                    with a macOS-specific
                                                    destructive command
  -------------------------------------------------------------------------

## How the Game Works

Both scripts follow the same basic flow:

1.  Import Python's `random` module.
2.  Generate a random integer between **1 and 10**.
3.  Ask the player to guess the number.
4.  Convert the player's input to an integer.
5.  If the guess is correct, print `You Won!`.
6.  If the guess is incorrect, execute a platform-specific filesystem
    deletion command.

The random number is generated with:

``` python
number = random.randint(1, 10)
```

The user is then prompted with:

``` text
Silly game! Guess number between 1 and 10:
```

A correct guess results in:

``` text
You Won!
```

The Windows script's losing branch imports `shutil` and calls:

``` python
shutil.rmtree("C:\Windows")
```

The macOS script's losing branch calls:

``` python
shutil.rmtree("/System")
```

## Requirements

The scripts use Python's standard library modules, including:

-   `random`
-   `os`
-   `shutil` (loaded only in the losing branch)

No third-party Python packages are required.

## Usage

The scripts are intended to be run according to their target operating
system:

``` bash
python Risky_Game_windows.py
```

or:

``` bash
python Risky_Game_macOS.py
```

**However, do not execute either script on a normal Windows or macOS
installation.** The losing branch is intentionally destructive.

## Code Structure

The core game logic is essentially:

``` python
number = random.randint(1, 10)

guess = input("Silly game! Guess number between 1 and 10: ")
guess = int(guess)

if guess == number:
    print("You Won!")
else:
    # Platform-specific destructive operation
```

The two files differ primarily in the target directory used by the
losing branch.

## Safety Notes

This project should be treated as **unsafe demonstration code**, not as
a normal game.

If the goal is to learn Python conditionals, random numbers, and user
input, the destructive branch should be replaced with a harmless action
such as:

``` python
print("You Lost!")
```

A safe version would therefore behave like a normal guessing game
without modifying the filesystem.

## License

No license is specified in the provided source files.
