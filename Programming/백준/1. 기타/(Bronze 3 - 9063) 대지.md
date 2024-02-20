---
tags:
  - Baekjoon
---
https://www.acmicpc.net/problem/9063
- 제일 작은 x,y와 제일 큰 x,y를 구하기 위해 오름차순으로 정렬 후 출력 
```C#
using System.Collections.Generic;

List<int> _xList = new List<int>();
List<int> _yList = new List<int>();

int _length = int.Parse(Console.ReadLine());
int[] _input = new int[2];

for (int i = 0; i < _length; i++)
{
    _input = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);
    _xList.Add(_input[0]);
    _yList.Add(_input[1]);
}

_xList.Sort();
_yList.Sort();

Console.WriteLine((_xList[_xList.Count - 1] - _xList[0]) * (_yList[_yList.Count - 1] - _yList[0]));
```