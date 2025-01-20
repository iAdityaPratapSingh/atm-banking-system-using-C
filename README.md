# ATM Banking System in C
A simple ATM banking system implemented in C. This program simulates the basic functionality of an ATM, such as withdrawing money, depositing funds, and checking account balance. The application is console-based and provides a user-friendly experience with PIN authentication for security.

# Features
Secure PIN Authentication: Users need to enter a correct PIN to access the ATM system, with a maximum of 3 attempts.
Withdrawal: Allows users to withdraw money while ensuring sufficient account balance.
Deposit: Provides functionality to add funds to the account balance.
Balance Inquiry: Displays the current account balance.
Multiple Transactions: Users can perform multiple transactions until they decide to exit.
Code Modules and Explanation

# 1. Header Files

#include<stdio.h>
#include<windows.h>
#include<time.h>
stdio.h: Standard Input/Output library for basic I/O operations like printf and scanf.
windows.h: Provides Windows-specific functionality, including Beep to play a sound.
time.h: Used to display the current date and time using time and ctime.

# 2. Variables

int pin=9876, option, entered_pin, count=0, amount=1;
float balance=8765;
int continue_transaction=1;
pin: Predefined PIN for authentication (9876).
option: Stores the user's menu selection.
entered_pin: Stores the PIN entered by the user.
count: Tracks the number of incorrect attempts.
amount: Stores the amount for withdrawal or deposit.
balance: Holds the initial account balance (8765).
continue_transaction: Flag for performing multiple transactions.

# 3. Authentication


while(pin != entered_pin) {
    printf("\nPlease enter your pin :");
    scanf("%d", &entered_pin);
    if(entered_pin != pin) {
        Beep(500,450);
        printf("Invalid pin!!!");
    }
    count++;
    if(count == 3 && pin != entered_pin) {
        exit(0);
    }
}
Prompts the user to enter a PIN.
Checks if the entered PIN matches the predefined one.
Plays a beep sound on invalid entry and terminates the program after 3 incorrect attempts.

# 4. Main Menu

printf("\n\t\t\t*************Available Transaction************");
printf("\n\n\t\t1.Withdrawl");
printf("\n\t\t2.Deposit");
printf("\n\t\t3.Check Balance");
printf("\n\n\t4.Please select the option :");
scanf("%d", &option);
Displays the main menu with options for Withdrawal, Deposit, and Balance Inquiry.
Takes user input for the selected option.

# 5. Transaction Options
# Withdrawal


case 1:
    printf("\n\t\tEnter the amount : ");
    scanf("%d", &amount);
    if(balance < amount) {
        printf("\n\t Sorry insufficient balance");
    } else {
        balance -= amount;
        printf("\n\t\tYou have withdrawn Rs.%d. Your new balance is %.2f", amount, balance);
    }
    break;
Prompts the user to enter an amount to withdraw.
Ensures the account has sufficient funds.
Deducts the amount from the balance and displays the updated balance.

# Deposit

case 2:
    printf("\n\t\t Please enter the amount : ");
    scanf("%d", &amount);
    balance += amount;
    printf("\n\t\tYou have deposited Rs.%d. Your new balance is %.2f", amount, balance);
    break;
Allows the user to deposit funds.
Adds the entered amount to the account balance and displays the updated balance.

# Balance Inquiry

case 3:
    printf("\n\t\t Your balance is Rs.%.2f", balance);
    break;
Displays the current account balance.

# 6. Invalid Option Handling

default:
    Beep(500,450);
    printf("\n\t\tInvalid Option!!!");
Plays a beep sound and notifies the user if they select an invalid menu option.

# 7. Continue Transaction

printf("\n\t\tDo you wish to perform another transaction? Press 1[Yes], 0[No]");
scanf("%d", &continue_transaction);
Allows the user to perform another transaction or exit the program.

# How to Run the Code
Compile the code using a C compiler like GCC or in an IDE like Dev-C++.
Run the executable file.
Enter the PIN to authenticate.
Follow the on-screen instructions to perform transactions.
