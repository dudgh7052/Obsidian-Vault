---
tags:
  - Baekjoon
  - Sort
---
https://www.acmicpc.net/problem/2587
```C#
List<int> _list = new List<int>();
int _sum = 0;
int _value = 0;

for (int i = 0; i < 5; i++)
{
    _value = int.Parse(Console.ReadLine());
    _list.Add(_value);

    _sum += _value;
}

_list.Sort();

Console.WriteLine(_sum / 5);
Console.WriteLine(_list[2]);
```