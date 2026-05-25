# Logic-Deducing-Game
This game uses a secret number that the user must guess, and gives hints to whether you have the right number in the right position, wrong position, or you just have the wrong number.

def bagels(secret_number):
    import random
    guess = 1
    
    
    print(f'Bagels, a deductive logic game.\nBy Al Sweigart al@inventwithpython.com\nI am thinking of a 3-digit number. Try to guess what it is.\nHere are some clues:\nWhen I say:    That means:')
    print('  Pico         One digit is correct but in the wrong position.\n  Fermi        One digit is correct and in the right position.\n  Bagels       No digit is correct.\nI have thought up a number.\n You have 10 guesses to get it.')

    while guess <= 10:
        
        pico = 0
        fermi = 0  
        game = False
        bagelz = ''
        guess_input = input(f'Guess # {guess} ')
        guess += 1
        
        for i in range(len(secret_number)):
            number = secret_number[i]
            
            
            if number == guess_input[i]:
                fermi += 1
            
            elif number not in guess_input:
                bagelz += 'bagels'
                
        
            else:
                pico += 1
                
        if pico > 0:
            print('Pico ' * pico)
            
        
        elif fermi > 0 and fermi < 3:
            print('Fermi ' * fermi)
        
        elif bagelz != '':
            print('Bagels')
            
        elif secret_number == guess_input:
            print('You got it!')
            game = True
            
            
        
        while game == True:
                    
                guess_input = input('Do you want to play again? (yes or no) ')
                if guess_input.strip().lower() == 'no':
                        print('Thanks for playing!')
                        return
                        
                elif guess_input.lower() == 'yes':
                        bagels(str(random.randint(100, 999)))
                        guess = 1
                        return  
print(bagels('701'))


