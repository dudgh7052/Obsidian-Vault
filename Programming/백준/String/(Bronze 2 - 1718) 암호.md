---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1718
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

string _input = Console.ReadLine();

string _password = Console.ReadLine();
int[] _values = new int[_password.Length];
for (int i = 0; i < _password.Length; i++)
{
    _values[i] = _password[i] - 96;
}

for (int i = 0; i < _input.Length; i++)
{
    if (_input[i] == ' ') 
    {
        _result.Append(' ');
        continue;
    }

    int _sum = _input[i] - _values[i % _values.Length];

    if (_sum < 97) _sum += 26; 

    _result.Append((char)_sum);
}

Console.WriteLine(_result);
```