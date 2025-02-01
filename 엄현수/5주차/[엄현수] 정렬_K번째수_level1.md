> https://school.programmers.co.kr/learn/courses/30/lessons/42748
>
> Arrays.copyOfRange()와 Arrays.sort() 함수 사용
```java
import java.util.*;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];

        for(int i = 0; i < commands.length; i++){
            int start = commands[i][0];
            int end = commands[i][1];
            int[] sub = Arrays.copyOfRange(array, start - 1, end);
            Arrays.sort(sub);
            answer[i] = sub[commands[i][2] - 1];
        }

        return answer;
    }
}
```
