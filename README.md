# rock-paper-scissors
import random

def get_computer_choice():
    return random.choice(["rock", "paper", "scissors"])

def determine_winner(user, computer):
    if user == computer:
        return "tie"
    elif (
        (user == "rock" and computer == "scissors") or
        (user == "paper" and computer == "rock") or
        (user == "scissors" and computer == "paper")
    ):
        return "win"
    else:
        return "lose"

def display_result(user, computer, result):
    print(f"\nYou chose: {user}")
    print(f"Computer chose: {computer}")
    if result == "tie":
        print("It's a tie!")
    elif result == "win":
        print("You win!")
    else:
        print("You lose.wins!")

def main():
    user_score = 0
    computer_score = 0

    print("Welcome to Rock-Paper-Scissors Game!")
    print("Instructions: Type rock, paper, or scissors to play. Type 'exit' to quit.\n")

    while True:
        user_choice = input("Enter your choice: ").strip().lower()
        if user_choice == "exit":
            print("Thanks for playing!")
            break

        if user_choice not in ["rock", "paper", "scissors"]:
            print("Invalid input! Please type rock, paper, or scissors.\n")
            continue

        computer_choice = get_computer_choice()
        result = determine_winner(user_choice, computer_choice)

        display_result(user_choice, computer_choice, result)

        if result == "win":
            user_score += 1
        elif result == "lose":
            computer_score += 1

        print(f"Score -> You: {user_score} | Computer: {computer_score}\n")

if __name__ == "__main__":
    main()
