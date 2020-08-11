# First Recurring Character

## Instruction
Return the first recurring character.  

//Google Question
//Given an array = [2,5,1,2,3,5,1,2,4]: It should return 2    
//Given an array = [2,1,1,2,3,5,1,2,4]: It should return 1  
//Given an array = [2,3,4,5]: It should return undefined  
//Given an array = [2,5,5,2,3,5,1,2,4]: return 5 because the pairs are before 2,2  

## Answer
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
