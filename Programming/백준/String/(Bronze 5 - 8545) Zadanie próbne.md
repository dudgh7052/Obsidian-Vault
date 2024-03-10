---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/8545
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

string _input = Console.ReadLine();

for (int i = _input.Length - 1; i >= 0; i--)
{
    _sb.Append(_input[i]);
}

Console.WriteLine(_sb);
```