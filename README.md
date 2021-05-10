# Budget-Branch-Program
first successful attempt at using randomization 

import random

budget = 1000.00
balance = 100.00 

def mail():
  fork_in_road = ""

  print("You have mail! Type 'y' to open or any key")
  fork_in_road = input("to quit the program: ")
  
  if fork_in_road.lower() == "y":
    decision_tree = 0
    decision_tree = random.randint(1,2)

    if decision_tree == 1:
      scenario_one(budget, balance)
    else:
      scenario_two(budget, balance)
  else:
    print("Congratulations on your monthly budget. This terminates the program.")

def scenario_one(budget, balance):
  choice = ""
  refund = 0.0 

  refund = budget * 0.2
  print("You received a tax-rebate of $","{:.2f}".format(refund),sep="")
  print("")
  print("You know this is an error. If you cash the check, there is a")
  print("25% chance you'll get caught. If you're caught, you'll have to pay")
  print("the money back, with a 50% penalty-fee.")
  print("")
  print("Would you like to cash the check?")

  choice = input("type 'y' for yes or 'n' for no: ")

  if choice.lower() == "y":
    randomizer = 0
    randomizer = random.randint(1,4)

    if randomizer == 4:
      penalty = 0.0
      final_balance = 0.0

      penalty = refund * 1.5
      final_balance = balance - penalty 

      print("YOU'VE BEEN AUDITED!!")
      print("You must pay back $","{:.2f}".format(penalty),sep="")
      print("")
      print("your current balance is $","{:.2f}".format(final_balance),sep="")
      if final_balance < 0:
        print("*sad trombone*")
        print("This ends the program.")
      else:
        print("This ends the program.")

    else:
      print("Congratulations!! You didn't get caught!")
      print("Your adjusted balance is $","{:.2f}".format(balance + refund),sep="")
      print("This ends the program.")
  else:
    print("what, you afraid of a little tiny audit?")
    print("This ends the program.")

def scenario_two(budget, balance):
  bitcoin = 0.0
  password = ""

  bitcoin = budget * 0.20

  print("You received notice that you have an unclaimed BitCoin balance!")
  print("The funds are locked. You must enter the correct password to access")
  print("")
  print("You left yourself a password hint. It says 'Do you remember")
  print("the password used when you took CIS-122 years back and created")
  print("a password validator program in section 4-3?'")
  print("")
  print("It's the same password. ")

  password = input("Enter the correct password to claim your BitCoin balance: ")

  if password == "prospero":
    final_balance = 0.0

    final_balance = balance + bitcoin 
    print("password confirmed!")
    print("The BitCoin funds of $", "{:.2f}".format(bitcoin), " have been added to your account",sep="")
    print("Your final balance is $", "{:.2f}".format(final_balance),sep="")
    print("This ends the program.")
  else:
    print("incorrect password")
    print("sucka")
    print("You may try one more time. If your password is incorrect, you")
    print("will be locked out of this account for 24 hours.")

    password = input("Please enter your password: ")

    if password == "prospero":
      final_balance = 0.0

      final_balance = balance + bitcoin 
      print("password confirmed!")
      print("The BitCoin funds of $", "{:.2f}".format(bitcoin), "have been added to your account",sep="")
      print("Your final balance is $","{:.2f}".format(final_balance),sep="")
      print("This ends the program.")


mail()  

# Module mail()
#   Declare String fork_in_road  
#   
#   Display "You have mail! Type 'y' to open or any key"
#   Display " to quit the program: "
#   Input fork_in_road  
#
#   If fork_in_road.lower() == "y" Then
#     Declare Integer decision_tree
#     
#     Set decision_tree = random(1, 2)
#     If decision_tree == 1 Then
#       Call scenario_one(budget, balance)
#     Else
#       Call scenario_two(budget, balance)
#     End If
#   End If
# End Module 

# Module scenario_one(budget, balance)
#   Declare String Choice 
#   Declare Real refund  
#
#   Set refund = budget * 0.2 //programmer chose 0.2 just to make the math interesting, this will make sense later//

### SIDE IDEA: set refund in range of 0.2-0.3. May have to divide by 10.

#   Display "You received a tax-rebate of $",refund
#   Display "" 
#   Display "You know this is an error. If you cash the check, there is a"
#   Display "25% chance you'll be caught. If you're caught, you'll have to pay"
#   Display "back the money, with a 50% penalty-fee."
#   Display ""
#   Display "Would you like to cash the check?"
#   Display "type "y" for yes or "n" for no"
#   Input Choice  
#
#   If choice.lower() == "y" Then 
#     Declare Integer randomizer
#
#     Set randomizer = random.randint(1,4)
#     If randomizer == 4 Then
#        Declare Real penalty 
#        Declare Real final_balance  
#        Set penalty = refund * 1.5
#        Set final_balance = balance - penalty 
#
#        Display "YOU'VE BEEN AUDITED!!"
#        Display "You must pay back $", penalty  
#        Display ""
#        Display "your current balance is $", final balance 
#        If final_balance < 0 Then 
#          Display "*sad trombone*"
#          Display "This ends the program."
#        Else
#          Display "This ends the program."
#     Else    
#        Display "Congratulations!! You didn't get caught!"  
#        Display "Your adjusted balance is $", balance + refund 
#        Display "This ends the program."
#     End If
#   Else
#      Display "what, you afraid of a little, tiny audit? O.o"
#      Display "This ends the program."
#   End If
# End Module

# Module scenario_two(budget, balance)
#   Declare Real bitcoin
#   Declare String password 
#
#   Set bitcoin = budget * 0.20 //0.20 was chosen by programmer for parity with scenario_one()//
#   Display "You received notice that you have an unclaimed BitCoin balance!"
#   Display "The funds are locked. You must enter the correct password to access"
#   Display ""
#   Display "You left yourself a password hint. It says 'Do you remember'"
#   Display "the password used when you took CIS-122 years back and created"
#   Display " 'a password validator program in section 4-3?'"
#   Display "It's the same password."
#   Display "Enter the correct password to claim your BitCoin balance: "
#   Input password
# 
#   If password == "prospero" Then
#     Declare Real final_balance
#
#     Set final_balance = balance + bitcoin 
#     Display "password confirmed!" 
#     Display "The BitCoin funds of $", bitcoin, "have been added to your account"
#     Display "Your final balance is $", final_balance
#     Display "This ends the program."
#
#   Else
#     Display "Incorrect password"
#     Display "You may try one more time. If your password is incorrect, you"
#     Display "will be locked out of this account for 24 hours."
#     Display "Please enter your password: "
#     Input password
#     If password == "prospero" Then 
#       Display "password confirmed!"" 
#       Display "The BitCoin funds of $", bitcoin, "have been added to your account"
#       Display "Your final balance is $", final_balance
#       Display "This ends the program."
#     Else
#       Display "Incorrect password"
#       Display "We can not access your BitCoin funds today."
#       Display "This ends the program." 
#     End If
#   End If
# End Module 
