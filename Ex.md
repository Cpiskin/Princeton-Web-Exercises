# Princeton-Web-Exercises
public class Ex {
    public static void main(String[] args) {
        if (args.length == 0) {
            System.out.println("Please provide a value for N as a command-line argument.");
            return;
        }

        int N = Integer.parseInt(args[0]);

        for (int i = -N; i <= N; i++) {
            for (int j = -N; j <= N; j++) {
                if (i == j || i == -j) {
                    System.out.print("* ");
                } else {
                    System.out.print(". ");
                }
            }
            System.out.println();
        }
    }
}
