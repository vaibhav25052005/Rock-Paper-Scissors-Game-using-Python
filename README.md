# Rock-Paper-Scissors-Game-using-Python
User Input: Prompt the user to choose rock, paper, or scissors.  Computer Selection: Generate a random choice (rock, paper, or scissors) for  the computer.  Game Logic: Determine the winner based on the user's choice and the  computer's choice.  Rock beats scissors, scissors beat paper, and paper beats rock. Display Result: 
1️⃣ import random
import random


Imports Python’s random module

Used to let the computer randomly choose rock, paper, or scissors

2️⃣ get_computer_choice() function
def get_computer_choice():
    """Randomly choose rock, paper, or scissors for the computer."""
    choices = ["rock", "paper", "scissors"]
    return random.choice(choices)

What it does:

Creates a list: ["rock", "paper", "scissors"]

Uses random.choice() to pick one item randomly

Returns the computer’s choice

Example:
Computer choice → "paper"

3️⃣ determine_winner(user, computer) function
def determine_winner(user, computer):
    """Determine the winner of a round."""
    if user == computer:
        return "tie"


If both choices are same → tie

    elif (user == "rock" and computer == "scissors") or \
         (user == "scissors" and computer == "paper") or \
         (user == "paper" and computer == "rock"):
        return "user"


These are the winning conditions for the user

\ allows writing conditions on multiple lines

    else:
        return "computer"


If none of the above → computer wins

Output:

"tie", "user", or "computer"

4️⃣ play_round() function
def play_round():


This function plays ONE round of the game

✅ Taking user input safely
    while True:
        user_choice = input("Choose rock, paper, or scissors: ").lower()
        if user_choice in ["rock", "paper", "scissors"]:
            break
        print("Invalid choice! Please try again.")


while True → loop until correct input

.lower() → converts input to lowercase

Only accepts valid choices

Keeps asking if input is wrong

🎲 Computer choice
    computer_choice = get_computer_choice()


Calls the function to get computer’s random choice

🖨️ Display choices
    print(f"You chose: {user_choice}")
    print(f"Computer chose: {computer_choice}")

🏆 Decide winner
    winner = determine_winner(user_choice, computer_choice)


Calls the winner function

    if winner == "tie":
        print("It's a tie!")
    elif winner == "user":
        print("You win!")
    else:
        print("Computer wins!")

🔁 Return result
    return winner


Sends result back to main game loop

5️⃣ main() function
def main():


This is the main control center of the game

🎉 Welcome message & scores
    print("Welcome to Rock-Paper-Scissors!")
    user_score = 0
    computer_score = 0

🔄 Game loop
    while True:


Keeps playing rounds until user quits

▶️ Play round
        winner = play_round()

📊 Update score
        if winner == "user":
            user_score += 1
        elif winner == "computer":
            computer_score += 1

📢 Show score
        print(f"Score => You: {user_score} | Computer: {computer_score}")

❓ Play again?
        play_again = input("Do you want to play again? (yes/no): ").lower()

        if play_again != "yes":
            print("Thanks for playing! Final score:")
            print(f"You: {user_score} | Computer: {computer_score}")
            break


Ends game if answer is not "yes"

6️⃣ Program entry point
if __name__ == "__main__":
    main()

Why this is important:

Ensures main() runs only when the file is executed directly

Prevents auto-execution if imported into another file

🔚 Overall Flow (Simple)
Start program
↓
User chooses rock/paper/scissors
↓
Computer chooses randomly
↓
Winner decided
↓
Score updated
↓
Ask to play again
↓
Exit when user says no
