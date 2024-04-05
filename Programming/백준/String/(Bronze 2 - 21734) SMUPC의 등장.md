---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/21734
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

string _input = Console.ReadLine();
for (int i = 0; i < _input.Length; i++)
{
    int _count = Sum(_input[i]);
    AppendCount(_input[i], _count);
}

Console.WriteLine(_result);

void AppendCount(char argChar, int argCount)
{
    for (int i = 0; i < argCount; i++)
    {
        _result.Append(argChar);
    }

    _result.AppendLine();
}

int Sum(char argChar)
{
    int _sum = 0;
    int _value = argChar;   

    while (_value > 0)
    {
        _sum += _value % 10;
        _value /= 10;
    }

    return _sum;
}
```