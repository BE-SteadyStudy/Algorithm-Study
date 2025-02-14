> https://school.programmers.co.kr/learn/courses/30/lessons/87946

```java
class Solution {
    // 최대 던전수 변수 
    private static int max=0;
    public int solution(int k, int[][] dungeons) {
        // 방문 체크 배열 
        boolean[] visited = new boolean[dungeons.length];
        // 완전 탐색
        dfs(k, dungeons, visited, 0, 0);
        return max;
    }
    
    private void dfs(int k, int[][] dungeons, boolean[] visited, int index, int count){
        // 모든 던전을 탐험했으면 
        if(dungeons.length==index){
            max=Math.max(max,count); // 최대 던전수 계산 
            return ;
        }
        
        // 완전 탐색
        for(int i=0;i<dungeons.length;i++){
            if(visited[i]) continue; // 방문했으면 PASS
            visited[i] = true; // 현재 위치 방문 체크하고 다음 탐색 
            
            // 남은 피로도가 최소 필요도보다 크거나 같으면
            // 소모 피로도를 소모한다.
            if(dungeons[i][0]<=k){
                dfs(k-dungeons[i][1], dungeons, visited, index+1, count+1);
            }else{ // 아닌 경우는 그냥 던전 개수만 증가 
                dfs(k, dungeons, visited, index+1, count);
            }
            visited[i] = false; // 탐색 후, 방문 체크 해제 
            
        }
        return ;
    }
    
    
}
```
