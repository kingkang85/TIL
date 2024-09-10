# MST (최소 신장 트리)
- 신장 트리 (Spanning Tree)
  - 무향 그래프에서 n개의 정점과 n-1개의 간선으로 이루어진 트리
- ${\textsf{\color{orange}최소 신장 트리 (Minimum Spanning Tree)}}$
  - 무향 가중치 그래프에서 신장 트리를 구성하는 간선들의 가중치의 합이 최소인 신장 트리

## KRUSKAL 알고리즘
1. 모든 간선을 가중치에 따라 ${\textsf{\color{blue}오름차순}}$으로 정렬
2. 가중치가 가장 낮은 간선부터 선택
  - 두 대표자가 다르다면, 엣지를 최소 비용 집합에 추가
  - 두 대표자가 같다면, ${\textsf{\color{crimson}사이클이 생성}}$되므로 무시
3. n-1개의 간선이 선택될 때까지 ${\textsf{\color{blue}2번 과정}}$을 반복

```py
class DisjointSet:
  def __init__(self, v):
    self.p = [0] * (len(v) + 1)
  
  def make_set(self, x):
    self.p[x] = x
  
  def find_set(self, x):
    if x != self.p[x]:
      self.p[x] = self.find_set(self.p[x])
    return self.p[x]
  
  def union(self, x, y):
    px = self.find_set(x)
    py = self.find_set(y)

    if px < py:
      self.p[y] = px
    else:
      self.p[x] = py

def mst_kruskal(vertices, edges):
  mst = []
  n = len(vertices)
  cls = DisjointSet(vertices)

  for i in range(n+1):
    cls.make_set(i)
  
  edges.sort(key = lambda x: x[2])

  for edge in edges:
    s, e, w = edge
    if cls.find_set(s) != cls.find_set(e):
      cls.union(s, e)
      mst.append(edge)
  return mst

# [시작 정점, 도착 정점, 가중치]
edges = [[1, 2, 1], [2, 3, 3], [1, 3, 2]]
vertices = [1, 2, 3]  # 정점 집합
mst_kruskal(vertices, edges)  # [[1, 2, 1], [1, 3, 2]]
```

## PRIM 알고리즘
1. 임의 정점을 하나 선택
2. 우선순위 큐를 사용하여 간선의 가중치가 ${\textsf{\color{blue}가장 작은}}$ 간선을 선택
3. 해당 간선이 연결하는 정점이 이미 방문한 정점이 아니라면, 이 간선을 ${\textsf{\color{orange}최소 신장 트리에 추가하고 방문 표시}}$
4. 우선순위 큐가 빌 때까지 반복

```py
import heapq
def prim(vertices, edges):
  mst = []

  adj_list = {v:[] for v in vertices}
  for start_v, end_v, w in edges:
    adj_list[start_v].append((end_v, w))
    adj_list[end_v].append((start_v, w))

  visited = set()
  init_vertex = vertices[0]
  min_heap = [[w, init_vetex, e] for e, w in adj_list[init_vertex]]
  heapq.heapify(min_heap)
  visited.add(init_vertex)

  while min_heap:
    weight, start_v, end_v = heapq.heappop(min_heap)
    if end_v in visited:
      continue
    
    visited.add(end_v)
    mst.append((start_v, end_v, weight))

    for adj_v, adj_w in adj_list[end_v]:
      if adj_v in visited:
        continue
      heapq.heappush(min_heap, [adj_w, end_v, adj_v])
  return mst

vertices = [1, 2, 3]
edges = [[1, 2, 30], [2, 3, 20], [1, 3, 10]]
mst = prim(vertices, edges)  #[(1, 3, 10), (3, 2, 20)]
```