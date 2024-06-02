---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/11235
```C#
var _dic = new Dictionary<string, int>();

int n = int.Parse(Console.ReadLine());
while (n-- > 0)
{
    string _input = Console.ReadLine();

    if (_dic.ContainsKey(_input)) _dic[_input]++;
    else _dic.Add(_input, 1);
}

int _maxValue = _dic.Values.Max();
var _list = _dic.OrderBy(x => x.Key).OrderByDescending(x => x.Value).ToList();

foreach(var element in _list)
{
    if (element.Value != _maxValue) break;

    Console.WriteLine(element.Key);
}
```