---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/11367
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string[] _input = Console.ReadLine().Split();

    _result.AppendFormat("{0} {1}\n", _input[0], Check(int.Parse(_input[1])));
}

Console.WriteLine(_result);

string Check(int argScore)
{
    return argScore switch
    {
        int value when value >= 97 => "A+",
        int value when value >= 90 => "A",
        int value when value >= 87 => "B+",
        int value when value >= 80 => "B",
        int value when value >= 77 => "C+",
        int value when value >= 70 => "C",
        int value when value >= 67 => "D+",
        int value when value >= 60 => "D",
        _ => "F"
    };
}
```