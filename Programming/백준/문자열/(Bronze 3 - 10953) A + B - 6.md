---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/10953
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();
StringBuilder _result = new StringBuilder();

int T = int.Parse(Console.ReadLine());
int[] _array = new int[2];

for (int i = 0; i < T; i++)
{
    _sb.Append(Console.ReadLine());
    _array = _sb.ToString().Split(',').Select(x => int.Parse(x)).ToArray();

    _result.AppendFormat("{0}\n", _array[0] + _array[1]);

    _sb.Clear();
}

Console.WriteLine(_result);
```