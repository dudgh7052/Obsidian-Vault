---
tags:
  - Baekjoon
  - 브루트포스
---
https://www.acmicpc.net/status?from_problem=1&problem_id=1018
```C#
// 처음 인덱스로부터 7,7 떨어진 곳까지 체크해서 바꿀게 있는지 체크
using System.Runtime.Intrinsics.X86;

int[] _matrixInput = Console.ReadLine().Split().Select(int.Parse).ToArray();
int N = _matrixInput[0];
int M = _matrixInput[1];
char[,] _matrix = new char[N, M];

int _minCount = 64;

for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();

    for (int j = 0; j < M; j++)
    {
        _matrix[i, j] = _input[j]; 
    }
}

for (int i = 0; i < N - 7; i++)
{
    for (int j = 0; j < M - 7; j++)
    {
        CheckCount(i, j);
    }
}

Console.WriteLine(_minCount);

void CheckCount(int argStartX, int argStartY)
{
    int _changeCase1 = 0; // 시작이 W인 상황
    int _changeCase2 = 0; // 시작이 B인 상황

    for (int i = argStartX; i < argStartX + 8; i++)
    {
        for (int j = argStartY; j < argStartY + 8; j++)
        {
            if ((i + j) % 2 == 0)
            {
                if (_matrix[i, j] != 'W') _changeCase1++;
                if (_matrix[i, j] != 'B') _changeCase2++;
            }
            else
            {
                if (_matrix[i, j] != 'B') _changeCase1++;
                if (_matrix[i, j] != 'W') _changeCase2++;
            }
        }
    }

    _minCount = Math.Min(_minCount, Math.Min(_changeCase1, _changeCase2));
}
```