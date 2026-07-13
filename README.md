import random
print("welcome to hangman_game!..")
print("Read rules of the game :")
print("you should a fruit name in this game..")
print("you can guess only one letter at a time..")
print("you have only 5 attempts left!..")



words = ["apple","banana","orange","grapes","guava","mango","dragon","peach","lemon"]
guessing_word = random.choice(words)
display = []
attempts = 5


for i in range(len(guessing_word)):
    display += "_"
print(display)

game_over = False
while not game_over:
    guessed_letter = input("enter a letter : ").lower()
    for position in range(len(guessing_word)):
        i = guessing_word[position]
        if i == guessed_letter:
            display[position] = guessed_letter
            print("congrats!..")
    print(display)

    if guessed_letter not in guessing_word:
        attempts -= 1
        print(f"you have only {attempts} chances left...")
        if attempts == 0:
            game_over = True
            print("you loose!..")

    if "_" not in display:
        game_over = True
        print("you won!..")
