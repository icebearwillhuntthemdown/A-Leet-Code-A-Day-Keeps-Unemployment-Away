# Big O 

## What is good code?
* **Readable**  
Is it clean and easy for others to read?
* **Scalable**
  * Memory - Space complexity
    How much memory does it take?
      * Heap : where we store variables that we assign values to
      * Stack : where we keep track of function calls 
  * Speed - Time complexity
    Does it scale as things grow larger?
<br/><br/>

## Big O
Big O is the measurement of scalability. Big O means how quickly the runtime grows, and measured by comparing the size of input and the number of operations that increases.   
![Courtesy from bigocheatsheet.com/](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbfTRLc%2FbtqF5eKu4wq%2FG1KP7fZGO2mdFIenj8ppiK%2Fimg.png =500x)  
Courtesy from bigocheatsheet.com/  
* O(1) : Constant Time.  
No loops.
* O(log N) : Logarithmic.   
* O(n) : Linear Time.  
The number of operations increases by the same amount of elements. For, while loops through n times.
* O(n log(n)) Logt Linear.
* O(n^2) : Quadratic.
* O(2^n) : Exponential
* O(n!)(a.k.a. no! :rofl:) : Factorial.  
Adding a loop for every element, which is the least efficient case.
<br/><br/>

### Rules
1. Always worst Case  
Big O only cares about **the worst case scenario**. If you're looking for a specific element in an array of size 10, consider it's at index 10 even though you might find it at index 1.
2. Remove constants  
Big O only cares about **how the line moves as inputs increase** meaning it doesn't matter how steep the line is. So drop the constants. At the end of the day it's just linear. e.g.) O(n/2 + 100000) -> O(n).
3. Different terms per input  
Different inputs, different variables. Consider each parameter as **separate n's**. If two parameters are taken in a method, the Big O notation would be O(a + b) if they're in the same indentation, or O(a * b) if nested. 
4. Drop non dominants  
Drop all except the most dominant one. e.g.) O(n + n^2) -> O(n^2), O(x^2+3x+100+x/2) -> O(x^2)
<br/><br/>

### What can cause time in a fucntion?
* Operations (+, -, *, /)
* Comparisons (<, >, ==)
* Looping (for, while)
* Outside Function call (function())

### What causes Space complexity?
* Variables
* Data structure
* Function call
* Allocations

## Reference
* [Udemy](https://www.udemy.com/course/master-the-coding-interview-data-structures-algorithms/)
* [The Big O Cheat Sheet](https://www.bigocheatsheet.com/)

