    choice = input("Choose Heads (H) or Tails (T): ").lower()
    if choice not in ['h', 't']:
        print("Invalid choice. Please choose 'H' for Heads or 'T' for Tails.")
        continue
    
    print(f"You bet ${bet_amount} on {'Heads' if choice == 'h' else 'Tails'}.")

    # Perform coin toss
    result = coin_toss()
    result_text = 'Heads' if result == 0 else 'Tails'

    print(f"The coin landed on {result_text}.")

    # Check if the player won or lost
    if (choice == 'h' and result == 0) or (choice == 't' and result == 1):
        print(f"You win! You earn ${bet_amount}.")
        balance += bet_amount  # Add bet amount to balance
    else:
        print(f"You lose! You lose ${bet_amount}.")
        balance -= bet_amount  # Subtract bet amount from balance

    # Ask the player if they want to continue
    if balance > 0:
        continue_game = input("Do you want to continue playing? (y/n): ").lower()
        if continue_game != 'y':
            print(f"Thanks for playing! Your final balance is ${balance}.")
            break
    else:
        print("You're out of money! Game over.")
        break

