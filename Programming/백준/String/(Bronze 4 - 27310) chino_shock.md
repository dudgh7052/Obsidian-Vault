---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/27310
```C#
List<char> _list = Console.ReadLine().ToCharArray().ToList();

int _sum = _list.Count + Count(':') + Count('_') * 5;

Console.WriteLine(_sum);

int Count(char argChar)
{
    return _list.Count(x => x == argChar);
}
```