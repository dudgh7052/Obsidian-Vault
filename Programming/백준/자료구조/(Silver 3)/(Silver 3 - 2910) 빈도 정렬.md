---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/2910
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
var _dic = new Dictionary<string, int>();

int[] NC = Console.ReadLine().Split().Select(int.Parse).ToArray();

string[] _split = Console.ReadLine().Split();
foreach(string value in _split)
{
    if (_dic.ContainsKey(value))
    {
        _dic[value]++;
    }
    else _dic.Add(value, 1);
}

var _list = _dic.OrderByDescending(x => x.Value).ToList();

foreach (KeyValuePair<string, int> element in _list)
{
    for(int i = 0; i < element.Value; i++)
    {
        _result.AppendFormat("{0} ", element.Key);
    }
}

Console.WriteLine(_result);
```