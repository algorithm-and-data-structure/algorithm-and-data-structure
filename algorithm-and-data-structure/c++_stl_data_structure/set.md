# set

- set은 key와 value처럼 관련있는 데이터를 한쌍으로 저장하는 컨테이너인 연관 컨테이너로 기본적으로 구현이 균형잡힌 이진 탐색트리인 레드블랙 트리로 되어있다
때문에 입력과 출력에 O(logn)의 시간이 걸린다.
- set은 같은 원소가 동시에 존재할 수 없기에 같은 값을 중복해서 입력시 무시된다
- O(1)이라는 더 빠른 속도로 set을 사용하기 위해 해시로 이루어진 unordered_set도 존재 하지만 해시값 충돌로 인해 최악의 경우  O(n)의 시간에 동작하게 되는 경우가 발생될 수 있다
  - 때문에 코드포스나 백준, icpc같은 경진대회 준비사이트나 경진대회에서는 unordered_set의 사용을 지양 한다. 

**생성자 예시**
- set<자료형> st;


**iterator**
- set은 iterator로 순회시 값이 작은 순서대로 순회가능
- tip: iterator는 적을 것이 많아 변수를 생성하는것이 비교적 힘들지만 아래의 방법으로 쉽게가능
  - auto tmp=s.begin();

- v.begin();
  - 가장 첫 번째 원소의 이터레이터를 반환
 
- v.end();
  - 가장 마지막 원소의 다음 이터레이터를 반환

  
**함수**

- st.size() 
  - set이 가진 원소의 개수를 반환
  
- st.empty()
  - set이 비어있을 경우 true 아닐경우 false를 반환

- st.clear(); 
  - 모든 원소를 제거.
  - 원소만 제거하고 메모리는 남음.
  - size만 줄어들고 capacity(메모리양)은 그대로 남음

- st.insert(k); 
  - set에 값 k를 넣음
  - 반환 값으로 pair<집어넣어진 iterator,집어 넣었는지에 대한 bool>이 반환됨
  - 시간복잡도: O(logn)

- v.erase(k); 
  - 값 k를 제거
  - 시간복잡도 O(logn).

- v.erase(iter); 
  - iter 가 가리키는 원소를 제거
  - 시간복잡도 O(logn).

- st.lower_bound(k); 
  - 원소 k가 시작하는 구간의 iterator.
  - 시간복잡도 O(logn).

- st.upper_bound(k); 
  - 원소 k가 끝나는 구간의 iterator.
  - 시간복잡도 O(logn).

- st.count(k)
  - st안에 있는 k의 개수
