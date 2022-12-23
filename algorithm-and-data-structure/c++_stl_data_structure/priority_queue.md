# priority_queue

**생성자 예시**
- priority_queue<자료형> pq;
  - 비어있는 우선순위 큐 생성
  - 기본 세팅은 최대힙
- priority_queue<자료형, 컨테이너, 우선순위 지정 방법> pq;
  - 비어있는 우선순위 큐 생성
  - 우선순위 지정 방법에 따라 정렬
  - 우선 순위 지정 방법
    - ![cmp](./priority_queue_cmp.png)

**함수**
###### iterator는 사용이 불가능 합니다
- pq.size()
  - 우선순위 큐에 들어가있는 원소의 개수를 반환
- pq.empty()
  - 비어있으면 true 아니면 false를 반환
- pq.push(x)
  - x를 우선순위 큐에 넣음
- pq.top()
  - 맨 위의 내용을 반환
  - 우선순위 큐가 비어있을 때 사용시 에러
- pq.pop()
  - 맨앞의 원소 삭제
  - 반환값 x
  - 우선순위 큐가 비어있을 때 사용시 에러 
