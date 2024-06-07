---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/2693
```C#
int T = int.Parse(Console.ReadLine());
while(T-- > 0)
{
    int[] _arr = Console.ReadLine().Split().Select(int.Parse).OrderBy(x => x).ToArray();
    Console.WriteLine(_arr[_arr.Length - 3]);
}
```