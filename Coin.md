# Princeton-Web-Exercises
import java.util.Scanner;
public class Coins {
    public static void main(String args[]) {

      // Write a program that reads in a command line integer N (number of pennies) and prints the best way (fewest number of coins) to make change using US coins     
     //  (quarters, dimes, nickels, and pennies only).
        
        // Scanner object
        Scanner s = new Scanner(System.in);
        
        // Write how much each coins cost in cents
        int penny = 1;
        int nickel = 5;
        int dime = 10;
        int quarter = 25;
        // Counters for the coins
        int pennyc = 0;
        int nickelc = 0;
        int dimec = 0;
        int quarterc = 0;
        
        // Get the number of cents
        System.out.println("Enter the amount of cents: ");
        int n = s.nextInt();
        
        // Create a while loop that will run until n=0
        while(n>0){
            while(n>=25){
                n-=25;
                quarterc++;
            }
            while(n>=10){
                n-=10;
                dimec++;
            }
            while(n>=5){
                n-=5;
                nickelc++;
            }
            while(n>=1){
                n-=1;
                pennyc++;
            }
        }
        
        //Display the results
        System.out.println("Number of quarters: " + quarterc);
        System.out.println("Number of dimes: " + dimec);
        System.out.println("Number of nickels: " + nickelc);
        System.out.println("Number of pennys: "+ pennyc);
        
    }
}
