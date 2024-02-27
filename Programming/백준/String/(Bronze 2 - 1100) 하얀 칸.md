---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1100
```C#
// 0 2 4 6 
// 1 3 5 8
// 0 2 4 6
using System.Text;

StringBuilder _sb = new StringBuilder();
int _count = 0;

bool _isEven = true;
for (int i = 0; i < 8; i++)
{
    _sb.Append(Console.ReadLine());

    if (_isEven)
    {
        for (int j = 0; j < _sb.Length; j += 2)
        {
            if (_sb[j].ToString() == "F")
            {
                _count++;
            }
        }
    }
    else
    {
        for (int j = 1; j < _sb.Length; j += 2)
        {
            if (_sb[j].ToString() == "F")
            {
                _count++;
            }
        }
    }

    _isEven = !_isEven;
    _sb.Clear();
}

Console.WriteLine(_count);
```