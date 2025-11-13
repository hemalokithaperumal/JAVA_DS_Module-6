# EX 1 You’re creating a health monitoring device which stores several sensor readings in an array. To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.
## DATE:13.11.2025
## AIM:
To write a JAVA program To determine the minimum value (e.g., lowest heartbeat), implement a recursive method.

## Algorithm
1. Start the program.  
2. Read the number of elements and store them in an array.  
3. Define a recursive function `findMin()` that compares elements to find the minimum.  
4. Base condition: If the array has one element, return that element.  
5. Recursive step: Compare the last element with the minimum of the rest of the array and return the smaller one.  
6. Display the minimum value.  
7. Stop the program.
   
## Program:
```
/**
 * Program: Determine the minimum value (e.g., lowest heartbeat) using recursion
 * Developed by: Hema Lokitha P
 * Register Number: 212223110014
 */
import java.util.Scanner;

public class MinValueRecursive {
    static int findMin(int arr[], int n) {
        if (n == 1)
            return arr[0];
        return Math.min(arr[n - 1], findMin(arr, n - 1));
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Enter number of readings: ");
        int n = sc.nextInt();
        int arr[] = new int[n];
        System.out.println("Enter the readings:");
        for (int i = 0; i < n; i++)
            arr[i] = sc.nextInt();
        System.out.println("Minimum value (lowest heartbeat): " + findMin(arr, n));
        sc.close();
    }
}
```
## Output:

<img width="538" height="378" alt="image" src="https://github.com/user-attachments/assets/34d1835a-a903-4204-9662-ccde8f7ec68a" />


## Result:
Thus the JAVA prograM ti find the minimum value (e.g., lowest heartbeat), implement a recursive method has implemented successfully
