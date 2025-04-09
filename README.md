# DSAproject
Banking Algorithm

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
struct Account {
int account_number;
char name[50];
float balance;
};
void createAccount(struct Account* acc);
void deposit(struct Account* acc);
void withdraw(struct Account* acc);
void checkBalance(struct Account* acc);
int main() {
struct Account account;
int choice;
account.balance = 0.0;
printf("Welcome to the Simple Banking System\n");
printf("************************************\n");
do {
printf("\nPlease choose an option:\n");
printf("1. Create an Account\n");
printf("2. Deposit Money\n");
printf("3. Withdraw Money\n");
printf("4. Check Balance\n");
printf("5. Exit\n");
printf("Enter your choice: ");
scanf("%d", &choice);
switch (choice) {
case 1:
createAccount(&account);
break;
case 2:
deposit(&account);
break;
case 3:
withdraw(&account);
break;
case 4:
checkBalance(&account);
break;
case 5:
printf("Thank you for using the banking system. Goodbye!\n");
break;
default:
printf("Invalid choice! Please try again.\n");
}
} while (choice != 5);

return 0;
}
void createAccount(struct Account* acc) {
printf("Enter account holder's name: ");
getchar();
fgets(acc->name, sizeof(acc->name), stdin);
acc->name[strcspn(acc->name, "\n")] = '\0';
printf("Enter initial deposit amount: ");
scanf("%f", &acc->balance);
acc->account_number = rand() % 10000 + 1000;
printf("Account created successfully! Your account number is %d\n", acc->account_number);
}
void deposit(struct Account* acc) {
float depositAmount;
printf("Enter amount to deposit: ");
scanf("%f", &depositAmount);

if (depositAmount > 0) {
    acc->balance += depositAmount;
    printf("Deposited successfully! New balance is %.2f\n", acc->balance);
} else {
    printf("Invalid deposit amount!\n");
}
}
void withdraw(struct Account* acc) {
float withdrawAmount;
printf("Enter amount to withdraw: ");
scanf("%f", &withdrawAmount);
if (withdrawAmount > 0 && withdrawAmount <= acc->balance) {
acc->balance -= withdrawAmount;
printf("Withdrawal successful! New balance is %.2f\n", acc->balance);
} else if (withdrawAmount > acc->balance) {
printf("Insufficient funds for withdrawal!\n");
} else {
printf("Invalid withdrawal amount!\n");
}
}
void checkBalance(struct Account* acc) {
printf("Account Number: %d\n", acc->account_number);
printf("Account Holder's Name: %s\n", acc->name);
printf("Current Balance: %.2f\n", acc->balance);
}
