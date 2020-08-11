# First Recurring Character

## Instruction
Return the first recurring character.  

//Google Question  
//Given an array = [2,5,1,2,3,5,1,2,4]: It should return 2    
//Given an array = [2,1,1,2,3,5,1,2,4]: It should return 1  
//Given an array = [2,3,4,5]: It should return undefined  
//Given an array = [2,5,5,2,3,5,1,2,4]: return 5 because the pairs are before 2,2  

## Answer 1 : The naive and wrong one
```javascript
const arr1 = [2,5,1,2,3,5,1,2,4];
const arr2 = [2,1,1,2,3,5,1,2,4];
const arr3 = [2,3,4,5];
const arr4 = [2,5,5,2,3,5,1,2,4];

firstRecurringCharacter(arr1); // 2
firstRecurringCharacter(arr2); // 2, 오답
firstRecurringCharacter(arr3); // undefinded
firstRecurringCharacter(arr4); // 2, 오답

firstRecurringCharacter([2,5,5,2,3,5,1,2,4]);

function firstRecurringCharacter(input){
  for(let i = 0; i < input.length; i++){
    for(let j = i+1; j < input.length; j++){
      if(input[i] === input[j]){
        return input[i];
      }
    }
  }
  return undefined;
}
```
일단 코드를 쓰면서도 O(n^2)이라서 찝찝했는데, 이 경우는 arr2, arr4의 경우는 커버하지 못한다. 그래서 틀린 풀이.  

## Answer 2
``` javascript
const arr1 = [2,5,1,2,3,5,1,2,4];
const arr2 = [2,1,1,2,3,5,1,2,4];
const arr3 = [2,3,4,5];
const arr4 = [2,5,5,2,3,5,1,2,4];

firstRecurringCharacter(arr1); // 2
firstRecurringCharacter(arr2); // 1
firstRecurringCharacter(arr3); // undefined
firstRecurringCharacter(arr4); // 5

function firstRecurringCharacter(input){
  let map = new Map();
  for(let i = 0; i < input.length; i++){
    if(map.get(input[i])){
      return input[i];
    }else{
      map.set(input[i], true);
    }
  }
  return undefined;
}
```
O(n)이고 arr2, arr4 같은 경우에도 적용된다. 반복문으로 map에 배열의 요소들을 하나씩 넣고, 이미 map에 존재하는 값을 만나면 return하는 식이다.  

## What I learnt
자바스크립트 map[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Map#Examples]에 대해서 배웠다
  * Map과 Object는 모두 Hash table로 유사하지만 다르다.
  * map[key] = value; 도 동작은 하는데 object와 구분을 위해 지양하고 메소드를 쓰는 것이 좋다고 한다.  
  * Map methods
    * let myMap = new Map();
    * get(key)
    * set(key, value)
    * has(key)
    * clear()
    * delete(key)
  * Map iteration methods
    * map.keys() : returns keys
    * map.values() : returns values
    * map.entries() : returns key, value pairs(entries). default in for of loop
    ```javascript
    let priceTable = new Map([
      ['apple', 500],
      ['banana', 400],
      ['orange', 1000]
    ]);
    
    for(let entry of priceTable){ //priceTable.entries()와 같다
      console.log(entry); // ['apple', 500]['banana', 400]['orange', 1000]
    }
    ```
  
  


