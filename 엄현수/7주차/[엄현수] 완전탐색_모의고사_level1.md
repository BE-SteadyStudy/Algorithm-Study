> https://school.programmers.co.kr/learn/courses/30/lessons/42840

```java
import java.util.*;

class Solution {
    public int[] solution(int[] answers) {
        int[] a1 = {1,2,3,4,5};
        int[] a2 = {2,1,2,3,2,4,2,5};
        int[] a3 = {3,3,1,1,2,2,4,4,5,5};
        int[] answer2 = new int[3];

        for (int i = 0; i < answers.length; i++) {
            if(a1[i % a1.length] == answers[i]) {
                answer2[0]++;
            }
            if(a2[i % a2.length] == answers[i]) {
                answer2[1]++;
            }
            if(a3[i % a3.length] == answers[i]) {
                answer2[2]++;
            }
        }

        int max = Math.max(answer2[0], Math.max(answer2[1], answer2[2]));

        List<Integer> answer = new ArrayList<>();

        for (int i = 0; i < answer2.length; i++) {
            if(answer2[i] == max) {
                answer.add(i + 1);
            }
        }
        return answer.stream().mapToInt(i -> i).toArray();
    }
}
```
