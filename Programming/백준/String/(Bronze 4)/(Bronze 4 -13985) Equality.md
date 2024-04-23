---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/13985
```C#
char[] _split = { '+', '=' };
int[] _list = Console.ReadLine().Split(_split).Select(int.Parse).ToArray();

if (_list[0] + _list[1] == _list[2]) Console.WriteLine("YES");
else Console.WriteLine("NO");
```