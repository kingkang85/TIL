# 위상 정렬 (Topology Sort)
- ${\textsf{\color{crimson}사이클이 없는 방향 그래프}}$의 모든 노드를 방향성에 거스르지 않도록 순서대로 나열


## 진입차수와 진출차수
- 진입차수 (Indegree) : 특정한 노드로 들어오는 간선의 개수
- 진출차수 (Outdegree) : 특정한 노드에서 나가는 간선의 개수


## 동작 과정 (큐 이용)
1. 진입차수가 0인 모든 노드 큐에 삽입
2. 큐가 빌 때까지 다음 과정 반복
  - 큐에서 원소를 꺼내 해당 노드에서 나가는 간선 제거
  - 새롭게 진입차수가 0인 노드 큐에 삽입

(단, 모든 원소를 방문하기 전에 큐가 빈다면 ${\textsf{\color{blue}사이클이 존재}}$)<br>

⇒ 결론 : ${\textsf{\color{orange}큐에 들어온 순서}}$가 ${\textsf{\color{orange}위상 정렬을 수행한 결과}}$와 같음


## 파이썬 코드
```py
from collections import deque

# 위상 정렬 함수
def topology_sort():
  result = []
  q = deque()

  # 진입차수가 0인 노드를 큐에 삽입
  for i in range(1, v+1):
    if indegree[i] == 0:
      q.append(i)
    
  while q:
    # 큐에서 원소 꺼내기
    now = q.popleft()
    result.append(now)

    # 해당 노드에서 나가는 간선 제거
    for next in graph[now]:
      indegree[next] -= 1
      # 새롭게 진입차수가 0인 되는 노드 큐에 삽입
      if indegree[next] == 0:
        q.append(next)
  
  # 결과 출력
  for node in result:
    print(node, end=' ')


# 노드의 개수와 간선의 개수 입력 받기
v, e = map(int, input().split())
# 모든 노드에 대한 진입차수 0으로 초기화
indegree = [0] * (v+1)
# 각 노드에 연결된 간선 정보를 담기 위한 연결 리스트
graph = [[] for _ in range(v+1)]

# 방향 그래프의 모든 간선 정보 입력 받기
for _ in range(e):
  a, b = map(int, input().split())
  graph[a].append(b)
  indegree[b] += 1

topology_sort()
```