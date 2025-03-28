import random
print("***Guess a number betwen 1 and 50. You have 5 attempts***")
attempts = 5
number = random.randint(1,50)
def get_integer_input(prompt):
    while True:
        user_input = input(prompt)
        try:
            value = int(user_input)
            return value
        except ValueError:
            print("Invalid input. Please enter an integer.")
while True:
    guess = get_integer_input("Your guess: ")
    attempts -= 1
    if attempts == 0 and guess == number:
        print("Correct! last attempt right! That was close.")
        TryAgain1 = input("Would you like to play again? (y/n): ").lower()
        if TryAgain1 == 'y':
            number = random.randint(1,50)
            attempts = 5
            continue
        if TryAgain == 'n':
            print("Exiting...Next time!")
            break
    if attempts == 0 and guess != number:
        TryAgain = input(f"No more attempts. The number is {number}. Play again? (y/n): ").lower()
        if TryAgain == 'y':
            number = random.randint(1,50)
            attempts = 5
            continue
        if TryAgain == 'n':
            print("Exiting...Next time!")
            break
    if guess == number:
        print(f"Correct! The number is {number}.")
        break
    elif guess > number:
        print(f"Try a smaller number....{attempts} attempts left.)")
    elif guess < number:
        print(f"Try a bigger number....{attempts} attempts left.)")
