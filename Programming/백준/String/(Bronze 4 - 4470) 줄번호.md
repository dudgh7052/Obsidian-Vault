---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/4470
- StringBuilder의 AppendFormat() 이용해서 형식에 맞게 저장 후 출력
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 1; i <= N; i++)
{
    _sb.AppendFormat("{0}. {1}\n", i, Console.ReadLine());
}

Console.WriteLine(_sb);
```