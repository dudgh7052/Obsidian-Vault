---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/9612
```C#
using System.Xml.Schema;

Dictionary<string, int> _dic = new Dictionary<string, int>();

int n = int.Parse(Console.ReadLine());
while (n-- > 0)
{
    string _input = Console.ReadLine();

    if (_dic.ContainsKey(_input)) _dic[_input]++;
    else _dic.Add(_input, 1);
}

int _maxValue = _dic.Values.Max();
var _list = _dic.OrderByDescending(x => x.Value).OrderByDescending(x => x.Key);

Console.WriteLine("{0} {1}", _list.First().Key, _list.First().Value);
```