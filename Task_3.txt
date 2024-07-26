/*Task 2 : ATM interface
 * 
1.Create a class to represent the ATM machine.
2. Design the user interface for the ATM, including options such as withdrawing, depositing, and
checking the balance.
3. Implement methods for each option, such as withdraw(amount), deposit(amount), and
checkBalance().
4. Create a class to represent the user's bank account, which stores the account balance.
5. Connect the ATM class with the user's bank account class to access and modify the account
balance.
6. Validate user input to ensure it is within acceptable limits (e.g., sufficient balance for withdrawals).
7. Display appropriate messages to the user based on their chosen options and the success or failure
of their transaction
*/

package Task3;
import java.util.Scanner;

public class AtmEx {

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int balance = 10000;
        int deposit, withdraw, choice;

        do {
            System.out.println("Welcome to ATM Machine ");
            System.out.println("1.Deposit:");
            System.out.println("2.Withdraw:");
            System.out.println("3.Balance inquiry:");
            System.out.println("4.Exit");

            System.out.println("Enter the choice :");
            choice = sc.nextInt();

            switch (choice) {

                case 1:
                    System.out.println("Enter the amount you want to deposit:");
                    deposit = sc.nextInt();
                    balance = balance + deposit;
                    System.out.println("Your updated balance is :" + balance);
                    System.out.println();
                    break;

                case 2:
                    System.out.println("Enter the amount to withdraw :");
                    withdraw = sc.nextInt();
                    if (balance >= withdraw) {
                        balance = balance - withdraw;
                        System.out.println("Your updated balance is :" + balance);
                    } else {
                        System.out.println("Insufficient funds...!!");
                    }
                    break;

                case 3:
                    System.out.println("Your account balance is: " + balance);
                    System.out.println();
                    break;

                case 4:
                    System.out.println("Exiting...");
                    break;
            }

            if (choice != 4) {
                System.out.println("Enter 1 to continue :");
                choice = sc.nextInt();
            }

        } while (choice != 4);

        System.out.println("Thank You..!!!");
        sc.close();
    }
}
