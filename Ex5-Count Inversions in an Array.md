# Ex5 Count Inversions in an Array
## DATE:13.11.2025

## AIM:
To write a Java program  to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < j

## Algorithm
1. Start the program.  
2. Read the dimensions of the matrices.  
3. Read elements of Matrix A (odd numbers) and Matrix B (even numbers).  
4. Perform matrix addition and store the result in Matrix C.  
5. Check whether all elements in Matrix C are even, odd, or mixed.  
6. Display the resulting matrix and its nature.  
7. Stop the program.

## Program:
```
/*
Program to find the nature of the resultant matrix.
Developed by: Hema Lokitha P
RegisterNumber: 212223110014
*/
import java.util.Scanner;

public class CountInversions {
    static long mergeCount(int[] arr, int[] temp, int left, int mid, int right) {
        int i = left, j = mid + 1, k = left;
        long invCount = 0;
        while (i <= mid && j <= right) {
            if (arr[i] <= arr[j]) {
                temp[k++] = arr[i++];
            } else {
                temp[k++] = arr[j++];
                invCount += (mid - i + 1);
            }
        }
        while (i <= mid) temp[k++] = arr[i++];
        while (j <= right) temp[k++] = arr[j++];
        for (i = left; i <= right; i++) arr[i] = temp[i];
        return invCount;
    }

    static long mergeSortCount(int[] arr, int[] temp, int left, int right) {
        long invCount = 0;
        if (left < right) {
            int mid = left + (right - left) / 2;
            invCount += mergeSortCount(arr, temp, left, mid);
            invCount += mergeSortCount(arr, temp, mid + 1, right);
            invCount += mergeCount(arr, temp, left, mid, right);
        }
        return invCount;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of elements: ");
        int n = sc.nextInt();
        int[] arr = new int[n];
        System.out.println("Enter the elements:");
        for (int i = 0; i < n; i++) arr[i] = sc.nextInt();
        int[] temp = new int[n];
        long inversions = mergeSortCount(arr, temp, 0, n - 1);
        System.out.println("Number of inversions: " + inversions);
        sc.close();
    }
}
```

## Output:

<img width="307" height="205" alt="image" src="https://github.com/user-attachments/assets/77bc1a29-984e-4ffb-b163-0aa13967c1e5" />


## Result:
Thus the Java program to to Count the number of inversions in an array where inversion is defined as: arr[i] > arr[j] and i < jis implemented successfully.
