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
