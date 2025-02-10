> https://school.programmers.co.kr/learn/courses/30/lessons/42839

```java
import java.util.*;

class Solution {
    Set<Integer> num = new HashSet<>();

    public int solution(String numbers) {
        String[] numbersArray = numbers.split("");
        boolean[] visited = new boolean[numbersArray.length];

        dfs("0", numbersArray, visited);

        return num.size();
    }

    private void dfs(String str, String[] number, boolean[] visited) {

        int decimal = Integer.parseInt(str);
        if(isPrime(decimal)) {
            num.add(decimal);
        }

        for(int i = 0; i < number.length; i++) {
            if(visited[i])  continue;
            visited[i] = true;

            dfs(decimal + number[i], number, visited);

            visited[i] = false;
        }

    }

    public static boolean isPrime(int n) {
        if (n < 2) return false;
        if (n == 2) return true; // 2는 유일한 짝수 소수
        if (n % 2 == 0) return false; // 짝수는 소수가 아님

        for (int i = 3; i <= Math.sqrt(n); i += 2) { // 홀수만 검사
            if (n % i == 0) return false;
        }
        return true;
    }
}
```
