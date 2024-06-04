---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/11004
```C#
int[] NK = Console.ReadLine().Split().Select(int.Parse).ToArray();
int[] _arr = Console.ReadLine().Split().Select(int.Parse).ToArray();
Array.Sort(_arr);
Console.WriteLine(_arr[NK[1] - 1]);
```