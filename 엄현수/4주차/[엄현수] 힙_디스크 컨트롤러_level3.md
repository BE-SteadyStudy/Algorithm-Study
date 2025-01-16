> https://school.programmers.co.kr/learn/courses/30/lessons/42627
>
> 어려웠다.. Task라는 클래스를 따로 만들어서 조건에 맞게 정렬을 시켜준다음 시간순서대로 처리하였다.
```java
import java.util.*;

class Solution {
    public int solution(int[][] jobs) {
        int answer = 0;

        int time = 0;  // 현재 시간
        int completeTask = 0;   // 완료된 작업 개수
        PriorityQueue<Task> disk = new PriorityQueue<>();
        PriorityQueue<Task> diskController = new PriorityQueue<>(Comparator.comparingInt(t -> t.turnAroundTime)); // 실행시간이 적은 것부터 정렬

        for(int[] i : jobs) {
            disk.add(new Task(i[0], i[1]));
        }

        while(completeTask < jobs.length) { // 작업이 완료된 건이 총 작업의 개수를 넘으면 종료

            while (!disk.isEmpty() && time >= disk.peek().requestTime) {  // 현재 시간이 다음 대기작업의 요청시간보다 같거나 높다면
                diskController.add(disk.poll()); // 디스크 컨트롤러에 작업 삽입
            }

            if(!diskController.isEmpty()) {  // 디스크 컨트롤러에 작업이 있다면
                Task task = diskController.poll();   //  diskController 에서 작업을 빼기
                if(time < task.requestTime) {   // 시간을 요청 시간으로 이동
                    time = task.requestTime;
                }
                time += task.turnAroundTime;    // 작업이 다 끝난 시점으로 이동
                completeTask++; // 완료 개수를 늘리고
                answer += time - task.requestTime; // 반환 시간을 세기
            } else if(!disk.isEmpty()) {    // 디스크 컨트롤러에 아무것도 없다면
                time = disk.peek().requestTime; // 다음 작업의 요청시각으로 이동
            }
        }

        return answer / jobs.length;
    }
}
class Task implements Comparable<Task> {
    int requestTime;
    int turnAroundTime;

    public Task(int requestTime,int turnAroundTime) {
        this.requestTime = requestTime;
        this.turnAroundTime = turnAroundTime;
    }

    @Override
    public int compareTo(Task o) {
        if(this.requestTime == o.requestTime) { return this.turnAroundTime - o.turnAroundTime;}
        return this.requestTime - o.requestTime;
    }
}
```
