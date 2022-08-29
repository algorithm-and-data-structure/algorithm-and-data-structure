# string

**생성자 예시**
- string s;
  - 비어있는 string s를 생성합니다.
  - string 을 선언 이후 s="123";형식으로 해서 일반 변수와 비슷하게 사용가능
- string s= "123";
  - "123"으로 초기화된 string을 생성
- string s(str)
  - 배열로 이루어진 문자열 str을 생성자의 인자의 인자로 입력시 str안의 문자열로 string이 초기화됨
  

**연산자**
- []
  - string은 []를 통해 배열처럼 i번째의 원소에 접근 가능
  - 사용법: s[i]
- &#43;
  - +를 이용하여 문자열 두개를 합친 새로 생성된 문자열을 반환
  - s1이 "123"이고 s2가 "456"이라면 s1+s2는 "123456"이 반환된다
  - s1+s2를 할 때 s1과 s2에는 변화가 없다.
- ==
  - 문자열 두개를 비교한다
  - 다르면 false 같으면 true를 반환한다
  - 예시: s1==s2

**함수**
###### [vector](https://github.com/LEE026/algorithm-and-data-structure/blob/main/c%2B%2B_stl_data_structure/vector.md)와 함수가 같기에 추가된 함수만을 기록

- s.length()
  - 문자열의 길이를 반환
  - 예를들어 "123"이면 3을 반환
  - s.size()와 결과는 똑같지만 length가 좀 더 직관적임
- s.substr(idx,len)
  - idx부터 시작해서 len 길이의 string 반환
  - 예시: s가 "0123456"일 때 s.substr(3,3)을 하면 "345"가 반환됨
  - 시간 복잡도: O(len)
