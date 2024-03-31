---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/7600
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine().ToUpper();
    int[] _array = new int[26];

    if (_input == "#") break;

    foreach (char _char in _input)
    {
        if (!char.IsLetter(_char)) continue;

        _array[_char - 65]++;
    }

    _result.AppendLine(Count(_array).ToString());
}

Console.WriteLine(_result);

int Count(int[] argArray)
{
    int _count = 0;

    foreach (int value in argArray)
    {
        if (value > 0) _count++; 
    }

    return _count;
} 
```