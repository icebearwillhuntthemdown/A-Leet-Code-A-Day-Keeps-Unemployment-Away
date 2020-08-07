# Merge Sorted Arrays

### Instruction
Merge and sort two int arrays. 

### Answer
```java
public class MergeSorted {
    public static void main(String[] args) {
        int[] arr = mergeSorted(new int[]{0, 1, 7}, new int[]{4, 8, 9});
        System.out.println(Arrays.toString(arr));   //[0, 1, 4, 7, 8, 9]
    }

    private static int[] mergeSorted(int[] arr1, int[] arr2){
        int[] mergedArray = new int[arr1.length + arr2.length];
        int j = 0, k = 0;

        if(arr1.length == 0){
            return arr2;
        }
        if(arr2.length == 0){
            return arr1;
        }

       for(int i = 0; i < mergedArray.length; i++){
           if(j != arr1.length && (k == arr2.length || arr1[j] < arr2[k])){
               mergedArray[i] = arr1[j];
               j++;
           }else{
               mergedArray[i] = arr2[k];
               k++;
           }
       }
        return mergedArray;
    }
}
```
