---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/18409
```C#
int N = int.Parse(Console.ReadLine());
string _input = Console.ReadLine();
int _count = 0;

for (int i = 0; i < N; i++)
{
    if (_input[i] == 'a' || _input[i] == 'i' || _input[i] == 'u' || _input[i] == 'e' || _input[i] == 'o')
    {
        _count++;
    }
}

Console.WriteLine(_count);
```