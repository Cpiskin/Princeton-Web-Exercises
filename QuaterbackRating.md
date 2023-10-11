#  To compare NFL quarterbacks, the NFL devised a the quarterback rating formula based on the quarterbacks number of completed passes (A), pass attempts (B),
# passing yards (C), touchdown passes (D), and interception (E) as follows:
# Completion ratio: W = 250/3 * ((A / B) - 0.3).
# Yards per pass: X = 25/6 * ((C / B) - 3).
# Touchdown ratio: Y = 1000/3 * (D / B)
# Interception ratio: Z = 1250/3 * (0.095 - (E / B))
# The quarterback rating is computed by summing up the above four quantities, but rounding up or down each value so that it is at least 0 and and at most 475/12. 
# Write a program QuarterbackRating.java that takes five command line inputs A, B, C, D, and E, and prints the quarterback rating. Use your program to compute 
# Steve Young's 1994 record-setting season (112.8) in which he completed 324 of 461 passes for 3,969 yards, and threw 35 touchdowns and 10 interceptions.
# As of 2014, the all-time single-season record is 122.5 by Aaron Rodgers in 2011.

import java.util.Scanner;
public class MyClass {
    public static void main(String args[]) {
      
        //Scanner object
        Scanner s = new Scanner(System.in);
      
        // Get all input neccessary
        System.out.println("Enter the number of completed passes (A): ");      
        int a = s.nextInt();
        System.out.println("Enter the number of pass attemps (B): ");      
        int b = s.nextInt();
        System.out.println("Enter the number of passing yards (C): ");      
        int c = s.nextInt();
        System.out.println("Enter the number of touchdown passes (D): ");      
        int d = s.nextInt();
        System.out.println("Enter the number of interceptions (E): ");      
        int e = s.nextInt();
        
        // calculate the 4 quantities
        double w = 250/3 * ((a/b) - 0.3);
        double x = 25/6 * ((c/b) - 3)
        double y = 1000/3 * (d/b);
        double z = 1250/3 * (0.095 - (e/b));
        
        // calculate rating
        double rating = w+x+y+z;
        
        // ensure the rating is at least 0 and at most 475/12
        rating = Math.max(0, Math.min(475.0/12, rating));

        // print the quarterback rating
        System.out.println("Quarterback Rating: " + rating);
        
    }
}
