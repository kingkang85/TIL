# 서로소 집합
- 교집합이 없는 집합들
- 상호베타 집합 연산
  - Make-Set(x) : 원소 스스로가 대표자가 됨
  - Find-Set(x) : 그룹의 대표자를 반환
  - Union(x, y) : 두 집합을 통합

⇒ 이를 이용해서 ${\textsf{\color{crimson}사이클을 검출}}$<br>
서로 다른 집합에 있는 원소들을 연결하면 사이클이 생기지 않는다!

## 서로소 집합 표현
1. ${\textsf{\color{orange}연결 리스트}}$
- 같은 집합의 원소들을 하나의 연결 리스트로 관리
- 맨 앞의 원소를 대표자로 선정
- 각 원소는 대표자를 가리키는 링크를 가짐

2. ${\textsf{\color{orange}트리}}$
- 같은 집합의 원소들을 하나의 트리로 표현
- 루트 노드가 대표자가 됨
- 어떤 노드의 인덱스와 부모 인덱스가 같으면 대표자

```py
p = [0] * (N+1)

# 새로운 집합 생성
def make_set(x):
  p[x] = x

# x를 포함하는 집합 찾기
def find_set(x):
  if x == p[x]:
    return x
  return find_set(p[x])

# x와 y를 포함하는 두 집합 통합
def union(x, y):
  px = find_set(x)
  py = fine_set(x)

  if px < py:
    p[y] = px
  else:
    p[x] = py
```

## 서로소 집합의 최적화
- ${\textsf{\color{blue}Path compression}}$
  - Find-Set 과정에서 모든 노드들이 직접 root를 가리키도록 함

```py
# 최적화 후
def find_set(x):
  if x != p[x]:
    p[x] = find_set(p[x])
  return p[x]
```

- ${\textsf{\color{blue}Rank를 이용한 Union}}$
  - 각 노드는 자신을 루트로 하는 subtree의 높이를 rank로 저장
  - 두 집합을 합칠 때 rank가 낮은 집합을 rank가 높은 집합에 붙임

```py
# 최적화 후
p = [0] * (N+1)
rank = [0] * (N+1)

def make_set(x):
  p[x] = x

def union(x, y):
  px = find_set(x)
  py = fine_set(y)

  if px != py:
    if rank[px] > rank[py]:
      p[py] = px
    elif rank[px] < rank[py]:
      p[px] = py
    else:
      p[py] = px
      rank[px] += 1
```