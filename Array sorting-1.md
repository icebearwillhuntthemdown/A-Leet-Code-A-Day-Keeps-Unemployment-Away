# Array sorting-1
### Instructions
// Create a program using arrays that sorts a list of integers in descending order.  
// Descending order is highest value to lowest.  
// In other words if the array had the values in it 106, 26, 81, 5, 15 your program should  
// ultimately have an array with 106,81,26, 15, 5 in it.  
// Set up the program so that the numbers to sort are read in from the keyboard.  
// Implement the following methods - getIntegers, printArray, and sortIntegers  
// getIntegers returns an array of entered integers from keyboard  
// printArray prints out the contents of the array  
// and sortIntegers should sort the array and return a new array containing the sorted numbers  
// you will have to figure out how to copy the array elements from the passed array into a new  
// array and sort them and return the new sorted array.  

### Answer
```java
import java.util.Arrays;
import java.util.Scanner;

public class ArrayChallenge {
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {

        int[] arr = getIntegers(5);
        printArray(arr);
        sortIntegers(arr);
    }

    // returns an array of entered integers from keyboard
    private static int[] getIntegers(int num){
        int[] nums = new int[num];
        System.out.println("Enter 5 numbers");
        for(int i = 0; i < num; i++){
            nums[i] = scanner.nextInt();
        }
        return nums;
    }

    //prints out the contents of the array
    private static void printArray(int[] arr){
        for(int i = 0; i < arr.length; i++){
            System.out.println("Element " + (i+1) + " is " + arr[i]);
        }
        System.out.println("-----printArray finished-----");
    }

    //sort the array and return a new array containing the sorted numbers
    private static int[] sortIntegers(int[] arr){
        int[] sortedArr = new int[arr.length];
        int temp = 0;

        for(int i = 0; i < arr.length; i++){
            for(int j = i+1; j < arr.length; j++){
                if(arr[i] < arr[j]){
                    temp = arr[i];
                    arr[i] = arr[j];
                    arr[j] = temp;

                }

            }
        }
        //copying arr into a new array
        for(int i = 0; i < arr.length; i++){
            sortedArr[i] = arr[i];
        }
        sortedArr = Arrays.copyOf(arr, arr.length);
        System.out.println(Arrays.toString(sortedArr));

        return sortedArr;

    }
}
```

### What I learnt
* Arrays.copyOf(arr, newLength)로 for loop 쓰지 않고 한 줄로 배열을 복사할 수 있다.
* Nest for loop 대신 while, boolean을 쓰는 방법도 있다
```java
public static int[] sortArray(int[] arr){
    //1. 배열 복사를 먼저 수행
    int[] sortedArr = Arrays.copyOf(arr, arr.length);
    boolean flag = true;
    int temp;

    //2. 복사한 배열을 정렬
    while(flag){
        flag = false;
        for(int = 0; i < sortedArr.length-1; i++){
            if(sortedArr[i] < sortedArr[i+1]){
                temp = sortedArr[i];
                sortedArr[i] = sortedArr[i+1];
                sortedArr[i+1] = temp;
                flag = true;
            }
        }
    }
    return sortedArr;
}
```
