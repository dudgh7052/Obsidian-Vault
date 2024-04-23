---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5524
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();
int N = int.Parse(Console.ReadLine());

for (int i = 0; i < N; i++)
{
    _sb.AppendLine(Console.ReadLine().ToString().ToLower());
}

Console.WriteLine(_sb.ToString());
```