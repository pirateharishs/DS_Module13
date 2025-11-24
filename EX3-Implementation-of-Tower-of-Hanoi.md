# Ex3
## Write a program to count the number of digits in an integer.
## DATE: 14-11-2025
## AIM:
To write a Java program to count the number of digits in an integer.

## Algorithm
1. Start the program.
2. Declare an integer variable n and count = 0.
3. Read the integer number n from the user.
4. If n is 0, then the count of digits is 1.
5. Otherwise, Repeat the steps while n is not equal to 0. Divide n by 10. Increment count by 1.
6. Display the value of count.
7. Stop the program.

## Program:
```java
/*
Program to to count the number of digits in an integer
Developed by: HARISH S
Register Number: 212223230071
*/

import java.util.Scanner;

public class CountDigits {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num, count = 0;

        System.out.print("Enter an integer: ");
        num = sc.nextInt();

        if (num == 0) {
            count = 1;
        } else {
            while (num != 0) {
                num = num / 10;
                count++;
            }
        }

        System.out.println("Number of digits: " + count);
        sc.close();
    }
}
```

## Output:
<img width="543" height="180" alt="image" src="https://github.com/user-attachments/assets/2e4cd75f-cb9c-461e-a79c-e7dec98ff288" />



## Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.
