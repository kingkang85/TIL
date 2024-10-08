# 24.08.01.
# 검색
## 1. 순차 검색 (Sequential Search)
- 일렬로 되어 있는 자료를 순서대로 검색
- 검색 대상의 수가 많을 때는 비효율적

---
### 정렬되어 있지 않은 경우
- 자료구조의 마지막을 향해 검색 대상을 찾아 나감
- 평균 비교 횟수 : (1/n)*(1+2+...+n) = `(n+1)/2`
- **시간 복잡도** : `O(n)`

#### 파이썬 코드
```py
def sequential_search(a, n, key):
  i = 0
  while i < n and a[i] != key:
    i += 1
  if i < n:  # a[i] == key인 경우
    return i
  else:
    return -1
```

---
### 정렬되어 있는 경우
- 원소의 키 값이 검색 대상의 키 값보다 크면 검색 종료
- 검색 실패의 경우 평균 비교 횟수가 **반으로 줄어듬**
- **시간 복잡도** : `O(n)`

#### 파이썬 코드
```py
def sequential_search2(a, n, key):
  i = 0
  while i < n and a[i] < key:  # key 값이 더 큰 경우도 고려
    i += 1
  if i < n and a[i] == key:
    return i
  else:
    return -1
```

## 2. 이진 검색 (Binary Search)
- 자료의 가운데에 있는 항목의 키 값과 비교하여 다음 검색의 위치를 결정하고 검색
- 자료가 **정렬**된 상태여야 함<br>
⇒ 자료에 삽입이나 삭제가 발생했을 때 다시 정렬하는 추가 작업이 필요
- 시간 복잡도 : O(logN)
  - 정렬이 필요한 경우 O(NlogN + logN)

### 검색 과정
1. 자료 중앙의 원소 선택
2. 중앙 원소 값과 목표 값 비교
3. 목표 값이 작으면 자료의 왼쪽 반에 대해서, 크면 오른쪽 반에 대해서 새로 검색
4. 목표 값을 찾을 때까지 1~3 반복

#### 파이썬 코드
```py
# 반복 구조
def binary_search(a, n ,key):
  start = 0
  end = n-1
  while start <= end:
    middle = (start + end)//2

    if a[middle] == key:  # 검색 성공
      return a[middle]

    elif a[middle] > key:
      end = middle - 1

    else:
      start = middle + 1
  return -1  # 검색 실패
```

```py
# 재귀 구조
def binary_search(low, high, target):
    # 기저조건 : target 을 발견하지 못하면 종료
    if low > high:
        return -1

    mid = (low + high)//2

    if target == arr[mid]:  # 검색 성공시 리턴
        return mid

    # target 이 mid 보다 작다 
    # == target이 mid 의 왼쪽에 존재한다
    # == high를 mid - 1로
    elif target < arr[mid]:
        return binary_search(low, mid - 1, target)

    else:
        return binary_search(mid + 1, high, target)
```