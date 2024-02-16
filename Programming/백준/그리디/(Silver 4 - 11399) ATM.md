---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/11399
```C#
using System.Collections.Generic;

List<int> _timeList = new List<int>();
int _totalSum = 0;
int _tempSum = 0;
int _count = 0;

_count = int.Parse(Console.ReadLine());
_timeList = Console.ReadLine().Split().Select(int.Parse).ToList();
_timeList.Sort();

for (int i = 0; i < _count; i++)
{
    _tempSum = 0;

    for (int j = 0; j < i + 1; j++)
    {
        _tempSum += _timeList[j];
    }

    _totalSum += _tempSum;
}

Console.WriteLine(_totalSum);
```