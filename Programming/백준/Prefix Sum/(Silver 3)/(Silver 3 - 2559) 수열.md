---
tags:
  - Baekjoon
  - PrefixSum
---
https://www.acmicpc.net/problem/2559
```C#
int[] _NK = Console.ReadLine().Split().Select(int.Parse).ToArray();
int[] _arr = Console.ReadLine().Split().Select(int.Parse).ToArray();
List<int> _list = new List<int>() { _arr[0] };
for (int i = 1; i < _arr.Length; i++)
{
    _list.Add(_list.Last() + _arr[i]);
}

int _max = _list[_NK[1] - 1];
for (int i = 1; i <= _list.Count -_NK[1]; i++)
{
    _max = Math.Max(_max, _list[i + _NK[1] - 1] - _list[i - 1]);
}

Console.WriteLine(_max);
```