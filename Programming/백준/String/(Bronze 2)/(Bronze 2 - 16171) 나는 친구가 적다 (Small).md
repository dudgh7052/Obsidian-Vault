---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/16171
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

string _input = Console.ReadLine();
string _word = Console.ReadLine();

foreach (char value in _input)
{
    if (char.IsLetter(value)) _sb.Append(value);
}

Console.WriteLine(_sb.ToString().Contains(_word) ? 1 : 0);
```