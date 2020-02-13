#!/usr/bin/env python3
# -*- coding: utf-8 -*-
"""
Created on Tue Sep 17 17:51:12 2019

@author: sofiaportillo
"""

"""
Course: Introduction to Python Programming
Student Name: Sofia Portillo
"""
#%% 
from random import randint
#note: x=randint(0, 10) will generate a random integer x and 0<=x<=10
# %%
def HumanPlayer(GameRecord):
    print("let's play...................")
    print("rock(r), paper(p), sissors(s)?")
    print("or do you want to see a record of the game (g)?")
    print("or do you want to quit(q)?")
    hchoice = input("Please make your choice now:")
    
    while (hchoice != 'r') and (hchoice != 'p') and (hchoice != 's') and (hchoice != 'g') and (hchoice != 'q') and (hchoice != 'rock') and (hchoice != 'paper') and (hchoice != 'scissors') and (hchoice != 'game') and (hchoice != 'quit'):
        print("The computer does not understand your input")
        print("let's play...................")
        print("rock(r), paper(p), sissors(s)?")
        print("or do you want to see a record of the game (g)?")
        print("or do you want to quit(q)?")
        hchoice = input("Please make your choice now:")
        
    
    if(hchoice == 'r'):
        hchoice = 'rock'
    elif(hchoice == 'p'):
        hchoice = 'paper'
    elif(hchoice == 's'):
        hchoice = 'scissors'
        
    return(hchoice)
    '''
    Parameter: GameRecord (the record of both players' choices and outcomes)
    Return: HumanChoice, a string that can only be an element in the set 
            {'rock', 'r', 'paper', 'p', 'scissors', 's', 'game', 'g', 'quit', 'q'}
    Description:
        This function asks the user to make a choice (i.e. input a string)        
        valid inputs are: rock or r, paper or p, scissors or s, game or g, quit or q
            quit means the user wants to quit the game
            game means the user wants to see the GameRecord
        This function will NOT return/exit until it gets a valid input from the user
            Thus, you need a while loop
    suggestion:
        HumanChoice in the set {'r', 'p', 's', 'g', 'q'}
    '''
# %%
def ComputerPlayer(GameRecord):
    
    x = randint(1,3)
    cchoice = ''
    if x == 1:
        cchoice = 'rock'
    elif x == 2:
        cchoice = 'paper'
    elif x == 3:
        cchoice = 'scissors'
    
    return(cchoice)
    '''
    Parameter: GameRecord (the record of both players' choices and outcomes)
    Return: ComputerChoice, a string that can only be in the set
            {'rock', 'r', 'paper', 'p', 'scissors', 's'}
    Description:
        ComputerPlayer will randomly make a choice
        ComputerPlayer should not look at the current choice of HumanPlayer
    '''

# %%
def Judge(ComputerChoice, HumanChoice):
    
    if (HumanChoice[0] == ComputerChoice[0]):
        outcome = 0
    elif (HumanChoice[0] == 'r') and (ComputerChoice[0] == 'p'):
        outcome = 1
    elif (HumanChoice[0] == 'p') and (ComputerChoice[0] == 's'):
        outcome = 1
    elif (HumanChoice[0] == 's') and (ComputerChoice[0] == 'r'):
        outcome = 1
    elif (HumanChoice[0] == 'r') and (ComputerChoice[0] == 's'):
        outcome = 2
    elif (HumanChoice[0] == 'p') and (ComputerChoice[0] == 'r'):
        outcome = 2
    elif (HumanChoice[0] == 's') and (ComputerChoice[0] == 'p'):
        outcome = 2
    else:
        outcome = 10
        print('error')
        
    return(outcome)
    
    '''
    Parameters:
        ComputerChoice is a string from ComputerPlayer
        HumanChoice is a string from HumanPlayer
    Return: Outcome
        Outcome is 0 if it is a draw/tie
        Outcome is 1 if ComputerPlayer wins
        Outcome is 2 if HumanPlayer wins
    Description:
        this function determines the outcome of a game
    '''

# %%
def PrintOutcome(Outcome, ComputerChoice, HumanChoice):
    
    
    
    print('')
    print('----------------------------------------Outcome----------------------------------------')
    
    if Outcome == 0:
        print("It is a tie: ", end = '')
    elif Outcome == 1:
        print("Computer wins: ", end = '')
    elif Outcome == 2:
        print("Human wins: ", end = '')
    
    if HumanChoice[0] == 'r':
        print("Computer chose", ComputerChoice, "; Human chose rock")
    if HumanChoice[0] == 'p':
        print("Computer chose", ComputerChoice, "; Human chose paper")
    if HumanChoice[0] == 's':
        print("Computer chose", ComputerChoice, "; Human chose scissors")
    
    
    
    
    print('---------------------------------------------------------------------------------------')
    print('')
    
    '''
    Parameters:
        Outcome is from Judge
        ComputerChoice is a string from ComputerPlayer
        HumanChoice is a string from HumanPlayer
    Return: None
    Description:
        print Outcome, Choices and Players to the console window
        the message should be human readable
    '''

# %%
def UpdateGameRecord(GameRecord, ComputerChoice, HumanChoice, Outcome):
    
    GameRecord['HumanPlayer'].append(HumanChoice)
    GameRecord['ComputerPlayer'].append(ComputerChoice)
    GameRecord['Outcome'].append(Outcome)
    
    '''
    Parameters: 
        GameRecord is the record of both players' choices and and outcomes
        ComputerChoice is a string from ComputerPlayer
        HumanChoice is a string from HumanPlayer
        Outcome is an integer from Judge
    Return: None
    Description:
        this function updates GameRecord, a list of three lists or a dictionary
    '''
# %%
def PrintGameRecord(GameRecord):
    
    print('')
    print('-------Record of the Game-------')
    numRounds = len(GameRecord['Outcome'])
    CompWins = 0
    HumWins = 0
    for e in GameRecord['Outcome']:
        if e == 1:
            CompWins += 1
        elif e == 2:
            HumWins += 1
    
    
    
    print('Number of rounds is', numRounds)
    print('Human wins', HumWins, 'round(s)')
    print('Computer wins', CompWins, 'round(s)')
    print('Human, Computer')
    for a,b in zip(GameRecord['HumanPlayer'],GameRecord['ComputerPlayer']):
        print(a, ",", b)
    print('')    
        
    '''
    Parameters: GameRecord (the record of both players' choices and outcomes)
    Return: None
    Description: this function prints the record of the game (see the sample run)
        the number of rounds. human wins x rounds. computer wins y rounds.
        the record of choices.
    '''
# %% the game
def PlayGame():
    print("Welcome to rock-paper-scissors !")
    game_record={"HumanPlayer":[], "ComputerPlayer":[], "Outcome":[]}    
    while True:        
        human_choice = HumanPlayer(game_record)        
        if human_choice == 'quit' or human_choice == 'q':
            break
        elif human_choice =='game' or human_choice == 'g':
            PrintGameRecord(game_record)
        else:
            computer_choice = ComputerPlayer(game_record)
            outcome = Judge(computer_choice, human_choice)
            PrintOutcome(outcome, computer_choice, human_choice)
            UpdateGameRecord(game_record, computer_choice, human_choice, outcome)
    print("------------GameOver----------")    
# %% do not modify anything below
if __name__ == '__main__':
    PlayGame()
 
