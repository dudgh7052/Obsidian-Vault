---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5704
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine();
    char[] _char = new char[26];
    bool _flag = true;

    if (_input == "*") break;

    foreach (char value in _input)
    {
        if (value == ' ') continue;

        _char[value - 97]++;
    }

    for (int i = 0; i < _char.Length; i++)
    {
        if (_char[i] == 0)
        {
            _flag = false;
            break;
        }
    }

    _result.AppendLine(_flag == true ? "Y" : "N");
}

Console.WriteLine(_result.ToString());
```