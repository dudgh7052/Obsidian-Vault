---
tags:
  - Baekjoon
  - 브루트포스
---
https://www.acmicpc.net/problem/1977
```C#
int M = int.Parse(Console.ReadLine());
int N = int.Parse(Console.ReadLine());

int _sum = 0;
int _min = 0;

for (int i = N; i >= M; i--)
{
    for (int j = 1; j <= i; j++)
    {
        if (i == j * j)
        {
            _sum += i;
            _min = i;
            break;
        }
    }
}

if (_sum == 0)
{
    Console.WriteLine(-1);
}
else
{
    Console.WriteLine($"{_sum}\n{_min}");
}
```