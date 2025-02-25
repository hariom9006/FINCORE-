# FINCORE-
project based on banking management sysytem
// Banking Management System in C 
#include<stdio.h>  
#include<stdlib.h> 
 
float balance = 1000.0; 
 
void checkBalance() { 
    printf("Current balance: $%.2f\n", balance); 
} 
 
void deposit(float amount) { 
    if (amount > 0) { 
        balance += amount; 
        printf("Deposited: $%.2f\n", amount); 
        checkBalance(); 
    } else { 
        printf("Invalid amount\n"); 
    } 
} 
 
void withdraw(float amount) { 
    if (amount > 0 && amount <= balance) { 
        balance -= amount; 
        printf("Withdrawn: $%.2f\n", amount); 
        checkBalance(); 
    } else { 
        printf("Invalid amount or insufficient funds\n"); 
    } 
} 
 
int main() { 
    int choice; 
    float amount; 
 
    while(1) { 
        printf("\nBanking Management System\n"); 
        printf("1. Check Balance\n"); 
        printf("2. Deposit\n"); 
        printf("3. Withdraw\n"); 
        printf("4. Exit\n"); 
        printf("Enter choice: "); 
        scanf("%d", &choice); 
 
        switch(choice) { 
            case 1: 
                checkBalance(); 
                break; 
            case 2: 
                printf("Enter amount: "); 
                scanf("%f", &amount); 
                deposit(amount); 
                break; 
            case 3: 
                printf("Enter amount: "); 
                scanf("%f", &amount); 
                withdraw(amount); 
                break; 
            case 4: 
                printf("Thank you for using our service!\n"); 
                exit(0); 
            default: 
                printf("Invalid choice\n"); 
        } 
    } 
    return 0; 
}
