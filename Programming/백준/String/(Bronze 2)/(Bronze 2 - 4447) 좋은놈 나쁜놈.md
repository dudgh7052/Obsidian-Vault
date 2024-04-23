---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/4447
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
string _input = string.Empty;

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    _input = Console.ReadLine();
    _result.AppendFormat("{0} {1}\n", _input, Check());
}

Console.WriteLine(_result);

int Count(char argFoundChar)
{
    char[] _chars = _input.ToLower().ToCharArray();
    return _chars.Count(x => x == argFoundChar);
}

string Check()
{
    int _count = Count('g');
    return _count switch
    {
        int value when value > Count('b') => "is GOOD",
        int value when value < Count('b') => "is A BADDY",
        int value when value == Count('b') => "is NEUTRAL",
    };
}
```