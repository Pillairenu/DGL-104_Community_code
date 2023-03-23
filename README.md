# DGL-104_Community_code
DGL 104 App Dev Foundations Winter 2023 

This is my commuinty code project repository.
## Community Code project

Chosen Community : [CODERANCH](https://coderanch.com/)

I like to contribute to the community by resolving unsolved queries and planning to answer the question for me and the instructor.

**Issue of Interest:1**

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
  **Code Explanation:**

  In this program, I first prompt the user to enter an account number using the Scanner class. Then I initialized a boolean variable called isValid to true, assuming that the account number is valid. Then I applied the conditions described one by one to check whether the account number was valid or not. First, I check the account number, which must have 16 characters. If it doesn't, isValid is set to false. Next, I checked that the first two characters of the account number are capital letters, with the first letter being lower than the second letter in ASCII value. If they're not, isValid is set to false. Then I checked that the third and fourth characters of the account number are prime numbers. If they're not, isValid is set to false. Then for the remaining 12 digits, calculate the sum of the digits in even positions of the account number, first doubling every second digit from right to left. If doubling a digit results in a two-digit number, add up the two digits to get a single-digit number. The sum of these digits is stored in a variable called sumEven. Then it calculates the sum of the digits in the odd positions of the account number and stores the sum in a variable called sumOdd. Finally, the program checks whether the sum of sumEven and sumOdd is divisible by 10. If the resulting sum is not divisible by 10, isValid is set to false.If all of the checks pass, the program displays a message indicating that the account number is valid. If any of the checks fail, the program displays a message indicating that the account number is invalid.





**Issue of Interest:2**

[Write a Java program that reads from the user a real number that
represents the length of the side opposite the 30 degree angle in 30-60-90 triangle.
The program then calculates and prints the area of this triangle
(rounded to 2 decimal places) according to the following formula:
area = 1/2 (√3 𝑥^2)](https://coderanch.com/t/754759/java/Java-Program-Practice)

**My Contribution:**

```
import java.util.Scanner;

public class Area 
{
    public static void main(String[] args) 
    {
        Scanner input = new Scanner(System.in);
        System.out.print("Enter the length of the opposite side ");/*length of the shorter side*/
        double oppositeSide = input.nextDouble();
        double area = 0.5 * Math.sqrt(3) * Math.pow(oppositeSide, 2);
        System.out.printf("The area of the triangle is %.2f\n", area);
    }
}


```
**Explanation:**

In a 30-60-90 triangle, the sides are in the ratio of 1:sqrt(3):2, where the hypotenuse is twice the length of the shorter side.Let assume the length of the side opposite to 30 is "x".Then, the length of the side opposite to the 60-degree angle is sqrt(3)x, and the length of the hypotenuse (opposite to the 90-degree angle) is 2x.
The area of the triangle is calculated using the formula:

Area = (base x height)/2

For 30-60-90 triangle the area is calculated using, 

Area =  (1/2)*(sqrt(3)x)*2x =.5*sqrt(3)*x^2

**Code Explanation:**

First, I read input from the user.I created a Scanner object named "input" to read user input.Then I prompt the user to enter the length of the side opposite the 30 degree angle in the 30-60-90 triangle and read the input as a double using the nextDouble() method.Then I calculate the area of the triangle using the given formula, which involves taking the square root of 3, multiplying it by the square of the opposite side length, and dividing by 2.Then I used the printf() method to print the calculated area to two decimal places. The %.2f format specifier is to print a floating-point number with two decimal places.


**Reflection on Community code**

I contributed to the community I choose by resolving unsolved queries. Almost all the questions in my community are answered instantly since the community is very active. I had only a very few questions to answer. I have resolved those questions, which were challenging for me since I have no strong knowledge in Java programming language. I first figured out the logic and then tried to write the code. Finally, I managed to resolve the questions. However, joining this community enhanced my knowledge of the Java programming language by trying to understand different issues from the conversations in the community.