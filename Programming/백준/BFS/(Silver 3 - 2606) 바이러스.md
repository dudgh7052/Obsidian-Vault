---
tags:
  - Baekjoon
  - BFS
---
https://www.acmicpc.net/problem/2606
- 참고: https://chlee200530.tistory.com/130
```C#
int N = int.Parse(Console.ReadLine());
int M = int.Parse(Console.ReadLine());

int _count = 0;

int[,] _map = new int[101, 101];
bool[] _visited = new bool[101];

Queue<int> _queue = new Queue<int>(); // 시작 노드를 저장 할 큐

for (int i = 0; i < M; i++)
{
    int[] _input = Console.ReadLine().Split().Select(x => int.Parse(x)).ToArray();

    // 서로 이어주기
    _map[_input[0], _input[1]] = 1;
    _map[_input[1], _input[0]] = 1;
}

BFS();
Console.WriteLine(_count - 1);

void BFS()
{
    // 1번 부터 차례대로 번호가 매겨짐
    _queue.Enqueue(1);
    _visited[1] = true; // 1번은 방문

    int _startX = 0;

    while (_queue.Count != 0)
    {
        _startX = _queue.Dequeue();
        _count++;

        for (int i = 0; i <= N; i++) // 각 번호별로 이어진 노드 찾기
        {
            // _startX와 이어진 컴퓨터 찾고, 체크 했는지 확인
            if (_map[_startX, i] == 1 && _visited[i] == false) 
            {
                _queue.Enqueue(i); // 이어져있고 번호의 컴퓨터가 아직 체크 안됐을 경우 큐에 추가
                _visited[i] = true; // 컴퓨터 체크
            }
        }
    }
} 
```