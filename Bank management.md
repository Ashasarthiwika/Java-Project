#include <stdio.h>
int main() {
    float balance = 0.0, amount;
    int choice;
    while (1) {
        printf("\n===== Bank Management System =====\n");
        printf("1. Deposit Money\n");
        printf("2. Withdraw Money\n");
        printf("3. Check Balance\n");
        printf("4. Exit\n");
        printf("Enter your choice: ");
        scanf("%d", &choice);
        switch (choice) {
            case 1: 
                printf("Enter amount to deposit: ");
                scanf("%f", &amount);

                if (amount > 0) {
                    balance += amount;
                    printf("Deposit successful! Current Balance: %.2f\n", balance);
                } else {
                    printf("Invalid amount! Deposit must be greater than zero.\n");
                }
                break;
            case 2: 
                printf("Enter amount to withdraw: ");
                scanf("%f", &amount);

                if (amount <= 0) {
                    printf("Invalid amount! Withdrawal must be greater than zero.\n");
                } else if (amount > balance) {
                    printf("Insufficient balance! Current Balance: %.2f\n", balance);
                } else {
                    balance -= amount;
                    printf("Withdrawal successful! Current Balance: %.2f\n", balance);
                }
                break;
            case 3: 
                printf("Current Balance: %.2f\n", balance);
                break;
            case 4: 
                printf("Exiting program...\n");
                return 0;
            default:
                printf("Invalid choice! Please try again.\n");
        }
    }
    return 0;
}
