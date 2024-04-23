---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/15904
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

char[] _array = { 'U', 'C', 'P', 'C' };
bool _flag = true;

_sb.Append(Console.ReadLine());

foreach(char value in _array)
{
    string _tmpStr = _sb.ToString();
    int _index = _tmpStr.IndexOf(value);
    if (_index != -1)
    {
        _sb.Clear();
        _sb.Append(_tmpStr.Substring(_index + 1));
        continue;
    }

    _flag = false;
    break;
}

Console.WriteLine(_flag == true ? "I love UCPC" : "I hate UCPC");
```