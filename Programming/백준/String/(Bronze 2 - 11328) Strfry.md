---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/11328
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();
string[] _input = new string[2];
bool _isPossible = true;

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    Check();
    _isPossible = true;
}

Console.WriteLine(_sb);

void Check()
{
    char[] _chars = new char[26];
    _input = Console.ReadLine().Split();
    if (_input[0].Length != _input[1].Length)
    {
        _sb.AppendLine("Impossible");
        return;
    }

    if (_input[0] == _input[1])
    {
        _sb.AppendLine("Possible");
        return;
    }

    for (int j = 0; j < _input[0].Length; j++)
    {
        _chars[_input[0][j] - 97]++;
    }

    for (int j = 0; j < _input[1].Length; j++)
    {
        _chars[_input[1][j] - 97]--;
    }

    for (int j = 0; j < _chars.Length; j++)
    {
        if (_chars[j] != 0)
        {
            _isPossible = false;
            break;
        }
    }

    if (_isPossible) _sb.AppendLine("Possible");
    else _sb.AppendLine("Impossible");
}
```