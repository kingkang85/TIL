# 개요
## 재귀호출
- 자신을 다시 호출하는 구조
```py
def fibo(n):
  if n < 2:
    return n

  return fibo(n-1) + fibo(n-2)
```
⇒ 엄청난 중복 호출이 존재한다는 단점

## 메모이제이션
- 이전에 계산한 값을 메모리에 저장해서 전체적인 실행 속도를 빠르게 하는 기술
- 시간복잡도 O(n)
- Top Down 방식

```py
def fibo_memo(n, memo=None):
  if memo is None:
    memo = {}

  if n in memo:
    return memo[n]
  
  if n <= 1:
    return n

  memo[n] = fibo_memo(n-1, memo) + fibo_memo(n-2, memo)
  return memo[n]
```

# DP (동적 계획)
- 그리디 알고리즘과 같이 ${\textsf{\color{crimson}최적화 문제}}$를 해결하는 알고리즘
- 상향식

```py
def fibo_dp(n):
  f = [0] * (n+1)
  f[0] = 0
  f[1] = 1
  for i in range(2, n+1):
    f[i] = f[i-1] + f[i-2]

  return f[n]
```

## 적용 요건
1. 중복 부분문제 구조
  - 큰 문제를 이루는 작은 문제들을 먼저 해결하고 최적 해를 이용하여 순환적으로 큰 문제를 해결
  - 이미 해결된 작은 문제들의 해를 어떤 공간(table)에 저장
  - 저장된 해들이 다시 필요할 때마다 재계산하지 않고 table 참조를 통해 ${\textsf{\color{crimson}중복된 계산을 피함}}$

2. 최적 부분문제 구조
  - 어떤 문제에 대한 해가 최적일 때 그 해를 구성하는 작은 문제들의 해 역시 최적이어야 함

```py
def lis_dp(nums):
  if not nums:
    return []
  
  n = len(nums)
  lis = [1] * n    # 각 숫자까지의 lis 길이 저장
  prev = [-1] * n  # 이전 숫자의 위치 기억

  for i in range(1, n):
    for j in range(i):
      if nums[i] > nums[j] and lis[i] < lis[j] + 1:
        lis[i] = lis[j] + 1
        prev[i] = j
    
  max_length = max(lis)
  max_index = lis.index(max_length)

  result = []
  while max_index != -1:
    result.append(nums[max_index])
    max_index = prev[max_index]
  
  return result[::-1]
```