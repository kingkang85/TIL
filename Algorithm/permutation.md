# 순열 (Permutation)
- 서로 다른 N개에서 R개를 중복 없이, 순서를 고려하여 나열

## 중복 순열
- 서로 다른 N개에서 R개를 ${\textsf{\color{red}중복을 허용하고}}$, 순서를 고려하여 나열

```py
path = []  # 경로를 기록할 리스트
# 0부터 시작하여 3개가 되면 종료
def perm(level):
    # 기저 조건
    if level == 3:
        print(*path)
        return

    # 후보군을 반복
    for i in range(1, 7):
        path.append(i)   # 재귀 호출 전 경로 기록
        perm(level + 1)  # 다음 재귀 호출
        path.pop()       # 재귀 호출 후 사용 경로 삭제

perm(0)
```

```py
path = []  # 경로를 기록할 리스트
used = [0] * 7  # 1~6 숫자의 사용 여부 기록할 리스트
# 0부터 시작하여 3개가 되면 종료
def perm(level):
    # 기저 조건
    if level == 3:
        print(*path)
        return

    # 후보군을 반복
    for i in range(1, 7):
      # if i in path:  # 시간 복잡도 : O(len(path)) => 비효율적
      #   continue
      
      if used[i] == 1:
        continue
      
      used[i] = 1
      path.append(i)   # 재귀 호출 전 경로 기록 + 사용 기록
      perm(level + 1)  # 다음 재귀 호출
      path.pop()       # 재귀 호출 후 사용 경로 삭제 + 사용 여부 초기화
      used[i] = 0

perm(0)
```