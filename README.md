balance = 5000  # initial balance
pin = 6208
attempts = 0
print("Welcome to the ATM!")
while attempts <3:
    entered_pin = int(input("Enter your PIN: "))
    if entered_pin == pin:
        print("PIN accepted. Access granted!")
        while True:
            print("\n----- ATM MENU -----")
            print("1. Check Balance")
            print("2. Deposit Money")
            print("3. Withdraw Money")
            print("4. Exit")
            choice = int(input("Enter your choice: "))

            if choice == 1:
                print("Your current balance is:", balance)

            elif choice == 2:
                amount = float(input("Enter amount to deposit: "))
                balance += amount # balance = balance+amount
                print("Amount deposited successfully!")

            elif choice == 3:
                amount = float(input("Enter amount to withdraw: "))
                if amount > balance:
                    print("Insufficient balance!")
                else:
                    balance -= amount
                    print("Withdrawal successful!")

            elif choice == 4:
                print("Thank you for using our ATM. Goodbye!")
                break

            else:
                print("Invalid choice. Please try again.")
        break  # Exit the outer while loop after successful login

    else:
        attempts += 1
        print("Incorrect PIN! Attempts left:", 3 - attempts)
if attempts == 3:
    print("ATM blocked due 62345to 3 incorrect PIN attempts. Please contact the bank.")
