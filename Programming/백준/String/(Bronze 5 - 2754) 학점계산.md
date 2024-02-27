---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2754
```C#
using System.Collections.Generic;

Dictionary<string, float> _scoreDictionary = new Dictionary<string, float>()
{
    { "A+", 4.3f }, { "A0", 4.0f }, { "A-", 3.7f },
    { "B+", 3.3f }, { "B0", 3.0f }, { "B-", 2.7f },
    { "C+", 2.3f }, { "C0", 2.0f }, { "C-", 1.7f },
    { "D+", 1.3f }, { "D0", 1.0f }, { "D-", 0.7f }, { "F", 0.0f }
};

string _input = Console.ReadLine();
Console.WriteLine("{0:F1}", _scoreDictionary[_input]);
```