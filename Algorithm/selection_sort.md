# 선택 정렬 (Selection Sort)
- 주어진 자료들 중 가장 작은 값의 원소부터 차례로 선택하여 위치를 교환<br>
⇒ **최소값**을 찾아 **맨 앞에 위치한 값**과 교환
- **시간 복잡도** : `O(n^2)`

### 파이썬 코드
```py
def SelectionSort(arr, n):
  for i in range(n-1):
    min_idx = i  # 현재 위치를 최소값이라고 가정
    for j in range(i+1, n):      # 다음 원소들을 순회하며,
      if arr[min_idx] > arr[j]:  # 더 작은 값이 있다면,
        min_idx = j              # 그 위치를 최소값으로 설정

    arr[i], arr[min_idx] = arr[min_idx], arr[i]  # 원래 위치(맨 앞)의 값과 최소값 교환
    return arr
```

## 셀렉션 알고리즘
- `k`번째로 큰 혹은 작은 원소를 찾는 방법
- **시간 복잡도** : `O(kn)`

### 파이썬 코드
```py
def select(arr, k):
  for i in range(k):
    min_idx = i
    for j in range(i+1, len(arr)):
      if arr[min_idx] > arr[j]:
        min_idx = j

    arr[i], arr[min_idx] = arr[min_idx], arr[i]
  return arr[k-1]
```