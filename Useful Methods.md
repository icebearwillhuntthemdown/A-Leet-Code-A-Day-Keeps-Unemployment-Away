# Useful Methods 

### Math
* Math.max(int a, int b) : return the maximum value between the two operands.

### Arrays
* Arrays.toString(array) : printing the elements of an array
* Arrays.copyOf(array, newLength) : copying an array into another
```java
int[] arr = {1,2,3,4,5};
int[] newArr = new int[arr.length];
for(int i = 0; i < arr.length; i++){
  newArr[i] = arr[i];
}
```
