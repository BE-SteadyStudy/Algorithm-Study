> https://school.programmers.co.kr/learn/courses/30/lessons/42746
>
> string array로 바꿔서 정렬 함수 override 해서 해결
```java
import java.util.*;

class Solution {
    public String solution(int[] numbers) {
        String answer = "";

        String[] array = Arrays.stream(numbers).mapToObj(String::valueOf).toArray(String[]::new);

        Arrays.sort(array, new Comparator<String>() {
            @Override
            public int compare(String o1, String o2) {
                String order1 = o1 + o2;
                String order2 = o2 + o1;
                return order2.compareTo(order1);
            }
        });

        answer = String.join("", array);
        
        if (answer.charAt(0) == '0') {
            return "0";
        }

        return answer;
    }
}
```
