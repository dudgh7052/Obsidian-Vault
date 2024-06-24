---
tags:
  - Baekjoon
  - Greedy
  - Sort
---
https://www.acmicpc.net/problem/12018
```C#
List<int> _list = new List<int>();

int[] _NM = Console.ReadLine().Split().Select(int.Parse).ToArray();
int _count = _NM[0];
int _totalPoint = _NM[1];
int _result = 0;

while (_count-- > 0)
{
    string[] _PL = Console.ReadLine().Split();
    int P = int.Parse(_PL[0]);
    int L = int.Parse(_PL[1]);
    int[] _points = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);

    int _sub = P - L;
    if (_sub < 0) 
    {
        _list.Add(1);
        continue;
    } 

    Array.Sort(_points);
    _list.Add(_points[_sub]);
}

_list.Sort();

foreach (int value in _list)
{
    _totalPoint -= value;

    if (_totalPoint < 0) break;

    _result++;
}

Console.WriteLine(_result);
```