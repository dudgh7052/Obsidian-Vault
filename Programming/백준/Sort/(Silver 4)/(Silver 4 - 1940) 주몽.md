---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/1940
- Hashset에 M - 값을 해주면서 짝 찾기
```C#
int N = int.Parse(Console.ReadLine());
int M = int.Parse(Console.ReadLine());
List<int> _list = Console.ReadLine().Split().Select(int.Parse).ToList();
HashSet<int> _hashset = new HashSet<int>();
int _result = 0;

foreach (int _value in _list)
{
    if (_hashset.Contains(_value)) _result++;
    else _hashset.Add(M - _value);
}

Console.WriteLine(_result);
```