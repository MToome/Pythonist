---
title: "Beginner Pythonist # Battleship"
last_modified_at: 2023-08-12
categories:
  - Blog
tags:
  - Begginer
  - Project
---

## Introduction 

  I am Marek and I started to learn computer science at codecademy. Python is the coding languet codecademy teaches for that. I have reached so far that I have to write a terminal game in python without clear instructions. My first program without clear instruction is this battleship game. It helped me to understand better programming and also consolidate what I have learned. I did read Austin Montgomery and Avery Smith post Python for Beginners: Battleship
  I will be going over the code and explaining it.
  Here is a link to my github repository: [Python Terminal game: Battleship](https://github.com/MToome/Portfolio_Python_Battleship)

## Code

  First it is needed to import _random module_ so we could use random number generator
```python
import random
```

### Board

  Can not play without a board, to make a board a function is needed that can be used to make different sized boards. Only  the board prints O with **[]**, **"** and **,** . To make nice looking board without extra marks, the unpacking operator(*) is used for that. While unpacking it looses the excess marks.
```python
def build_board(dims):
    board =[['O' for _ in range(dims)] for _ in range(dims)]
    for row in board:
        print(*row)
       
```

### Ship spawn
  
  To spawn ship randomly the _random module_ is used. On every line their is written what the line will do.
```python
def spawn_ship(dims):
   
  # Ship length is randomly selected between 1 and dims size. 
    ship_len = random.randint(1,dims)

  # Ship orientation is randomly selected between 0 and 1
  # (vertical or horizontal).  
    ship_orientation = random.randint(0,1)

  # Checks if the orientation is 0 then it generates 
  # the random location.
    if ship_orientation == 0:

  # Selects the row for the ship randomly between 0 and 
  # inputted dims size - 1, then multiples it to ship length list.
    ship_row = [random.randint(0, dims-1)] * ship_len

  # Pick the first coordinate for the ship, have to subtract 
  # the ship length to make sure the ship would not go off board.
    ship_col = random.randint(0, dims - ship_len)

  # _Zip_ combines the ship_row and ship cord, _list_ makes 
  # it to list of coordinates.
    cor = list(zip(ship_row, range(ship_col, ship_col + ship_len)))

  # If the orientation is not 0 it will do the following:
  # Selects the row for the ship randomly between 0 and 
  # input dims size - 1, then multiply it to ship length list.
    else:
        ship_col = [random.randint(0, dims-1)]* ship_len

  # Do pick the first coordinate for the ship, it is needed
  # to subtract the ship length to make sure the ship would 
  # not go off board.
        ship_row = random.randint(0, dims - ship_len)

  # _Zip_ combines the ship_row and ship cord and list makes 
  # it to list.
        cor = list(zip(range(ship_row, ship_row + ship_len), ship_col))
  # Returns the coordinates.
    return cor
```

### Guessing
  This is for guessing where the ship is, also their is exit function in it and breaking protection from entering letters or to high or low number.
```python
def player_shoot():    
    # As long as the value is True this loop will run.
    while True:
        # User input is asked.
        shoot_col = input("Col: ") 
        # If user input is "exit" it will end the game, 
        # _.lower()_ is fail safe for if user has caps lock on.
        if shoot_col.lower() == "exit" or shoot_col.lower() == "q":
            # Built in exit function.
            exit()
        # This try helps to prevent game blowing up.
        try:
            # Turns user input into integer.
            int(shoot_col)
        # If try fails does this.
        except:
            # Shows this.
            print("Please enter a number without a decimel")
            # Restarts the loop.
            continue
        # When input is higher the board size or lower then 1. 
        if int(shoot_col) > len(board_size) or int(shoot_col) < 1:
            # It shows this.
            print("Please, enter number in the board.")
            # And restarts the loop.
            continue
        # If the input will pass all failsafe.
        else:
            # It ends the loop.
            break
```

#### Same as shoot_col
```python   
     while True:   
        shoot_row = input("Row:")
        if shoot_row.lower() == "exit" or shoot_row.lower() == "q":
            exit()
        try:
            int(shoot_row)
        except:
            print("Please enter a number without a decimel")
            continue
        if int(shoot_row) > len(board_size) or int(shoot_row) < 1:
            print("Please, enter number in the board.")
            continue
        else:
            break
```
  This ends the function and returns the input reduced by one because python starts counting at 0.
```python
    return (int(shoot_row)- 1, int(shoot_col) - 1)
```



### Updating
  Changing the board, showing where are the previous shots and where the ship has been hit.
```python
def update(guess, board, ship, guess_list):
    # Checks if the guess player made is allready made.
    if guess in guess_list:
        # It shows this text.
        print("You allready shot their")
    # When player hits the ship.
    elif guess in ship:
        # Shows this text.
        print("Direct hit")
        # Enters _X_ in the board.
        board[guess[0]][guess[1]] = "X"
        # Removes the location from the ship list.
        ship.remove(guess)
    # When _if_ and _elif_ is not triggered.
    else:
        # Shows this text
        print("Missed")
        # Enters **-** to the board as mark for missed shot.
        board[guess[0]][guess[1]] = "-"
        # Enters the guess to the guess_list.
    guess_list.append(guess)
    # Ends the functin and returns the updated board.
    return board
```

### Defining the board size.
```python
# This makes 4x4 size board.
board_size = build_board(4)
```

### Starting message
 Prints when starting the game.
```python
def start_message():
    print("Get ready for battle")
    print("Let's sink a ship!!!")
```
### Function to unite
 This function combines it all.
```python
def main():
    while True:
        # Calls the function to print start message.
        start_message()
        # Prints the board previously defined.
        b = board_size
        # Shows the board.
        print_board(board_size)
        # Generats the ship.
        cruiser = spawn_ship(len(board_size))  
        # Empty list where values are store after guessing.
        guess_list = []
        # Game end is defined, if the ship lenght is 0 game ends,
        # until then it cycles.
        while len(cruiser) > 0:
            # Calls the guessing function.
            player_guess = player_shoot()
            # Changes the board and checking the ship location.
            b = update(player_guess, b, cruiser, guess_list)
            # Shows the board.
            print_board(board_size)
        # Prints after cycle has ended.
        print("Congrats you sunk the ship")
        # Asks the player input if the player wants to play again.
        game_restart = input("Do you want to play again? y or n : ")
        # _.lower()_ makes the ansewr lower case and then it 
        # checks if it is **y**.
        if game_restart.lower() == "y":
        # If it is _y_ loop will run as many times as their
        # was guesses.
            for i in range(len(guess_list)):
        # **Num** gets the value of one guess, row and column
                num = guess_list[i]
        # This changes all the hits and miss markers to O, 
        # their would be a clean board again.
                board_size[num[0]][num[1]] = "O"
        # Emptying the guess list.
            guess_list.clear()
        # Starts the main function again.
            continue
        # Ends the function.
        return
```

### Calls the function
This calls the function to start the game.
```python
main()
```