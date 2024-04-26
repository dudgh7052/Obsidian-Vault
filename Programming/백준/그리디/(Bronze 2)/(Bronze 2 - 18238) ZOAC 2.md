---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/18238
```C#
string _input = Console.ReadLine();

int _firstCount = 0;
int _secondCount = 0;
int _nowChar = 'A';
int _targetChar = 0;
int _totalCount = 0;

for (int i = 0; i < _input.Length; i++)
{
    _targetChar = _input[i];

    _firstCount = Math.Abs(_nowChar - _targetChar); // 오른쪽 방향
    // 왼쪽 방향, 기존 오른쪽 방향으로 돌린거에서 초기화해주는 느낌
    // 26 - 10(오른쪽) = 16(왼쪽 방향 카운트) 
    _secondCount = 26 - Math.Abs(_nowChar - _targetChar); 

    if (_firstCount < _secondCount) _totalCount += _firstCount;
    else _totalCount += _secondCount;

    _nowChar = _targetChar;
}

Console.WriteLine(_totalCount);
```