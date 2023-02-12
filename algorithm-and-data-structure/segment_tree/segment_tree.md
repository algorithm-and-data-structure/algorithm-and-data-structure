# 세그먼트 트리
- 특정지점의 값을 업데이트 하는 point update와 특정 범위에 대해 값을 구하는 range query를 모두 O(logN)의 시간으로 처리 가능한 자료구조이다.

- 이 문서는 많은 변형이 존재하는 세그먼트 트리에서 기초적인 형태라고 할 수있는 교환법칙이 성립하는 연산 중 구간 합을 구하는 방법에 대한 내용이다.

**누적합을 이용한 구간합**
-
- 누적합을 이용한 구간합의 경우 전처리에 O(N), range query에 O(1)의 시간이 드는 방법이다.

- 세그먼트 트리보다 구현이 쉽고 빨라 종종 사용하게 되지만 point update에 O(N)이 걸린다는 큰 단점 때문에 값의 업데이트가 존재할 경우 사용하지 않는다.

**세그먼트 트리**
-
- 위의 내용대로 세그먼트 트리는 point update와 range query를 모두 O(logN)만에 처리하기 때문에 값의 업데이트가 존재하지 않는 경우에는 누적합을 이용한 구간합보다 느려 사용되지 않지만 업데이트가 있을 경우에는 매우 유용한 자료구조이다.

**세그먼트 트리의 형태**
-
- 배열 {0,1,2,3,4}가 존재한다고 할 때 세그먼트 트리는 이렇게 구성된다.
![segmentTree](./segTree%EC%98%88%EC%8B%9C.png)


**세그먼트 트리 구현**
- 
- 세그먼트 트리는 힙처럼 배열을 이용하여 구현이 되며 완전이진트리의 모습을 하게된다.
- 때문에 배열의 길이는 2N 높이는 logN이 되게 되지만 일부 특수한 상황의 경우 2N을 넘어가는 경우가 있어 4N의 공간을 확보해 두는 것을 추천한다.

**point update**

![segmentTree update](./segTree_update%EC%98%88%EC%8B%9C.png)

``` c++
public:
	void update(int idx, ll num) {
		update(idx, num, 0, last, 1);
	}
private:
	ll update(int idx, ll num, int left, int right, int now) {
		if (idx < left || right < idx) return 0LL;

		ll c = 0;
		if (left == right) {
			c = num - tree[now];
		}
		else {
			int mid = (left + right) / 2;
			c = update(idx, num, left, mid, now * 2) 
				+ update(idx, num, mid + 1, right, now * 2 + 1);
		}

		tree[now] += c;
		return c;
	}
```

**range query**

[2,4]에 해당하는 부분합을 구하기 위해선 초록색으로 칠해진 부분을 더하면 된다. 

![segmentTree query](./segTree_query%EC%98%88%EC%8B%9C.png)

``` c++
public:
	ll query(int l, int r) {
		return query(l, r, 0, last, 1);
	}
private:
	ll query(int l, int r, int left, int right, int now) {
		if (right < l || r < left) return 0LL;
		if (l <= left && right <= r) return tree[now];

		int mid = (left + right) / 2;
		ll res = query(l, r, left, mid, now * 2) 
			+ query(l, r, mid + 1, right, now * 2 + 1);

		return res;
	}
```