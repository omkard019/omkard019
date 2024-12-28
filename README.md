#include <stdio.h>

int main() {
    int pin = 1234, enteredPin, option;
    double balance = 1000.00; // Initial balance
    double deposit, withdraw;

    printf("Enter ATM PIN: ");
    scanf("%d", &enteredPin);

    // Check if entered pin is correct
    if (enteredPin != pin) {
        printf("Incorrect PIN. Access denied.\n");
        return 0; // End the program if the PIN is incorrect
    }

    while (1) {
        // Display options to the user
        printf("\nATM Menu:\n");
        printf("1. Check Balance\n");
        printf("2. Deposit\n");
        printf("3. Withdraw\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &option);

        switch (option) {
            case 1: // Check Balance
                printf("Your current balance is: $%.2f\n", balance);
                break;

            case 2: // Deposit
                printf("Enter amount to deposit: $");
                scanf("%lf", &deposit);
                if (deposit > 0) {
                    balance += deposit;
                    printf("You have successfully deposited $%.2f\n", deposit);
                } else {
                    printf("Invalid deposit amount.\n");
                }
                break;

            case 3: // Withdraw
                printf("Enter amount to withdraw: $");
                scanf("%lf", &withdraw);
                if (withdraw <= balance) {
                    balance -= withdraw;
                    printf("You have successfully withdrawn $%.2f\n", withdraw);
                } else {
                    printf("Insufficient balance.\n");
                }
                break;

            case 4: // Exit
                printf("Thank you for using the ATM. Goodbye!\n");
                return 0; // Exit the program

            default:
                printf("Invalid choice. Please try again.\n");
        }
    }

    return 0;
}

