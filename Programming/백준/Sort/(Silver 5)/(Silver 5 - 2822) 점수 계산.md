---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/2822
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
var _dic = new Dictionary<int, int>();
SortedSet<int> _indexList = new SortedSet<int>();
int _sum = 0;

for(int i = 1; i <= 8; i++)
{
    int _score = int.Parse(Console.ReadLine());

    _dic.Add(i, _score);
}

var _list = _dic.OrderByDescending(x => x.Value).ToList();

int _count = 0;
foreach (var element in _list)
{
    _sum += element.Value;
    _indexList.Add(element.Key);

    _count++;
    if (_count == 5) break;
}

Console.WriteLine("{0}\n{1}", _sum, string.Join(' ', _indexList));
```