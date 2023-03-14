# DGL-104_Community_code
DGL 104 App Dev Foundations Winter 2023 
## Community Code project

Chosen Community : [CODERANCH](https://coderanch.com/)

**Issue of Interest:**

  [Write a Java program that prompts the user to enter an account number. Display whether the number is valid or invalid according to the given situations.](https://coderanch.com/t/756159/java/Java-simple)

  **My Contribution:**

  ```
import java.util.Scanner;

public class ValidateAccountNumber
{
    public static void main(String[] args) 
    {

        Scanner scanner = new Scanner(System.in);
        System.out.print("Enter an account number: ");
        String accountNumber = scanner.nextLine();

        boolean isValid = true;

        // Check if the account number has 16 characters

        if (accountNumber.length() != 16)
        {
            isValid = false;
        }

        //Check characters are capital letters and in the correct order

        char firstChar = accountNumber.charAt(0);
        char secondChar = accountNumber.charAt(1);
        if (!Character.isUpperCase(firstChar) || !Character.isUpperCase(secondChar) || firstChar >= secondChar) 
        {
            isValid = false;
        }

        //Check digits are prime numbers

        int prime1 = Character.getNumericValue(accountNumber.charAt(2));
        int prime2 = Character.getNumericValue(accountNumber.charAt(3));
        if (!isPrime(prime1) || !isPrime(prime2))
        {
            isValid = false;
        }

        // The sum of the digits in even places, doubled and reduced to a single digit

        int sumEven = 0;
        for (int i = 14; i >= 4; i -= 2) 
        {
            int digit = Character.getNumericValue(accountNumber.charAt(i));
            int doubledDigit = digit * 2;
            sumEven += (doubledDigit % 10) + (doubledDigit / 10);
        }

        // The sum of the digits in odd places

        int sumOdd = 0;
        for (int i = 15; i >= 4; i -= 2)
        {
            int digit = Character.getNumericValue(accountNumber.charAt(i));
            sumOdd += digit;
        }

        // Check if the sum of even and odd digits is divisible by 10

        if ((sumEven + sumOdd) % 10 != 0)
        {
            isValid = false;
        }

        // Display the result

        if (isValid)
        {
            System.out.println("The account number " + accountNumber + " is valid.");
        } 
        else 
        {
            System.out.println("The account number " + accountNumber + " is invalid.");
        }
    }

    // Check if a number is prime or not

    private static boolean isPrime(int n)
    {
        if (n <= 1)
        {
            return false;
        }
        for (int i = 2; i <= Math.sqrt(n); i++)
        {
            if (n % i == 0)
            {
                return false;
            }
        }
        return true;
    }
}

  ```
  **Explanation:**

  In this program, I first prompt the user to enter an account number using the Scanner class. Then I initialized a boolean variable called isValid to true, assuming that the account number is valid. Then I applied the conditions described one by one to check whether the account number was valid or not. First, I check the account number, which must have 16 characters. If it doesn't, isValid is set to false. Next, I checked that the first two characters of the account number are capital letters, with the first letter being lower than the second letter in ASCII value. If they're not, isValid is set to false. Then I checked that the third and fourth characters of the account number are prime numbers. If they're not, isValid is set to false. Then for the remaining 12 digits, calculate the sum of the digits in even positions of the account number, first doubling every second digit from right to left. If doubling a digit results in a two-digit number, add up the two digits to get a single-digit number. The sum of these digits is stored in a variable called sumEven. Then it calculates the sum of the digits in the odd positions of the account number and stores the sum in a variable called sumOdd. Finally, the program checks whether the sum of sumEven and sumOdd is divisible by 10. If the resulting sum is not divisible by 10, isValid is set to false.If all of the checks pass, the program displays a message indicating that the account number is valid. If any of the checks fail, the program displays a message indicating that the account number is invalid.