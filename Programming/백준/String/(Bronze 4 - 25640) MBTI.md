---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/25640
```C#
string _input = Console.ReadLine();
int N = int.Parse(Console.ReadLine());
int _count = 0;

for (int i = 0; i < N; i++)
{
    string _friendMbti = Console.ReadLine();
    if (_input != _friendMbti) continue;

    _count++;
}

Console.WriteLine(_count);
```