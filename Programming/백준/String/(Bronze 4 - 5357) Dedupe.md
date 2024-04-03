---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5357
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();
    AppendInput(_input);
}

Console.WriteLine(_result);

void AppendInput (string argStr)
{
    char _lastChar = default;
    StringBuilder _sb = new StringBuilder();

    foreach (char value in argStr)
    {
        if (_lastChar != value)
        {
            _lastChar = value;
            _sb.Append(value);
        }
    }

    _result.AppendLine(_sb.ToString());
}
```