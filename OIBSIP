import java.util.Scanner;
import java.util.ArrayList;

public class ATM {
    private static Scanner scanner = new Scanner(System.in);
    private static int userId = 12345; // Example user ID
    private static int userPin = 6789; // Example user PIN
    private static double balance = 1000; // Example initial balance
    private static ArrayList<String> transactionHistory = new ArrayList<>();

    public static void main(String[] args) {
        System.out.println("Welcome to the ATM!");
        if (login()) {
            displayMenu();
        } else {
            System.out.println("Incorrect ID or PIN. Exiting...");
        }
    }

    private static boolean login() {
        System.out.print("Enter User ID: ");
        int enteredId = scanner.nextInt();
        System.out.print("Enter PIN: ");
        int enteredPin = scanner.nextInt();

        if (enteredId == userId && enteredPin == userPin) {
            System.out.println("Login successful!");
            return true;
        } else {
            return false;
        }
    }

    private static void displayMenu() {
        boolean exit = false;
        while (!exit) {
            System.out.println("\nChoose an option:");
            System.out.println("1. Transactions History");
            System.out.println("2. Withdraw");
            System.out.println("3. Deposit");
            System.out.println("4. Transfer");
            System.out.println("5. Quit");

            int choice = scanner.nextInt();
            switch (choice) {
                case 1:
                    printTransactionHistory();
                    break;
                case 2:
                    withdraw();
                    break;
                case 3:
                    deposit();
                    break;
                case 4:
                    transfer();
                    break;
                case 5:
                    exit = true;
                    System.out.println("Thank you for using the ATM. Goodbye!");
                    break;
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void printTransactionHistory() {
        if (transactionHistory.isEmpty()) {
            System.out.println("No transaction history available.");
        } else {
            for (String transaction : transactionHistory) {
                System.out.println(transaction);
            }
        }
    }

    private static void withdraw() {
        System.out.print("Enter amount to withdraw: ");
        double amount = scanner.nextDouble();
        if (amount > balance) {
            System.out.println("Insufficient funds!");
        } else {
            balance -= amount;
            transactionHistory.add("Withdrawal: -" + amount);
            System.out.println("Withdrawal successful. Your new balance is: " + balance);
        }
    }

    private static void deposit() {
        System.out.print("Enter amount to deposit: ");
        double amount = scanner.nextDouble();
        balance += amount;
        transactionHistory.add("Deposit: +" + amount);
        System.out.println("Deposit successful. Your new balance is: " + balance);
    }

    private static void transfer() {
        System.out.print("Enter recipient's account number: ");
        String recipientAccount = scanner.next();
        System.out.print("Enter amount to transfer: ");
        double amount = scanner.nextDouble();
        if (amount > balance) {
            System.out.println("Insufficient funds!");
        } else {
            balance -= amount;
            transactionHistory.add("Transfer to " + recipientAccount + ": -" + amount);
            System.out.println("Transfer complete. Your new balance is: " + balance);
        }
    }
}



