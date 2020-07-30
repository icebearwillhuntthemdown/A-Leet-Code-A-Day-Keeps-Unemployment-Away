# Reverse the Array - Int Array

### Instruction
-Write a method called reverse() with an int array as a parameter.
-The method should not return any value. In other words, the method is allowed to modify the array parameter.
-In main() test the reverse() method and print the array both reversed and non-reversed.
-To reverse the array, you have to swap the elements, so that the first element is swapped with the last element and so on.
-For example, if the array is {1, 2, 3, 4, 5}, then the reversed array is {5, 4, 3, 2, 1}.


### Answer
```java
public class ReverseArray {
    public static void main(String[] args) {
        int[] arr = {1,2,3,4,5,6,7,8,9};
        System.out.println("The original is " + Arrays.toString(arr)); 
        //Result : The original is [1, 2, 3, 4, 5, 6, 7, 8, 9]
        reverse(arr);
        //Result : The reversed is [9, 8, 7, 6, 5, 4, 3, 2, 1]
    }

    private static void reverse(int[] arr){
        int j = arr.length-1;

        for(int i = 0; i < arr.length / 2; i++){
            int temp = arr[i];
            arr[i] = arr[j];
            arr[j] = temp;
            j--;
        }

        System.out.println("The reversed is " + Arrays.toString(arr));
    }
}
```

# Reverse the Array - String Array

### Instruction
Write a method that takes a string and prints it backwards.

### Answer
```java
public class Main {
    public static void main(String[] args) {
        reverse("Hi My name is Hana!");
    }

    public static void reverse(String str){
        int length = str.length();
        char[] strArr = new char[length];
        char[] newArr = new char[length];
        String reversed = "";

        for(int i = 0; i < length; i++){
            strArr[i] = str.charAt(i);
        }

        for(int i = 0; i < length; i++){
            newArr[i] = strArr[(length-1) - i];
            reversed += newArr[i];
        }

        System.out.println(Arrays.toString(strArr));    // [H, i,  , M, y,  , n, a, m, e,  , i, s,  , H, a, n, a, !]
        System.out.println(Arrays.toString(newArr));    // [!, a, n, a, H,  , s, i,  , e, m, a, n,  , y, M,  , i, H]
        System.out.println(reversed);   // !anaH si eman yM iH
    }
}
```
[GeeksforGeeks](https://www.geeksforgeeks.org/reverse-a-string-in-java/) 풀이 참고해서 다시 



