# Multistage Graph Shortest Path Finder

INF = float('inf')

def multistage_shortest_path(graph, stages, n):
    # cost array
    cost = [0] * (n + 1)
    # path array
    path = [0] * (n + 1)

    # last node cost = 0
    cost[n] = 0

    # calculate from last to first
    for i in range(n - 1, 0, -1):
        min_cost = INF
        for j in range(i + 1, n + 1):
            if graph[i][j] != INF:
                if graph[i][j] + cost[j] < min_cost:
                    min_cost = graph[i][j] + cost[j]
                    path[i] = j
        cost[i] = min_cost

    # construct path
    shortest_path = [1]
    current = 1

    while current != n:
        current = path[current]
        shortest_path.append(current)

    return cost[1], shortest_path


# Example graph (Adjacency Matrix)
# INF means no direct path
graph = [
    [],
    [0, INF, 2, 1, INF, INF, INF, INF],
    [INF, 0, INF, INF, 3, 2, INF, INF],
    [INF, INF, 0, INF, 6, 7, INF, INF],
    [INF, INF, INF, 0, INF, INF, 6, INF],
    [INF, INF, INF, INF, 0, INF, 4, 2],
    [INF, INF, INF, INF, INF, 0, INF, 1],
    [INF, INF, INF, INF, INF, INF, 0, 0]
]

n = 7          # number of nodes
stages = 4     # number of stages

cost, path = multistage_shortest_path(graph, stages, n)

print("Minimum Cost:", cost)
print("Shortest Path:", path)
