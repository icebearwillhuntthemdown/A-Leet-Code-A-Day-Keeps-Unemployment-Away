# [Array 101](https://leetcode.com/explore/featured/card/fun-with-arrays/521/introduction/)

배열을 아주 쉽고 적절하게 비유를 통해 설명하는 글을 발견했다. 안다고 생각하지 말고 기초부터 꼼꼼히 다시 공부하기! :fire: 

### What is an Array?
Array = storing DVDs in a box!  
> An Array is a collection of items. The items could be integers, strings, DVDs-anything really. The items are stored in neighboring contiguous memory locations, in definite size. Because they're stored together, checking through the entired collection of items is straightforward.

* a collection type
* only holds a sinlge type of data
* data is stored in contiguous memory location
* the definite size is decided on creation
* 0-indexed, meaning the highest index is arr.length-1

```java
public class arrayAndDVDs{
  DVD[] dvdCollection = new DVD[15];

  public class DVD{
    public String name;
    public int releaseYear;
    public String director;
    
    public DVD(String name, int releaseYear, String director){
      this.name = name;
      this.releaseYear = releaseYear;
      this.director = director;
  }
  
  public String toString(){
    System.out.println("Film : " + this.name + ", release Year : " + this.releaseYear + ", Director : " + this.director);
  }
}
```


### Default value for empty index
Java always initialises empty Array slot to **null** if it contains objects, or to default values if it contains primitive values.
  * int[] : 0
  * float[] : 0.0
  * bool[] : false

### Capacity vs Length
* Capacity : the maximum amount the array can hold e.g.) 
  * can be checked by array.length
* Length : the actual number of items that the array currently holds
  * need a user variable to keep track of the actual length
> When an Array is given as a parameter, without any additional information, you can safely assume that **length == capacity**, therefore we can use arr.length.

### Max Consecutive Ones
Given a binary array, find the maximum number of consecutive 1s in this array.

``` Java
class Solution {
    public int findMaxConsecutiveOnes(int[] nums) {
        
        int max = 0;
        int currCount = 0;
        
        for(int i=0; i<nums.length; i++){
            if(nums[i] == 1){
                currCount++;
                max = Math.max(max, currCount);
            }else{
                currCount = 0;
            }
        }
        
      return max;
        
    }
}

```

### Insertion
```Java
 int[] intArray = new int[6];
        int length = 0;

        for(int i = 0; i < 3; i++){
            intArray[length] = i;
            length++;
        }
```

1. At the end : simply append the new element using the length variable
```
intArray[length] = 10; //10 is added at index 3
length++;
``` 
1. At the beginning : move all the existing elements to the right and add the new element at index 0 
```
for(int i = 3; i >= 0; i--){
  intArray[i+1] = intArray[i]; //move the exsiting elements to the right
}

intArray[0] = 20; //and add a new element at index 0
```
1. In the middle : move all the elements from the specific index onwards to the right and add the new element at the index
```
//adding a new element at index 2
for(int i = 4; i >= 2; i--){
  intArray[i+1] = intArray[i]; //move some elements to the right to make a space
}

intArray[2] = 30; // add the new element in the space

```
