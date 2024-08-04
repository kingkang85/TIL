# 24.07.31.
# 2차원 배열
```py
arr = [[0] * 3] * 2  # 얕은 복사
arr[0][0] = 100
print(arr)
```

# 배열 순회
- n*m 배열의 모든 원소를 빠짐 없이 조사

## 행 우선 순회
```py
for i in range(n):
  for j in range(m):
    print(arr[i][j])
```

## 열 우선 순회
```py
for j in range(m):
  for i in range(n):
    print(arr[i][j])
```

## 지그재그 순회
```py
for i in range(n):
  for j in range(m):
    print(arr[i][j + (m-1-2*j) * (i%2)])
```
- 증가 : j (ex. 0, 1, 2, 3)
- 감소 : m-1-j (ex. 3-0, 3-1, 3-2, 3-3)

## 델타를 이용한 2차 배열 탐색


## 전치 행렬
- 원소의 행과 열의 위치가 바뀐 행렬

```py
arr = [[1, 2, 3], [4, 5, 6], [7, 8, 9]]

for i in range(3):
  for j in range(3):
    if i < j:
      arr[i][j], arr[j][i] = arr[j][i], arr[i][j]
```
