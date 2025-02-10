> https://school.programmers.co.kr/learn/courses/30/lessons/86491

```java
import java.util.*;

class Solution {
    public int solution(int[][] sizes) {
        int answer = 0;

        for (int[] size : sizes) {
            Arrays.sort(size);
        }
        int maxWidth = 0;
        int maxHeight = 0;
        for (int[] i : sizes) {
            maxWidth = Math.max(maxWidth, i[0]);
            maxHeight = Math.max(maxHeight, i[1]);
        }
        answer = maxWidth * maxHeight;
        return answer;
    }
}
```
