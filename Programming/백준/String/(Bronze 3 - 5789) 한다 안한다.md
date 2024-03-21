---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5789
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();

    bool _sameFlag = false;
    int _half = _input.Length / 2;

    _sameFlag = _input[_half - 1] == _input[_half];

    _result.AppendLine(_sameFlag == true ? "Do-it" : "Do-it-Not");
}

Console.WriteLine(_result);
```