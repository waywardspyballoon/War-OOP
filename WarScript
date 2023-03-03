from random import shuffle

RANKS = {1: "Deuces", 2: "Threes", 3: "Fours",
        4: "Fives", 5: "Sixes", 6: "Sevens",
        7: "Eights", 8: "Nines", 9: "Tens",
        10: "Jacks", 11: "Queens", 12: "Kings",
        13: "Aces"}

SINGRANK = {1: "Deuce", 2: "Three", 3: "Four",
        4: "Five", 5: "Six", 6: "Seven",
        7: "Eight", 8: "Nine", 9: "Ten",
        10: "Jack", 11: "Queen", 12: "King",
        13: "Ace"}

SUITS = {1: "Clubs",
         2: "Diamonds",
         3: "Hearts",
         4: "Spades"}

class GameInit:
    def __init__(self):
        rank = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13]
        suit = [1, 2, 3, 4]
        self.deck = [(rnk, sut) for rnk in rank for sut in suit]
        shuffle(self.deck)
        self.firstdeal = True
        self.p1hand = self.deck.pop(0)
        self.p2hand = self.deck.pop(0)
        self.player1 = ''
        self.player2 = ''
        self.p1score = 0
        self.p2score = 0

    def __repr__(self):
        return f'{SINGRANK[self.p1hand[0]]} of {SUITS[self.p1hand[1]]}, {self.p2hand}'

    def player(self, p1, p2):
        self.player1 = p1
        self.player2 = p2


    def deal(self):
        if len(self.deck) > 1:
            self.p1hand = self.deck.pop(0)
            self.p2hand = self.deck.pop(0)

    def eval(self):
        print(f'Player 1 hand {SINGRANK[self.p1hand[0]]} of {SUITS[self.p1hand[1]]} \n'
              f'Player 2 hand {SINGRANK[self.p2hand[0]]} of {SUITS[self.p2hand[1]]}')
        if self.p1hand[0] > self.p2hand[0]:
            print('player 1 wins!')
            self.p1score += 1
            return
        elif self.p1hand[0] == self.p2hand[0]:
            if self.p1hand[1] > self.p2hand[1]:
                print('player 1 wins!')
                self.p1score += 1
                return
            else:
                print('player 2 wins!')
                self.p2score += 1
                return
        self.p2score += 1
        print('player 2 wins!')
        return



    def maingame(self):
        play1 = input('enter name of player 1')
        play2 = input('enter name of player 2')
        self.player(play1, play2)
        while len(self.deck) > 1:
            dealStatus = input('deal a new hand? y / n').lower()
            if dealStatus == 'y' and self.firstdeal == False:
                self.deal()
                self.firstdeal = False
            if dealStatus == 'n':
                exit()
            elif dealStatus not in 'yn' or dealStatus == '':
                print('invalid entry, try again')
                continue
            self.eval()
            self.firstdeal = False
        print(f'deck has been exhausted')
        if self.p1score > self.p2score:
            print(f'{play1} wins WAR!')
        elif self.p1score < self.p2score:
            print(f'{play2} wins WAR!')
        else:
            print('tie!')
        pA = True
        while pA == True:
            playAgain = input('Play again? y / n').lower()
            if playAgain == 'y':
                pA = False
                newgame = GameInit()
                newgame.maingame()
            elif playAgain == 'n':
                exit()
            else:
                print('invalid entry, try again')
                continue

initialize = GameInit()
initialize.maingame()

