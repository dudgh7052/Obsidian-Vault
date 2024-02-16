---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/5585
```C#
int[] _coins = { 500, 100, 50, 10, 5, 1 };

int _price = int.Parse(Console.ReadLine());
int _remain = 1000 - _price;
int _count = 0;

for (int i = 0; i < _coins.Length; i++)
{
    if (_coins[i] > _remain) continue;

    _count += _remain / _coins[i];
    _remain -= (_remain / _coins[i]) * _coins[i];

    if (_remain == 0) break;
}

Console.WriteLine(_count);
```