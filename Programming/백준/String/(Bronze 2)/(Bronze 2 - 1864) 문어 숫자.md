---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1864
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int _sum = 0;
int _index = 0;

while (true)
{
    string _input = Console.ReadLine();
    _sum = 0;
    _index = _input.Length - 1;

    if (_input == "#") break;

    for (int i = 0; i < _input.Length; i++)
    {
        if (_index > 0) _sum += GetValue(_input[i]) * (int)MathF.Pow(8, _index);
        else _sum += GetValue(_input[i]);
        _index--;
    }

    _result.AppendLine(_sum.ToString());
}

Console.WriteLine(_result);

int GetValue(char argChar)
{
    int _value = 0;

    switch (argChar)
    {
        case '-':
            _value = 0;
            break;
        case '\\':
            _value = 1;
            break;
        case '(':
            _value = 2;
            break;
        case '@':
            _value = 3;
            break;
        case '?':
            _value = 4;
            break;
        case '>':
            _value = 5;
            break;
        case '&':
            _value = 6;
            break;
        case '%':
            _value = 7;
            break;
        case '/':
            _value = -1;
            break;
    }

    return _value; 
}
```