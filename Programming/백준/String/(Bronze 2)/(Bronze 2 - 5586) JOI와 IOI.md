---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5586
```C#
string _input = Console.ReadLine();
string _joi = "JOI";
string _ioi = "IOI";
int _joiCount = 0;
int _ioiCount = 0;

for (int i = 0; i < _input.Length - 2; i++)
{
    if (_input[i] == 'J' && _input[i + 1] == 'O' && _input[i + 2] == 'I')
    {
        _joiCount++;
    }
    else if (_input[i] == 'I' && _input[i + 1] == 'O' && _input[i + 2] == 'I')
    {
        _ioiCount++;
    }
}

Console.WriteLine(string.Format("{0}\n{1}", _joiCount, _ioiCount));
```