---
tags:
  - Baekjoon
  - Greedy
  - Sort
---
https://www.acmicpc.net/problem/1758
```C#
List<int> _list = new List<int>();
long _totalTip = 0;

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    _list.Add(int.Parse(Console.ReadLine()));
}

_list.Sort();
_list.Reverse();

for (int i = 0; i < _list.Count; i++)
{
    _list[i] -= i;
    if (_list[i] > 0) _totalTip += _list[i];
}

Console.WriteLine(_totalTip);
```