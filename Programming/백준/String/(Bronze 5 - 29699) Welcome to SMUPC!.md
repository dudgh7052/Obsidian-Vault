---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/29699
```C#
string _input = "WelcomeToSMUPC";

int N = int.Parse(Console.ReadLine());

int _index = ((N - 1) % _input.Length);
Console.WriteLine(_input[_index]);
```