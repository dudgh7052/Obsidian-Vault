---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/1269
```C#
int _count = 0;

int[] AB = Console.ReadLine().Split().Select(int.Parse).ToArray();
var _aDic = new Dictionary<string, int>();
var _bDic = new Dictionary<string, int>();

foreach (string value in Console.ReadLine().Split())
{
    _aDic.Add(value, 1);
}

foreach (string value in Console.ReadLine().Split())
{
    _bDic.Add(value, 1);
}

foreach (var element in _aDic)
{
    if (!_bDic.ContainsKey(element.Key)) _count++;
}

foreach (var element in _bDic)
{
    if (!_aDic.ContainsKey(element.Key)) _count++;
}

Console.WriteLine(_count);
```