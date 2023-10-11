# is January 1 more likely to fall on a Saturday or Sunday? Write a program to determine the number of times each occurs in a 400 year interval.
public class Exercise26 {
    public static void main(String args[]) {
      
      //Saturday counter
      int satc = 0;
      //Sunday counter
      int sunc = 0;
      //Number of days
      int days = 365;
      //Number of years
      int years = 400;
      // counter for thw while loop
      int i = 0;
      
      // create a while loop that will work for 400 years          
      while(i<=(years*days)){
         // days that are saturday
          if(i%6 == 0 && i%7 != 0){
              satc++;
          }
          // days that are sunday
          if(i%7 == 0){
              sunc++;
          }
         // add 365 so we skip a year
          i+=365;
      }

      // outputs
      System.out.println("Number of sundays: " + sunc);
      System.out.println("Number of saturdays: " + satc);
      System.out.println("So Sunday is more likely than Saturday");
    }
}
