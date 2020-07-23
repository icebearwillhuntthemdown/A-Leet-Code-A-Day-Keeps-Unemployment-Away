# Array-Find the Minimum

### Instruction
-Write a method called readIntegers() with a parameter called count that represents how many integers the user needs to enter.
-The method needs to read from the console until all the numbers are entered, and then return an array containing the numbers entered.
-Write a method findMin() with the array as a parameter. The method needs to return the minimum value in the array.
-In the main() method read the count from the console and call the method readIntegers() with the count parameter. 
-Then call the findMin() method passing the array returned from the call to the readIntegers() method.
-Finally, print the minimum element in the array.

### Answer
```java
public class Minimum {
    private static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        System.out.println("Enter the count of numbers");
        int count = scanner.nextInt();

        int[] inputValues = readIntegers(count);
        int minimum = findMin(inputValues);
        System.out.println("The minimum number is " + minimum);
    }

    private static int[] readIntegers(int count){
        System.out.println("Enter " + count + " numbers");

        int[] arr = new int[count];
        for(int i = 0; i < count; i++){
            arr[i] = scanner.nextInt();
        }

        return arr;
    }

    private static int findMin(int[] arr){
        int min = arr[0];
        boolean repeat = true;

        for(int i = 0; i < arr.length; i++){
            if(arr[i] < min){
                min = arr[i];
            }
        }

        return min;
    }
}
```

### What I learnt
알고리즘에서 제일 중요한 건 코드도 아니고 사고력인 것 같다. 최소값 찾는 과정을 괜히 복잡하게 생각해서 아래처럼 더 복잡한 코드를 만들어냈는데 다시 생각해보니 그럴 이유가 전혀 없었음 🙃 바보같지만 이번 기회에 배웠으니까 됐다. 
```java
    while(repeat){
        repeat = false;
        for(int i = 0; i < arr.length; i++){
            if(arr[i] < min) {
                min = arr[i];
                repeat = true;
                break;
            }

        }
    }
```
