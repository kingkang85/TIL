# 검색
## 1. 순차 검색 (Sequential Search)
- 일렬로 되어 있는 자료를 순서대로 검색
- 검색 대상의 수가 많을 때는 비효율적

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
### 정렬되어 있는 경우
- 원소의 키 값이 검색 대상의 키 값보다 크면 검색 종료
- 검색 실패의 경우 평균 비교 횟수가 반으로 줄어듬
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

#### 파이썬 코드
```py
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

## 3. 해쉬 (Hash)

