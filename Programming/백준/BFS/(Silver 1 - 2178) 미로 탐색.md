---
tags:
  - Baekjoon
  - BFS
---
https://www.acmicpc.net/problem/2178
- 참고: https://chlee200530.tistory.com/133, https://code-piggy.tistory.com/entry/%EB%B0%B1%EC%A4%80-C-2178
```C#
// 최단거리를 구하는기에 너비 우선 탐색(BFS) 활용
using System;
using System.Collections.Generic;

int[] _inputData = Console.ReadLine().Split().Select(x => int.Parse(x)).ToArray();
int N = _inputData[0];
int M = _inputData[1];

int[,] _map = new int[101, 101]; // 맵 저장 행렬
bool[,] _visited = new bool[101, 101]; // 방문 확인 행렬
int[,] _distanceMap = new int[101, 101]; // 시작점부터의 거리를 저장하는 행렬

Queue<(int, int)> _queue = new Queue<(int, int)>();

int[] _dirX = { -1, 1, 0, 0 };
int[] _dirY = { 0, 0, -1, 1 };

// 갈 수 있는 곳인지 맵 정보 초기화
for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();
    for (int j = 0; j < _input.Length; j++)
    {
        _map[i, j] = int.Parse(_input[j].ToString());
    }
}

_distanceMap[0, 0] = 1;
BFS(0, 0);
Console.WriteLine(_distanceMap[N - 1, M - 1]);

void BFS(int argX, int argY)
{
    _queue.Enqueue((argX, argY));
    _visited[argX, argY] = true;
    
    while(_queue.Count != 0)
    {
        var _current = _queue.Dequeue();

        // pop 됐을때의 x좌표, y좌표
        int _curX = _current.Item1;
        int _curY = _current.Item2;

        // 상하좌우 체크
        for (int i = 0; i < 4; i++)
        {
            _curX = _current.Item1 + _dirX[i];
            _curY = _current.Item2 + _dirY[i];

            // 인덱스 범위를 벗어나면 continue
            if (_curX < 0 || _curY < 0 || _curX > N || _curY > M) continue;

            // 이미 방문했거나 해당 집이 0이면 continue
            if (_visited[_curX, _curY] == true || _map[_curX, _curY] == 0) continue;

            _visited[_curX, _curY] = true;
            _queue.Enqueue((_curX, _curY));

            // 기존의 위치의 거리에서 1 더한 값을 현재 위치에 넣기
            _distanceMap[_curX, _curY] = _distanceMap[_current.Item1, _current.Item2] + 1;
        }
    }
}
```