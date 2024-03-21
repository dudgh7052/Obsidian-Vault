---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2204
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
List<string> _list = new List<String>();

while (true)
{
    int N = int.Parse(Console.ReadLine());
    if (N == 0) break;

    _list.Clear();

    for (int i = 0; i < N; i++)
    {
        _list.Add(Console.ReadLine());
    }

    // OrdinalIgnoreCase를 통해 대소문자 구별없이 정렬(Ordinal은 대소문자 구별)
    _list.Sort(StringComparer.OrdinalIgnoreCase);

    _result.AppendLine(_list[0]);
}

Console.WriteLine(_result.ToString());
```