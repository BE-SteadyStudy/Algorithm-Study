> https://school.programmers.co.kr/learn/courses/30/lessons/42842

```java
class Solution {
    public int[] solution(int brown, int yellow) {
        for (int i = 1; i <= yellow; i++) {
            if(yellow % i == 0 && (yellow / i + i) * 2 + 4 == brown) {
                return new int[] {yellow / i + 2, i + 2};
            }            
        }
        return null;
    }
}
```
