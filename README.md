# coding test practice

### 프로그래머스 
Q) 구슬을 나누는 경우의 수
```java
class Solution {
    public int solution(int balls, int share) {
        int answer = 0;
        int sub = balls-share;
        int greater;
        int less;
        double dballs = balls;
        if (sub > 0 ) {
	        if (share > sub) {
	    	    greater = share;
	    		less = sub;
	    	}
	    	else {
	    	greater = sub; 
	    	less = share; }
            for (double i = dballs-1; i > 1 ; i--) {
                if (i > greater) {dballs *= i;}
                if (i <= less) {dballs /= i;}
                 }
        }
        return answer = (sub == 0) ? 1 : (int)dballs;
    }
}
```
Q) 최빈값 구하기 
```java
import java.util.Arrays;

class Solution {
    public int solution(int[] array) {
     Arrays.sort(array);
     int length = array.length;
    
     int[] countarray = new int[length];
     int answer = 0;
     int max = 0;
     int count = 0;
     int freqNum = 0;

    for (int i = 0; i < length; i++) {
      int k = i;
      countarray[i] = 0;
      if (k < length-1) {
        while (array[k] == array[k+1]) {
          countarray[i]++;
          k++;
          if (k == array.length-1) break;
        }
      }
    }

    for (int i = 0; i < length; i++) {
      if (countarray[i] > max) {
        max = countarray[i];
        freqNum = i;
      }
    }

    for (int i = 0; i < length; i++) {
      if (countarray[i] == max) {
      count++;
      }
    }

    return answer = (count==1) ? array[freqNum] : -1; 
        
    }
}
```

Q) 숨어있는 숫자의 덧셈 (2) 
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

Q) 분수의 덧셈
```java
class Solution {
    public int[] solution(int denum1, int num1, int denum2, int num2) {
        int[] answer = new int[2];
        int denum = denum1*num2+denum2*num1;
        int num = num1*num2;
        int x = denum;
        int y = num;
        int temp = 0;
        int r = 1;
        if (y > x) {
            temp = x;
            x = y;
            y = temp;
        }
        while (r != 0) {
            r = x % y;
            x = y;
            y = r;
        }
        answer[0] = denum/x;
        answer[1] = num/x;
        return answer;
    }
}
```
