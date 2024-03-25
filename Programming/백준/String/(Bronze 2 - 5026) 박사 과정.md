---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5026
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());

for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();

    if (_input == "P=NP") _result.AppendLine("skipped");
    else
    {
        string[] _splitStr = _input.Split('+');
        _result.AppendLine((int.Parse(_splitStr[0]) + int.Parse(_splitStr[1])).ToString());
    }
}

Console.WriteLine(_result.ToString());
```