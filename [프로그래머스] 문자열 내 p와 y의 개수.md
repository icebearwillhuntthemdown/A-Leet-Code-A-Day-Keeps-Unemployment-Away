# [프로그래머스] 문자열 내 p와 y의 개수

* 문제 설명 : 대문자와 소문자가 섞여있는 문자열 s가 주어집니다. s에 'p'의 개수와 'y'의 개수를 비교해 같으면 True, 다르면 False를 return 하는 solution를 완성하세요. 'p', 'y' 모두 하나도 없는 경우는 항상 True를 리턴합니다. 단, 개수를 비교할 때 대문자와 소문자는 구별하지 않습니다. 예를 들어 s가 pPoooyY면 true를 return하고 Pyy라면 false를 return합니다.
* 제한사항
  * 문자열 s의 길이 : 50 이하의 자연수
  * 문자열 s는 알파벳으로만 이루어져 있습니다.
  
<br/><br/>

### 풀이 1
``` java
class Solution {
    boolean solution(String s) {
        String lower = s.toLowerCase();
        char[] charArr = lower.toCharArray();
        int numP = 0;
        int numY = 0;
        
        if(lower.contains("p") || lower.contains("y")){
            for(char c : charArr){
                if(c == 'p') numP++;
                if(c == 'y') numY++;
            }
            
            if(numP == numY){
                return true;
            }else{
                return false;
            }
        }
        return true;
    }
}
```
`contains()` 함수는 파라미터로 char가 아니라 CharSequence를 받는다는 것을 배웠다. CharSequence는 인터페이스고 String이 그 구현체 중 하나로, ""를 써야 한다. 문제를 읽자마자 일단 p, y가 포함되는 조건이 거짓이면 true를 리턴하라기에 if문과 return true;를 먼저 써놓고 시작했는데 다른 사람들 풀이를 보고 그런 일차원적인 접근을 지양해야 함을 배웠다. 이렇게 풀어도 틀린 것은 아니지만 다른 사람들 풀이를 보고 좀 더 효율적으로 짜봤다. 


### 풀이 2
```java
class Solution {
    boolean solution(String s) {
        char[] charArr = s.toLowerCase().toCharArray();
        int count = 0;
    
        for(char c : charArr){
            if(c == 'p') count++;
            if(c == 'y') count--;
        }

        return count == 0;
    }
}
```
다른 사람 풀이를 참고해서 p, y가 둘 다 없거나 수가 같으면 true인 것을 count == 0; 한 줄로 처리해서 변수를 줄였고, `contains()` 호출을 생략했고, 조건문도 없앴다. 정말 똑똑한 접근... :astonished: 기억해둬야지...    
