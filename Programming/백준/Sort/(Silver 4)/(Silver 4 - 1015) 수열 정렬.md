---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/1015
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

List<int> _list = new List<int>();

int N = int.Parse(Console.ReadLine());
_list.AddRange(Console.ReadLine().Split().Select(int.Parse));

var _sorted = _list.OrderBy(x => x).ToList();

foreach (int value in _list)
{
    int _index = _sorted.IndexOf(value);
    _sorted[_index] = 1001;
    _result.AppendFormat("{0} ", _index);
}

Console.WriteLine(_result);
```