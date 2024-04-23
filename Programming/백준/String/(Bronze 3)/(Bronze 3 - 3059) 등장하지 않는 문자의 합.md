---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/3059
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int T = int.Parse(Console.ReadLine());
int _sum = 0;

for (int i = 0; i < T; i++)
{
    string _input = Console.ReadLine();

    for (int j = 65; j < 91; j++)
    {
        if (!_input.Contains((char)j))
        {
            _sum += j;
        }
    }

    _sb.AppendLine(_sum.ToString());
    _sum = 0;
}

Console.WriteLine(_sb);
```