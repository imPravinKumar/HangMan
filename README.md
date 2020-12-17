# HangMan
# Buliding an Game
import random
def hangman():

    word_list = ['phone','black','internet','program','notepad','keyboard']
    word = random.choice(word_list)
    turns = 6
    guessword = ''
    valid_entry = set('abcdefghijklmnopqrstuvwxyz')

    while len(word)>0:
        main_word = ""
        missed = 0

        for letter in word:
            if letter in guessword:
                main_word = main_word+letter
            else:
                main_word = main_word+"_ "

        if main_word == word:
            print(main_word)
            print("YOU WON!")
            break
        
        print("guess the word", main_word)
        guess = input()

        if guess in valid_entry:
            guessword = guessword + guess
        else:
            print("enter valid character")
            guess = input()

        if guess not in word:
            turns = turns-1

            if turns==5:
                print("YOU MISSED 5 TURNS LEFT")
                print("-----------------------")
            if turns==4:
                print("YOU MISSED 4 TURNS LEFT")
                print("-----------------------")
                print("           0           ")
            if turns==3:
                print("YOU MISSED 3 TURNS LEFT")
                print("-----------------------")
                print("           0           ")
                print("           |           ")
            if turns==2:
                print("YOU MISSED 2 TURNS LEFT")
                print("-----------------------")
                print("           0           ")
                print("           |           ")
                print("          / \          ")
            if turns==1:
                print("LAST CHANCE 1 TURNS LEFT")
                print("-----------------------")
                print("           0           ")
                print("          /|\          ")
                print("          / \          ")
            if turns==0:
                print("YOU  DIED")
                print("-----------------------")
                print("           0_|         ")
                print("          /|\          ")
                print("          / \          ")
                break



name = input("ENTER YOUR SWEET NAME:")
print("HI",name)
print("````````````````````````````````")
print("Welcome to Hangman game"",""save yourself by guessing the correct word" ":)")
print("you will be given 5 chance ")
print("Good Luck" "!")

hangman()
