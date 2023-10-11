#  A gymnast's score is determined by a panel of 6 judges who each decide a score between 0.0 and 10.0. The final score is determined by 
# discarding the high and low scores, and averaging the remaining 4. Write a program GymnasticsScorer.
# java that takes 6 real command line inputs representing the 6 scores and prints their average, after throwing out the high and low scores.

import java.util.Scanner;
public class MyClass {
    public static void main(String args[]) {
      
      //Scanner object
      Scanner s = new Scanner(System.in);
      
      //Get all the input needed
      System.out.println("First score: ");
      double s1 = s.nextDouble();
      System.out.println("Second score: ");
      double s2 = s.nextDouble();
      System.out.println("Third score: ");
      double s3 = s.nextDouble();
      System.out.println("Fourth score: ");
      double s4 = s.nextDouble();
      System.out.println("Fifth score: ");
      double s5 = s.nextDouble();
      System.out.println("Sixth score: ");
      double s6 = s.nextDouble();
      
      // create an array to hold the inputs 
      double [] nums = { s1, s2, s3, s4, s5, s6 };
     // create a min and a max
      double min = nums[0];
      double max = nums[0];
      
      // finding the min and max in the for loop
      for(int i=1; i<6; i++){
          if (nums[i] < min) {
                min = nums[i]; // If we find a smaller number, update min
            } else if (nums[i] > max) {
                max = nums[i]; // If we find a larger number, update max
            }
      }
      
      // calculate the final score
      double finalscore = (s1+s2+s3+s4+s5+s6) - (min+max);
      
      // display the result
      System.out.println("The finals score is " + finalscore);
      
    }
}
