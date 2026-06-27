# ATM-SYSTEM-PROGRAM
This project is a simple ATM (Automated Teller Machine) simulation developed in Python. It demonstrates the use of basic programming concepts by allowing a user to interact with an ATM-like menu after entering the correct PIN Check Balance Withdraw Money Deposit Money Exit

pin= 2422
balance=0

askPin= int(input("Enter your 4 digit ATM pin: "))


if askPin != pin:
    print("Access Denied!")
while askPin==pin:
    
    print("=====ATM OPTION=====")
    print(  "1. Check Balance")
    print(  "2. Withdraw"   )
    print(  "3. Deposit"    )
    print(  "4. Exit"      )

    askOption= int(input("Enter number from the option: "))

    if askOption==1:
        print(f"Balance: $ {balance}")
    elif askOption==2:
        askForAmount= int(input("Enter the amount you want to withdraw: "))
        if askForAmount > balance:
            print("Insufficient fund Enter Amount Again")
        else:
            balance-=askForAmount
            print("Withdraw successful!")
    elif askOption ==3:
        askForDepositAmount= int(input("Enter amount to deposit: "))
        balance+=askForDepositAmount
        print("Deposit successful!")
    elif askOption ==4:
        print("Thank you for choosing our bank.")
        break
    else:
        print("Invalid input")
