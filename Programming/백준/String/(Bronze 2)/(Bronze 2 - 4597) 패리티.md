---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/4597
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine();

    if (_input == "#") break;

    bool _isEven = _input[_input.Length - 1] == 'e' ? true : false;
    int _count = 0;

    foreach (char c in _input)
    {
        if (c == '1') _count++;
    }

    string _subStr = _input.Substring(0, _input.Length - 1);

    if (_isEven)
    {
        if (_count % 2 == 0) _result.AppendLine(_subStr + "0");
        else _result.AppendLine(_subStr + "1");
    }
    else
    {
        if (_count % 2 == 0) _result.AppendLine(_subStr + "1");
        else _result.AppendLine(_subStr + "0");
    }
}

Console.WriteLine(_result);
```