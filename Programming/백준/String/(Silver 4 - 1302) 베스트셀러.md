---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1302
```C#
var _dic = new Dictionary<string, int>();
List<string> _list = new List<string>();

int N = int.Parse(Console.ReadLine());
while (N-- > 0)
{
    string _title = Console.ReadLine();

    if (_dic.ContainsKey(_title))
    {
        _dic[_title]++;
    }
    else _dic.Add(_title, 1);
}

int _maxValue = _dic.Values.Max();
foreach (KeyValuePair<string, int> value in _dic)
{
    if (value.Value < _maxValue) continue;

    _list.Add(value.Key);
}

_list.Sort();

Console.WriteLine(_list[0]);
```