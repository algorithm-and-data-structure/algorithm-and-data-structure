# map

- map은 key와 value처럼 관련있는 데이터를 한쌍으로 저장하는 컨테이너인 연관 컨테이너로 기본적으로 구현이 균형잡힌 이진 탐색트리인 레드블랙 트리로 되어있기 때문에 입력과 출력에 O(logn)의 시간이 걸린다.
- map은 key값을 기준으로 정렬이 되며, 같은 key가 동시에 존재할 수 없기에 같은 key를 중복해서 입력시 에러가 발생한다
- O(1)이라는 더 빠른 속도로 map을 사용하기 위해 해시로 이루어진 unordered_map도 존재 하지만 해시값 충돌로 인해 최악의 경우  O(n)의 시간에 동작하게 되는 경우가 발생될 수 있다
  - 때문에 코드포스나 백준, icpc같은 경진대회 준비사이트나 경진대회에서는 unordered_map의 사용을 지양 한다. 

**생성자 예시**
>- map<key의 자료형, value의 자료형> m;


**iterator**
> - map은 iterator로 순회시 key 값이 작은 순서대로 순회가능.
> - key와 value가 pair형태로 들어가 있기에 pair의 포인터를 사용하듯이 사용하면 된다.
> - TIP: iterator는 적을 것이 많아 변수를 생성하는것이 비교적 힘들지만 아래의 방법으로 쉽게가능.
>   - auto tmp=m.begin();

> - m.begin();
>   - 가장 첫 번째 원소의 이터레이터를 반환.
>
>- m.end();
>   - 가장 마지막 원소의 다음 이터레이터를 반환.

  
**함수**

> - m.size() 
>   - map이 가진 원소의 개수를 반환.
  
> - m.empty()
>   - map이 비어있을 경우 true 아닐경우 false를 반환.

>- m.clear(); 
>   - 모든 원소를 제거.
>   - 원소만 제거하고 메모리는 남음.
>   - size만 줄어들고 capacity(메모리양)은 그대로 남음.

>- m.insert({k,v}); 
>   - map에 값 k를 key로 하는 value v를 넣음.
>   - 시간복잡도: O(logn)

> - m.erase(k); 
>   - 값 k를 제거.
>   - 시간복잡도 O(logn).

>- m.erase(iter); 
>   - iter 가 가리키는 원소를 제거.
>   - 시간복잡도 O(logn).

>- m.lower_bound(k); 
>  - key k가 시작하는 구간의 iterator.
>  - 시간복잡도 O(logn).

>- m.upper_bound(k); 
>   - key k가 끝나는 구간 다음칸에 해당하는 iterator.
>   - 시간복잡도 O(logn).

>- m.count(k)
>   - m안에 있는 k의 개수
>   - map에서는 k의 존재 유무를 확인시에만 사용하지만 여러개의 값이 들어갈 수 있는 multimap에서는 개수를 구할 때 사용할 수 있다.

**map을 쉽게 사용하는 방법**

>- m[k];
>   - key k가 가지고 있는 값을 반환.
>   - k에 해당하는 key가 없을시 value를 해당 자료형의 초기값으로 해서 생성.

>- m[k]=v;
>   - key k가 없을 경우 key를 k로 value를 v로 하는 노드를 추가
>   - 있을 경우 key k가 가진 value를 v로 변경

>- TIP
>   - m[k]++;이나 m[k]*=a; 등의 방식으로도 사용 가능

