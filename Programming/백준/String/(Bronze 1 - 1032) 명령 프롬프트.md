---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1032
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

List<string> _list = new List<string>();
char _nowChar = default;
bool _IsSame = true;

int N = int.Parse(Console.ReadLine());

for (int i = 0; i < N; i++)
{
    _list.Add(Console.ReadLine());
}

for (int i = 0; i < _list[0].Length; i++)
{
    _IsSame = true;

    _nowChar = _list[0][i];

    for (int j = 1; j < _list.Count; j++)
    {
        if (_list[j][i] == _nowChar) continue;

        _IsSame = false;
    }

    if (_IsSame)
    {
        _sb.Append(_nowChar);
    }
    else
    {
        _sb.Append('?');
    }
}

Console.WriteLine(_sb);
```