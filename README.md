# Word-play
Please go through the code and tell me the mistake in aforb. I am always getting 0 as the result. The code is in python.


# Word Play

import math
fin = open('words.txt')

# Function to find word having no 'e'.

def has_no_e (word):
    for letter in word:
        if letter == 'e':
            return False
    return True

# Function to print words without 'e' and find percentage of words not having 'e'.

def print_no_e ():
    ne = 0
    ye = 0
    for line in fin:
        word = line.strip()
        x = has_no_e (word)
        if x == True:
            ne = ne +1
            print (word)
        else:
            ye = ye + 1
    pne = (ne/ye)*100
    print (pne)

# Function to check that the given word doesnt contain the given letters.

def avoids (word, forbidden):
    for letter in word:
        if letter in forbidden:
            return False
    return True

# Function to print words that doesnt contain the given letters.

def aforb (forbidden):
    count = 0
    for line in fin:
        word = line.strip()
        x = avoid (word, forbidden)
        if x == True:
            count = count + 1
            print (word)
    print (count)

# Function to identify if the word is made up of given set of letters.

def uses_only (word, random):
    for letter in word:
        if letter not in random:
            return False
    return True

# Function to identify if the word uses given set of letters atleast once.

def uses_all (word, given):
    for letter in given:
        if letter not in word:
            return False
    return True

# Function to check if the letters of the given word is in alphabetical order.

def is_alphabetical (word):
    previous = word[0]
    for letter in word:
        if letter < previous:
            return False
        previous = letter
    return True
