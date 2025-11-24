# EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
## DATE: 13.08.2025
## AIM:
To write a JAVA program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.

## Algorithm:
```
1. Start
2.Read the number of elements (e.g., number of heartbeat readings).
3.Store all readings in an array.
4.Call a recursive function findMin(arr, index)
If index == arr.length - 1, return arr[index]
Else return min(arr[index], findMin(arr, index + 1))
5.Print the minimum value returned by the recursive function.
6.End 
```
## Program:
```
/*
Program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
Developed by: HARISH S
Register Number: 212223230071
*/
import java.util.*;

public class Main {
    static int getMin(int[] arr, int i, int n) {
        if (i == n - 1) {
            return arr[i];
        }

    
        int minRest = getMin(arr, i + 1, n);
       
        return Math.min(arr[i], minRest);
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }
        System.out.println(getMin(arr, 0, n));
    }
}
```

## Output:

<img width="649" height="254" alt="image" src="https://github.com/user-attachments/assets/e2c774aa-cc92-40f6-acb8-778042dd4078" />


## Result:
Thus the JAVA program to find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully

# Ex2 Count how many times a number appears in an array recursively.
## DATE:15-08-2025
## AIM:
To write a Java program to Count how many times a number appears in an array recursively.

## Algorithm
1. Read the value of n, input n elements into array arr, and read the number key whose occurrences must be counted.
2. Call the recursive function countOccurrences(arr, n, 0, key) starting from index 0.
3. Inside the recursive function, check if the current index equals n;if yes, return 0 because the entire array has been checked.
4. If arr[index] equals key, return 1 + countOccurrences(arr, n, index + 1, key);otherwise return countOccurrences(arr, n, index + 1, key).
5. Return the final count to the main program and print how many times key appears in the array.   

## Program:
```
/*
Program Count how many times a number appears in an array recursively.
Developed by: HARISH S
Register Number: 212223230071
import java.util.Scanner;

public class CountOccurrencesRecursive {
    
    public static int countOccurrences(int[] arr, int n, int index, int key) {
        if (index == n) {
            return 0; 
        }
        if (arr[index] == key) {
            return 1 + countOccurrences(arr, n, index + 1, key);
        } else {
            return countOccurrences(arr, n, index + 1, key);
        }
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

    
        int n = sc.nextInt();

        int[] arr = new int[n];
        for (int i = 0; i < n; i++) {
            arr[i] = sc.nextInt();
        }

        int key = sc.nextInt();

        int count = countOccurrences(arr, n, 0, key);

        System.out.println("The number " + key + " appears " + count + " time(s) in the array.");
    }
}


*/
```

## Output:

<img width="679" height="380" alt="image" src="https://github.com/user-attachments/assets/f8c606ed-86b7-4c72-9b48-ae94ce15babb" />


## Result:
Thus, the Java program to Count how many times a number appears in an array recursively is implemented successfully.

# EX3 Write a program to count the number of digits in an integer.
## DATE:18-08-2025
## AIM:
To write a C program to implement Tower of Hanoi

## Algorithm
1. Read the input number Take an integer num from the user.
2. Convert the number to a non-negative value Use Math.abs(num) and store it in n to handle negative numbers.
3. Check if the number is zero If n == 0, set digit count to 1 (since zero has one digit).
4. Count digits for non-zero numbers Repeatedly divide n by 10 and increment the counter until n becomes 0.
5. Display the digit count Output the total number of digits.
 

## Program:
```
/*
Program to to count the number of digits in an integer
Developed by: HARISH S
Register Number: 212223230071
import java.util.Scanner;

public class CountDigits {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int num = sc.nextInt();

        int count = 0;
        int n = Math.abs(num); 

        if (n == 0) {
            count = 1; 
        } else {
            while (n > 0) {
                n /= 10; 
                count++;
            }
        }

        System.out.println("Number of digits: " + count);
    }
}
*/

```

## Output:

<img width="733" height="328" alt="image" src="https://github.com/user-attachments/assets/e98aa441-ca80-47c7-9d17-30a8f18ae029" />


## Result:
Thus, the Java program to to count the number of digits in an integer is implemented successfully.

# Ex4 You are given a Java program that performs matrix addition. If Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension, what will be the nature (even/odd/mixed) of the resulting matrix?
## DATE: 19/08/25
## AIM:
To write a java function to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix.

## Algorithm
```
1. Start the program.
2.Read the number of rows rows and columns cols.
3.Create three 2D arrays.
4.Input elements for Matrix A.
5.Input elements for Matrix B.
6.Perform matrix addition
7.After each row is printed, move to the next line.
8. End the program.  
```
## Program:
```
/*
Program to ind the nature of resultant matrrix.
Developed by: HARISH S
Register Number: 212223230071
*/

import java.util.Scanner;

public class OddEvenMatrixAddition {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int rows = sc.nextInt();
        int cols = sc.nextInt();

        int[][] A = new int[rows][cols];
        int[][] B = new int[rows][cols];
        int[][] result = new int[rows][cols];

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                A[i][j] = sc.nextInt();
            }
        }

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                B[i][j] = sc.nextInt();
            }
        }

        for (int i = 0; i < rows; i++) {
            for (int j = 0; j < cols; j++) {
                result[i][j] = A[i][j] + B[i][j];
                System.out.print(result[i][j] + " ");
            }
            System.out.println();
        }
        sc.close();
    }
}


```

## Output:

<img width="491" height="756" alt="image" src="https://github.com/user-attachments/assets/f3559ebf-4c04-4c4d-899b-bd507f9ad631" />


## Result:
Thus, the java program to evaluate weather the given Matrix A has all odd numbers and Matrix B has all even numbers of the same dimension and find the nature of resultant matrrix is implemented successfully.

# Ex5 Count Inversions in an Array
## DATE: 20/08/25
## AIM:
To write a Java program  to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
```
1. Start the program.
2.Declare an array arr[] and a variable count = 0 to store the number of inversions.
3.Read the array elements from the user.
4.For each pair of elements (arr[i], arr[j]), check if arr[i] > arr[j] and i < j.
5.If the above condition is true, increment the inversion count.
6.Continue until all pairs are checked.
7.Display the total number of inversions found in the array and stop the program.
```
## Program:
```
/*
Program toto Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j
Developed by: HARISH S
Register Number: 212223230071
*/

import java.util.Scanner;

public class CountInversions {

    // Function to sort the array and return inversion count
    public static int mergeSortAndCount(int[] arr, int left, int right) {
        int count = 0;
        if (left < right) {
            int mid = (left + right) / 2;

            // Count inversions in left subarray
            count += mergeSortAndCount(arr, left, mid);

            // Count inversions in right subarray
            count += mergeSortAndCount(arr, mid + 1, right);

            // Count inversions while merging
            count += mergeAndCount(arr, left, mid, right);
        }
        return count;
    }

    // Merge two sorted subarrays and count inversions
    private static int mergeAndCount(int[] arr, int left, int mid, int right) {
        int[] leftArr = new int[mid - left + 1];
        int[] rightArr = new int[right - mid];

        for (int i = 0; i < leftArr.length; i++)
            leftArr[i] = arr[left + i];
        for (int i = 0; i < rightArr.length; i++)
            rightArr[i] = arr[mid + 1 + i];

        int i = 0, j = 0, k = left, swaps = 0;

        while (i < leftArr.length && j < rightArr.length) {
            if (leftArr[i] <= rightArr[j]) {
                arr[k++] = leftArr[i++];
            } else {
                arr[k++] = rightArr[j++];
                swaps += (leftArr.length - i); // Count inversions
            }
        }

        while (i < leftArr.length) arr[k++] = leftArr[i++];
        while (j < rightArr.length) arr[k++] = rightArr[j++];

        return swaps;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt();
        int[] arr = new int[n];
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();

        int result = mergeSortAndCount(arr, 0, n - 1);
        System.out.println(result);
    }
}

```

## Output:

<img width="541" height="466" alt="image" src="https://github.com/user-attachments/assets/a7263658-8359-4ab8-a712-20b5c373b90f" />


## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.



