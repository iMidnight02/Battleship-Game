while True: #making the game loop so that the user can play again if they want to
    ship_place_row = 3; 
    ship_place_column = 4;

    print("Welcome to the battleship game!");
    print("The computer has placed a ship on the grid which is about 10x10. Try to guess where it is! \n You only have 5 tries though.");

    attempts = 5;
    won = 0;


    # The main game loop, it will continue until the user runs out of attempts or wins the game
    while attempts > 0 and won == 0:
        print("\nRemaining attempts:");
        print(attempts);


        # Getting the user's guess for the row and column, and checking if it's valid
        guess_row = int(input("Guess Row: "));
        guess_column = int(input("Guess Column: "));
        if guess_row < 1 or guess_row > 10 or guess_column < 1 or guess_column > 10:
            print("Oops, that's not even in the ocean. Try again!")
        
        # Checking if the user's guess is correct, if it's a hit or a miss, and providing hints accordingly
        elif guess_row == ship_place_row and guess_column == ship_place_column:
            print("Congratulations! You sunk the battleship!");
            won = 1;
        # If the user's guess is incorrect, it will decrease the number of attempts and provide hints to help them find the battleship
        else:
            attempts = attempts - 1;
            print("You missed the battleship! Try again!");

        if guess_row > ship_place_row:
            print("Hint: Go more High!")
        elif guess_row < ship_place_row:
            print("Hint: Go more Low!")

        if guess_column > ship_place_column:
            print("Hint: Go more Left!")
        elif guess_column < ship_place_column:
            print("Hint: Go more Right!")
        
        # If the user runs out o[index.py](https://github.com/user-attachments/files/26324613/index.py)
f attempts and hasn't won the game, it will reveal the location of the battleship
        if won == 0:
            print("\nGame Over! The battleship was located at Row: ",ship_place_row ," Column: " , ship_place_column);


    # After the game ends, it will ask the user if they want to play again. If they choose to play again, it will restart the game loop. If they choose not to play again, it will thank them for playing and exit the program.
    print("Do you want to play again?");
    play_again = str(input("Play Again? (Y/N): "));
    if play_again == "Y":
        print("Restarting the game...\n\n");

    if play_again == "N":
        print("Thank you for playing! Goodbye!\n \n Game developed by: Xrys");
        break;


