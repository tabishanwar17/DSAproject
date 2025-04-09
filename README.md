# DSAproject

# Simple Banking System in C

This repository contains a simple command-line banking system implemented in the C programming language. It allows users to create an account, deposit and withdraw funds, and check their account balance.

## Features

* **Create Account:** Allows a user to create a new bank account by providing their name and an initial deposit. A unique account number is automatically generated.
* **Deposit Money:** Enables users to deposit funds into their existing account.
* **Withdraw Money:** Allows users to withdraw funds from their account, with a check for sufficient balance.
* **Check Balance:** Displays the account number, account holder's name, and the current balance of the account.
* **Simple Command-Line Interface:** Provides an easy-to-use menu-driven interface for interacting with the banking system.

### Compilation

1.  Save the provided C code into a file named `banking_system.c`.
2.  Open your terminal or command prompt.
3.  Navigate to the directory where you saved the file.
4.  Compile the code using the following command:

    ```bash
    gcc banking_system.c -o banking_system
    ```

### Running the Program

1.  After successful compilation, you can run the executable using the following command:

    ```bash
    ./banking_system
    ```

2.  The program will then display a menu with the available options. Follow the prompts to interact with the banking system.

## How to Use

1.  **Create an Account (Option 1):**
    * Enter `1` and press Enter.
    * You will be prompted to enter the account holder's name. Type the name and press Enter.
    * You will then be asked for the initial deposit amount. Enter the amount and press Enter.
    * A unique account number will be generated and displayed.

2.  **Deposit Money (Option 2):**
    * Enter `2` and press Enter.
    * Enter the amount you wish to deposit and press Enter.
    * The program will confirm the deposit and display the new balance.

3.  **Withdraw Money (Option 3):**
    * Enter `3` and press Enter.
    * Enter the amount you wish to withdraw and press Enter.
    * The program will check for sufficient funds and, if available, process the withdrawal and display the new balance. Otherwise, it will display an "Insufficient funds" message.

4.  **Check Balance (Option 4):**
    * Enter `4` and press Enter.
    * The program will display your account number, name, and current balance.

5.  **Exit (Option 5):**
    * Enter `5` and press Enter to close the banking system.

## Code Explanation

The code consists of the following key components:

* **`struct Account`:** Defines a structure to hold account information, including the account number (integer), account holder's name (string), and account balance (float).
* **`createAccount(struct Account* acc)`:** A function that takes a pointer to an `Account` structure. It prompts the user for their name and initial deposit, assigns a random account number, and initializes the account balance.
* **`deposit(struct Account* acc)`:** A function that takes a pointer to an `Account` structure. It prompts the user for the deposit amount and updates the account balance if the amount is positive.
* **`withdraw(struct Account* acc)`:** A function that takes a pointer to an `Account` structure. It prompts the user for the withdrawal amount and updates the account balance if sufficient funds are available and the amount is positive.
* **`checkBalance(struct Account* acc)`:** A function that takes a pointer to an `Account` structure and displays the account details (number, name, and balance).
* **`main()`:** The main function that initializes an `Account` structure, presents the menu to the user, and uses a `do-while` loop and a `switch` statement to handle user input and call the appropriate functions.

## Limitations

* **Single Account:** This system currently only supports a single account.
* **No Data Persistence:** Account data is not saved when the program exits. Each time the program runs, it starts with a fresh account.
* **Basic Error Handling:** The error handling is basic (e.g., checking for positive deposit/withdrawal amounts and sufficient funds).
* **No Security Features:** This is a very basic system and lacks any security features.

## Future Enhancements

* Implement support for multiple accounts.
* Add data persistence (e.g., using files) to save and load account information.
* Implement more robust error handling and input validation.
* Add features like transaction history.
* Incorporate basic security measures.
