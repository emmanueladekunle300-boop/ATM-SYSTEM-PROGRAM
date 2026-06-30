# ATM-SYSTEM-PROGRAM
This project is a simple ATM (Automated Teller Machine) simulation developed in Python. It demonstrates the use of basic programming concepts by allowing a user to interact with an ATM-like menu after entering the correct PIN Check Balance Withdraw Money Deposit Money Exit

#Ask user to create a atm pin
aksForPassword= int(input("Enter a 4 digit password to set your ATM pin: "))
pinPassword=aksForPassword

#Ask use to choose to continue or to not
print("Now you can have access to your bank !")
askForContinuetion= input("Will you like to continue (y/n): ")

#Variable for balance to use in the code
balance=0

#Comparing the answer inputed by the use to execute the program or to stop 
if askForContinuetion == "n":
    print("Thank you for choosing us")
elif askForContinuetion== "y":
    #Ask user for pin 
    askPin= int(input("Enter your 4 digit ATM pin: "))
    #Comparing the inputed answer using if statement
    if askPin != pinPassword:
        print("Access Denied!")
    while askPin==pinPassword:
        #The option to choose
        print("=====ATM OPTION=====")
        print(  "1. Check Balance")
        print(  "2. Withdraw"   )
        print(  "3. Deposit"    )
        print(  "4. Exit"      )
        print(  "5. Reset pin"      )
        #Ask user to choose from the option above
        askOption= int(input("Enter number from the option: "))
        #Comparing the option selected to carry out operation
        if askOption == 1:
            print(f"Balance: $ {balance}")
        elif askOption == 2:
            askForAmount= int(input("Enter the amount you want to withdraw: "))
            askForTheWithDrawalPin= int(input("Enter your pin:"))
            #Ask user for the pin created to withdraw money
            if askForTheWithDrawalPin == pinPassword:
                if askForAmount > balance:
                    print("Insufficient fund Enter Amount Again")
                else:
                    balance-=askForAmount
                    print("Withdraw successful!")

        elif askOption == 3:
            askForDepositAmount= int(input("Enter amount to deposit: "))
            balance+=askForDepositAmount
            print("Deposit successful!")

        elif askOption == 4:
            print("Thank you for choosing our bank.")
            break

        elif askOption == 5:
            askForResetPin= int(input("Enter your old pin: "))
            if askForResetPin == pinPassword:
                askForNewPassword= int(input("Enter your new password: "))
                pinPassword==askForNewPassword
                print("Password Reset Successful!")

        else:
            print("Invalid option")
