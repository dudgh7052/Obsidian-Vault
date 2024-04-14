---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/6550
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
StringBuilder _sb = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine();
    int _index = 0;

    if (_input == null) break;

    string[] _split = _input.Split();

    foreach (char value in _split[1])
    {
        if (value != _split[0][_index]) continue;

        _sb.Append(value);
        _index++;

        if (_index == _split[0].Length) break;
    }

    _result.AppendLine(_sb.ToString() == _split[0] ? "Yes" : "No");

    _sb.Clear();
}

Console.WriteLine(_result);
```