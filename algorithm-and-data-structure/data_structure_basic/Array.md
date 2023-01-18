# Array
같은 data type을 갖는 원소들을 하나의 group으로 관리

- ### **Array의 ADT**
    <index,value> 쌍의 집합.<br/>
    Array는 인덱스와 value 사이의 mapping으로 정의한다.

- ### **연산**  
  - <p>
      크기가 size인 array 생성.<br/>
      Create(size)
    </p>
  - <p>
      집합 S로 정의 된 Array를 생성.<br/>
      Initialize (S = {<0,value_0>,<1,value_1>,...<n, value_n>})        
    </p>
   - <p>
     Array A의 index에 mapping 되는 value를 반환.<br/>
     Get(A, index)
  - <p>
      Array A의 index에 mapping 되는 값을 value로 선정.<br/>
      Set(A, index, value)
    </P>
- ### **구현**
  - <p>
    Get, Set 연산은 일반적으로 [ ] 연산자로 구현.
    Index는 0부터 시작.
    컴파일러는 Array를 메모리의 연속된 위치에 할당.
    </p>

- ### **Multi-dimensional-Array**
  - <p>
    원소들을 2차원, 3차원 등의 형태로 나타낼 수 있음.
    int Array[ ][ ]... 의 형태로 표현.
    </p>

  
