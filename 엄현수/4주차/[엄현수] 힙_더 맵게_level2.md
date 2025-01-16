> https://school.programmers.co.kr/learn/courses/30/lessons/42626
>
> PriorityQueue를 사용하여 작은 순서대로 처리
```java
import java.util.*;

class Solution {
    public int solution(int[] scoville, int K) {
        int answer = 0;
        PriorityQueue<Integer> minHeap = new PriorityQueue<>();
        
        for(int i : scoville) {
            minHeap.add(i);
        }
        
        while(minHeap.peek() < K) {
            if (minHeap.size() <= 1) {
                return -1;
            }
            
            int first = minHeap.poll();
            int second = minHeap.poll();
            minHeap.add(first + (second * 2));
            answer++;

        }
        
        return answer;
    }
}
```
