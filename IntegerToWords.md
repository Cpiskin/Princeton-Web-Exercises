# Princeton-Web-Exercise 21 Number to English
 //Write a program to read in a command line integer between -999,999,999 and 999,999,999 and print the English equivalent. Here is an exhaustive list of words that your program should //use: negative, zero, one, two, three, four, five, six, seven, eight, nine, ten, eleven, twelve, thirteen, fourteen, fifteen, sixteen, seventeen, eighteen, nineteen, twenty, thirty, //forty, fifty, sixty, seventy, eighty, ninety, hundred, thousand, million . Don't use hundred, when you can use thousand, e.g., use one thousand five hundred instead of fifteen hundred

public class IntegerToWords {
    private static final String[] units = {"zero", "one", "two", "three", "four", "five", "six", "seven", "eight", "nine"};
    private static final String[] teens = {"eleven", "twelve", "thirteen", "fourteen", "fifteen", "sixteen", "seventeen", "eighteen", "nineteen"};
    private static final String[] tens = {"", "", "twenty", "thirty", "forty", "fifty", "sixty", "seventy", "eighty", "ninety"};
    private static final String[] specialNames = {"", " thousand", " million"};

    // Method to convert numbers less than one thousand to words
    private static String convertLessThanOneThousand(int number) {
        String current;

        // Handling units place
        if (number % 100 < 10){
            current = units[number % 10];
            number /= 10;
        }
        // Handling teens (11 to 19)
        else if (number % 100 < 20){
            current = teens[number % 10 - 1];
            number /= 100;
        }
        // Handling tens place
        else {
            current = units[number % 10];
            number /= 10;
            current = tens[number % 10] + current;
            number /= 10;
        }
        
        // If there is a non-zero hundreds place, add it
        if (number == 0) return current;
        return units[number] + " hundred" + (current.isEmpty() ? "" : " and " + current);
    }

    // Main method to convert the entire number to words
    public static String convert(int number) {
        if (number == 0) { return "zero"; }
        String prefix = "";

        // Handle negative numbers
        if (number < 0) {
            number = -number;
            prefix = "negative";
        }

        String current = "";
        int place = 0;

        // Loop through the number, grouping digits in sets of three
        do {
            int n = number % 1000;
            if (n != 0){
                String s = convertLessThanOneThousand(n);
                current = s + specialNames[place] + current;
            }
            place++;
            number /= 1000;
        } while (number > 0);

        return (prefix + current).trim();
    }

    // Main method to test the conversion
    public static void main(String[] args) {
        int number = Integer.parseInt(args[0]);
        if (number < -999999999 || number > 999999999) {
            System.out.println("Please enter a number between -999999999 and 999999999.");
        } else {
            String result = convert(number);
            System.out.println(result);
        }
    }
}
