---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/4358
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

var _dic = new Dictionary<string, int>();

int _count = 0;

while (true)
{
    string _input = Console.ReadLine();

    if (_input == null) break;

    if (!_dic.ContainsKey(_input))
    {
        _dic.Add(_input, 1);
    }
    else _dic[_input]++;

    _count++;
}

var _list = _dic.OrderBy(x => x.Key).ToList();

foreach (KeyValuePair<string, int> value in _list)
{
    _result.AppendFormat("{0} {1:f4}\n", value.Key, (float)value.Value / _count * 100);
}

Console.WriteLine(_result);
```