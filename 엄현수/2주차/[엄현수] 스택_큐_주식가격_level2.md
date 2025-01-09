> https://school.programmers.co.kr/learn/courses/30/lessons/42584
>
> 일일히 완전탐색으로 해도 가능했지만 시간복잡도가 O(n^2)가 나오기 때문에 스택을 사용하여 O(n)으로 줄이기로 하였음

```java
import java.util.*;


class Solution {
    public int[] solution(int[] prices) {
        int[] answer = new int[prices.length];
        Stack<Integer> idxStack = new Stack<>();
        
        for(int i = 0; i < prices.length; i++) {
            while(!idxStack.isEmpty() && prices[i] < prices[idxStack.peek()]) {
                int index = idxStack.pop();
                answer[index] = i - index;
            }
            idxStack.push(i);
        }
        
        while(!idxStack.isEmpty()) {
            int index = idxStack.pop();
            answer[index] = prices.length - 1 - index;
        }
        
        return answer;
        
        
//         int[] answer = new int[prices.length];

//         for (int i = 0; i < prices.length; i++) {
//             int price = prices[i];
//             for (int j = i + 1; j < prices.length; j++) {
//                 if (price > prices[j]) {
//                     answer[i] = j - i;
//                     break;
//                 }
//                 if(j == prices.length - 1) {
//                     answer[i] = prices.length - i - 1;
//                 }
//             }
//         }
        
//         return answer;
    }
}
```
