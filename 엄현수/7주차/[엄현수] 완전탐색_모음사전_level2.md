> https://school.programmers.co.kr/learn/courses/30/lessons/84512

```java
import java.util.*;

class Solution {
    private static int cnt = 0;
    private static int answer = 0;
    private static final String[] alphabet = {"A", "E", "I", "O", "U"};
    private static boolean flag = false;


    public int solution(String word) {
        
        dfs("", word);

        return answer;
    }

    private void dfs(String str, String word) {

        if(str.equals(word)) {
            answer = cnt;
            flag = true;
            return;
        }

        if(str.length() == alphabet.length)
            return;

        for (String s : alphabet) {
            cnt++;
            dfs(str + s, word);
            if(flag) return;
        }

    }
}
```
