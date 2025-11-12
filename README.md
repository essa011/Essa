import java.util.Scanner;

public class CreditLimitCalculator {
   public static void main(String[] args) {
       Scanner input = new Scanner(System.in);

       // Prompt the user for the first account number
       System.out.print("Enter account number (or a negative number to quit): ");
       int accountNumber = input.nextInt();

       // Continue until user enters a negative account number
       while (accountNumber >= 0) {
           // Prompt for beginning balance
           System.out.print("Enter beginning balance: ");
           double beginningBalance = input.nextDouble();

           // Prompt for total charges this month
           System.out.print("Enter total charges this month: ");
           double charges = input.nextDouble();

           // Prompt for total credits this month
           System.out.print("Enter total credits this month: ");
           double credits = input.nextDouble();

           // Prompt for allowed credit limit
           System.out.print("Enter allowed credit limit: ");
           double creditLimit = input.nextDouble();

           // Calculate new balance
           double newBalance = beginningBalance + charges - credits;

           // Display the new balance
           System.out.printf("New balance is %.2f%n", newBalance);

           // Check if credit limit is exceeded
           if (newBalance > creditLimit) {
               System.out.println("Credit limit exceeded.");
           }

           System.out.println(); // blank line for readability

           // Prompt the user for the next account number
           System.out.print("Enter account number (or a negative number to quit): ");
           accountNumber = input.nextInt();
       }

       System.out.println("Program terminated.");
       input.close();
   }
}