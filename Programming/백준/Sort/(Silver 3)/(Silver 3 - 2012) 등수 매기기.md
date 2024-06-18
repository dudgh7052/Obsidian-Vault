---
tags:
  - Baekjoon
  - Sort
  - Greedy
---
https://www.acmicpc.net/problem/2012
```C#
List<int> _list = new List<int>();
long _result = 0;

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    _list.Add(int.Parse(Console.ReadLine()));
}

_list.Sort();

int _nowCount = 1;
foreach (int value in _list)
{
    _result += Math.Abs(_nowCount - value);
    _nowCount++;
}

Console.WriteLine(_result);
```