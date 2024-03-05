---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2857
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

for (int i = 0; i < 5; i++)
{
    if (Console.ReadLine().Contains("FBI"))
    {
        _sb.Append(i + 1);
        _sb.Append(" ");
    }
}

if (_sb.Length != 0)
{
    Console.WriteLine(_sb);
}
else
{
    Console.WriteLine("HE GOT AWAY!");
}
```