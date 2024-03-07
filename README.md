# snake-and-ladder-game
Players roll a die to advance on a 10-space board encountering ladders &amp; snakes. Rolling a 6 grants an extra roll, max 3 per turn. Invalid moves keep players in place. Game ends when reaching the final space, ranks by finishing order.
//code

import random
# Function to roll a dice
def roll_dice():
 return random.randint(1, 6)
# Function to move the player's position on the board
def move_player(player, roll):
 player += roll
 if player in snakes.keys():
 print("Oops! You encountered a snake. Going down to", 
snakes[player])
 player = snakes[player]
 elif player in ladders.keys():
 print("Yay! You found a ladder. Going up to", ladders[player])
 player = ladders[player]
 return player
# Function to check if the player has won
def has_won(player):
 return player >= 100
# Initialize the game
player1 = 0
player2 = 0
# Define snakes and ladders positions
snakes = {16: 6, 47: 26, 49: 11, 56: 53, 62: 19, 64: 60, 87: 24, 93: 73, 
95: 75, 98: 78}
ladders = {1: 38, 4: 14, 9: 31, 21: 42, 28: 84, 36: 44, 51: 67, 71: 91, 80: 
100}
# Main game loop
while True:
 input("Player 1, press Enter to roll the dice...")
 roll = roll_dice()
 print("Player 1 rolled a", roll)
 player1 = move_player(player1, roll)
 print("Player 1 is now at position", player1)
 
 if has_won(player1):
 print("Player 1 has won!")
 break
 
 input("Player 2, press Enter to roll the dice...")
 roll = roll_dice()
 print("Player 2 rolled a", roll)
 player2 = move_player(player2, roll)
 print("Player 2 is now at position", player2)
 
 if has_won(player2):
 print("Player 2 has won!")
 break
