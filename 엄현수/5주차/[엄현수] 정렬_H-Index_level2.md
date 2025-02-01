> https://school.programmers.co.kr/learn/courses/30/lessons/42747
>
> 문제 설명이 어려웠다. h번 이상 인용된 논문이 h편 이상이라는 부분을 놓쳤었다.
```java
import java.util.*;

class Solution {
    public int solution(int[] citations) {
        int hIndex = 0;
        Arrays.sort(citations);

        for (int i = 0; i < citations[citations.length - 1] ; i++) {    // 인용된 횟수
            int idx = 0;   // 논문 인덱스
            int count = 0;  // i회 이상 인용된 논문의 수
            while(idx < citations.length) { // 인용된 횟수가 최대 길이만큼만
                if(citations[idx] >= i) {    // 작은 순서대로 i를 넘겼다면
                    count = citations.length - idx;    // 오름차순 정렬이 되어있기 때문에 남은 논문의 갯수가 count
                    if(count >= i)
                        hIndex = i;
                    break;
                }
                idx++;
            }
        }

        return hIndex;
    }
}
```
