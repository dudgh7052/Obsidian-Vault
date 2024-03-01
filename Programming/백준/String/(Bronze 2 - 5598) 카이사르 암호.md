---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5598
```C#
char[] _input = Console.ReadLine().ToCharArray();

for (int i = 0; i < _input.Length; i++)
{

    if (_input[i] < 68) // A, B, C일 경우
    {
        _input[i] = (char)(_input[i] + 23);
    }
    else
    {
        _input[i] = (char)(_input[i] - 3);
    }
}

Console.WriteLine(new string(_input));
```