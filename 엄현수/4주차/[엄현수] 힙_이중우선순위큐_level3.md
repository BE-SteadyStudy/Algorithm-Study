> https://school.programmers.co.kr/learn/courses/30/lessons/42628
>
> 간단하게 풀이
``` java
import java.util.*;

class Solution {
    public int[] solution(String[] operations) {
        int[] answer = new int[2];
        PriorityQueue<Integer> op = new PriorityQueue<>();

        for (int i = 0; i < operations.length; i++) {
            String[] split = operations[i].split(" ");
            if (split[0].equals("I")) {
                op.add(Integer.parseInt(split[1]));
            }
            else if (split[0].equals("D")) {
                if(split[1].equals("-1") && !op.isEmpty()) {
                    op.poll();
                }
                else if (split[1].equals("1") && !op.isEmpty()) {
                    int maxValue = op.stream().max(Integer::compare).orElseThrow();
                    op.remove(maxValue);
                }
            }
        }

        if(op.isEmpty()) {
            return answer;
        }

        int max = op.stream().max(Integer::compare).orElseThrow();
        answer[0] = max;
        answer[1] = op.peek();

        return answer;
    }
}
```
