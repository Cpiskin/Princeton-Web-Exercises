import java.util.Scanner;
public class Triangle {
    public static void main(String args[]) {
      
        // Scanner object
        Scanner s = new Scanner(System.in);
        
        // Get input
        System.out.println("Enter the number of lines: ");
        int n = s.nextInt();

        for(int i=0; i<n; i++){
            // add 1 more space each time
            for(int c=0; c<i; c++){
                System.out.print(" ");
            }
           // add star at the beginning
            for(int b=n; i<b; b--){
                System.out.print("*");
            }
            // Add a new line
            System.out.println();
        }
    }
}
