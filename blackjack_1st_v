import random
cards = [11, 2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10]
carte_utente = []
carte_computer = []
capitale = 300
scommessa = None

def fix_As(cards_list):
    while sum(cards_list) > 21 and 11 in cards_list:
        cards_list.remove(11)
        cards_list.append(1)
    return cards_list

def primo_giro(capitale):
    user_cards = []
    computer_cards = []
    while True:
        wish_to_play = input("Do you want to play blackjack? ").lower()
        if wish_to_play == "yes" or wish_to_play == "y":
            bet = int(input("Place your bet. 1, 5, 10, 25, 50 "))
            capitale -= bet
            for item in range(0,2):
                user_cards.append(random.choice(cards))
                computer_cards.append(random.choice(cards))
        print(f"Your cards are {user_cards} and the sum of your cards is {sum(user_cards)}")
        print(f"Computer cards are {computer_cards[0]}, X")
        return user_cards, computer_cards, capitale, bet

def more_cards(user_cards):
    while sum(user_cards) < 21:
        wish = input("Do you want another card? Type yes or no").lower()
        if wish == "yes" or wish == "y":
            user_cards.append(random.choice(cards))
            fix_As(user_cards)
            print(f"Your cards are {user_cards} and the sum of your cards is {sum(user_cards)}")
        else:
            print(f"Your cards are {user_cards} and the sum of your cards is {sum(user_cards)}")
            break
    return user_cards

def more_cards_comp(computer_cards):
    while sum(carte_utente) <= 21 and sum(computer_cards) <17:
        computer_cards.append(random.choice(cards))
        fix_As(computer_cards)
    print(f"Computer cards are {computer_cards} and the sum is {sum(computer_cards)}")
    return computer_cards

def calcolo_punteggio(user_cards, computer_cards):
    user_score = sum(user_cards)
    computer_score = sum(computer_cards)

    if user_score == 21 and computer_score == 21:
        print("Computer wins")
        return "computer"
    elif user_score > 21:
        print("Computer wins")
        return "computer"
    elif computer_score <= 21 and computer_score > user_score:
        print("Computer wins")
        return "computer"
    elif computer_score == user_score:
        print("It's a draw! ")
        return 'Draw'
    elif computer_score > 21 and user_score <= 21:
        print("User wins")
        return "User"
    else:
        print("User wins")
        return "User"

def accredito_vincita(vincitore, capital, bet):
    if vincitore == "User":
        capital += bet * 2
    elif vincitore == "Draw":
        capital += bet
    else:
        capital

    bet = None
    return bet, capital

while capitale > 0:
    carte_utente, carte_computer, capitale, scommessa = primo_giro(capitale)
    carte_utente = more_cards(carte_utente)
    carte_computer = more_cards_comp(carte_computer)
    fix_As(carte_utente)
    fix_As(carte_computer)
    winner_is = calcolo_punteggio(carte_utente, carte_computer)
    scommessa, capitale = accredito_vincita(winner_is, capitale, scommessa)

