# 이진탐색(Binary Search)
- **정렬되어있는 배열에서** 특정한 값을 찾아내는 알고리즘

- 정렬되어 있지 않다면 정상작동을 보장할 수 없음

- 배열 중간의 임의의 값을 선택하고 찾고자하는 값인 X와 비교해서 X가 중간 값보다 작으면 중간을 기준으로 왼쪽에 있는 데이터 들을, 크면 오른쪽에 있는 데이터들을 동일한 방법으로 탐색하고 이 과정을 더이상 탐색할 것이 없거나, 중앙값이 X일경우 까지 반복하여 값을 찾는 알고리즘

- 이진탐색의 시간복잡도는 **O(logn)**이고 많은 곳에서 쓰이고 있다


**이진탐색 예시**
> { 17, 28, 43, 67, 88, 92, 100 }에서 43을 검색시

> 1. 가운데의 값인 67과 43을 비교하면 43이 67보다 작기 때문에 찾으려는 값은 67의 좌측에 있는걸 알 수 있다.
> 2. 좌측에 있는 배열을 대상으로 다시 탐색을 진행 할 경우 배열은 { 17, 28, 43 }이되고 이 배열의 가운데 값인 28과 43을 비교시 43이 더 크기에 찾으려는 값이 우측에 있다는 것을 알 수 있다.
> 3. 우측에 있는 배열을 대상으로 탐색을 진행할 경우 배열은 {43}이 되며 다시 가운데의 값과 찾으려는 값을 비교시 43으로 일차하기에 해당하는 값을 찾고 종료한다.


**c++ stl로 있는 이진탐색**
> - binary_search
> - lower_bound
> - upper_bound

**코딩테스트에서의 팁**
> 알고리즘들 중에서 O(logn)만에 동작되는 알고리즘은 거의 없고, 그 중 대표적인 알고리즘이 이진탐색이기에 알고리즘 문제에서 O(logn)만에 해결해야 되는 부분이 있을경우 이진탐색 계열 알고리즘을 생각해 보는 것이 좋다.
