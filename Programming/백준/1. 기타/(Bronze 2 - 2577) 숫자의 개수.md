---
tags:
  - Baekjoon
---
https://www.acmicpc.net/problem/2577
```C#
int[] _array = new int[3];
int _sum = 0;
int[] _count = new int[10];

for (int i = 0; i < 3; i++)
{
    _array[i] = int.Parse(Console.ReadLine());
}

_sum = _array[0] * _array[1] * _array[2];

while (_sum != 0)
{
    int _index = _sum % 10;
    _count[_index] = _count[_index] + 1;
    _sum /= 10;
}

foreach (int i in _count)
{
    Console.WriteLine(i);
}
```