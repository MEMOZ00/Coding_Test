# coding test practice

### 프로그래머스 

Q) 숨어있는 숫자의 덧셈 (2) 71/100 
```java
class Solution {
    public int solution(String my_string) {
        int answer = 0;
        int[] numList = new int[my_string.length()];
        
        for(int i = 0; i < my_string.length(); i++) {
            if(my_string.charAt(i) - '0' >= 0 && my_string.charAt(i)- '0' < 10) {
               numList[i] = my_string.charAt(i) - '0';
               int k = i; 
               while(k < my_string.length()-1 && my_string.charAt(k+1) - '0' >= 0 && my_string.charAt(k+1) - '0' < 10) {
                   numList[i] *= 10;     
                   k++;                 
                   }
                answer += numList[i];    
            } else {
                answer += numList[i];
            }
        } 

        return answer;
    }
}
```
