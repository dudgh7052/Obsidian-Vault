---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2954
```C#
// a, e, i, o, u 모음이 나오면 뒤 2글자 건너뛰기
using System.Text;

StringBuilder _result = new StringBuilder();

string _input = Console.ReadLine();

for (int i = 0; i < _input.Length; i++)
{
    _result.Append(_input[i]);

    if (_input[i] == 'a' || _input[i] == 'e' || _input[i] == 'i' || _input[i] == 'o' || _input[i] == 'u')
    {
        i += 2;
    }
}

Console.WriteLine(_result);
```