# [Array 101](https://leetcode.com/explore/featured/card/fun-with-arrays/521/introduction/)

배열을 아주 쉽고 적절하게 비유를 통해 설명하는 글을 발견했다.

Array = storing DVDs in a box!  

> An Array is a collection of items. The items could be integers, strings, DVDs-anything really. The items are stored in neighboring contiguous memory locations, in definite size. Because they're stored together, checking through the entired collection of items is straightforward.

>

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
Java always initialises empty Array slot to null if it contains objects, or to default values if it contains primitive values.
  * int[] : 0
  * float[] : 0.0
  * bool[] : false




