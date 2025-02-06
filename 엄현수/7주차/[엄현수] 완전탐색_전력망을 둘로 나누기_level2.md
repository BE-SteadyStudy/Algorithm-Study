> https://school.programmers.co.kr/learn/courses/30/lessons/86971

```java
import java.util.*;

class Solution {
    
    private int[] parent;
    
    private void init(int n) {
        for(int i = 1; i <= n; i++) 
            parent[i] = i;
    }
    
    private int findParent(int n) {
        if(parent[n] != n) {
            parent[n] = findParent(parent[n]);
        }
        return parent[n];
    }
    
    private void union(int a, int b) {
        a = findParent(a);
        b = findParent(b);
        
        if(a < b)
            parent[b] = a;
        else
            parent[a] = b;
    }
    
    
    public int solution(int n, int[][] wires) {
        int answer = Integer.MAX_VALUE;
        
        for(int i = 0; i < wires.length; i++) { // i = 끊는 번호
            parent = new int[n+1]; 
            init(n);    // 초기 설정
            
            for(int j = 0; j < wires.length; j++) {
                // i인 것을 제외하고 노드 연결
                if(i == j) continue;
                if(findParent(wires[j][0]) != findParent(wires[j][1])) {
                    union(wires[j][0], wires[j][1]);
                }
            }
            
            Map<Integer, Integer> connect = new HashMap<>();            
            // 부모의 최상의 노드 부터 개수 세기
            for(int j = 1; j <= n; j++) {
                int root = findParent(j);
                connect.put(root, connect.getOrDefault(root, 0) + 1);
            }
            
            if(connect.size() == 2) {
                List<Integer> counts = new ArrayList<>(connect.values());
                int diff = Math.abs(counts.get(0) - counts.get(1));
                answer = Math.min(answer, diff);
            }       
                     
        }        
        
        return answer;
    }
}
```
