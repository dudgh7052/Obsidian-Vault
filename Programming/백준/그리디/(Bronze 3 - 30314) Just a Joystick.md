---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/30314
```C#
// 정방향과 역방향 둘 중에 더 낮은 이동 카운트를 출력하는 문제
// 기존 랭커꺼에서 자신의 걸로 바꾸기 
// https://www.acmicpc.net/problem/18238 ZOAC 2와 매우 비슷한 문제
int n = int.Parse(Console.ReadLine());

int _firstCount = 0; // 정방향 카운트
int _secondCount = 0; // 역방향 카운트

int _totalCount = 0;

List<string> _list = new List<string>();
_list.Add(Console.ReadLine());
_list.Add(Console.ReadLine());

int _rankerStr = 0;

for (int i = 0; i < n; i++)
{
    _rankerStr = _list[0][i];
    _firstCount = Math.Abs(_rankerStr - _list[1][i]); // 정방향
    _secondCount = 26 - Math.Abs(_rankerStr - _list[1][i]); // 역방향

    if (_firstCount < _secondCount) _totalCount += _firstCount;
    else _totalCount += _secondCount;
}

Console.WriteLine(_totalCount);
```