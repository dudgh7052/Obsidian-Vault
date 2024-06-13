---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/1431
```C#
var _dic = new Dictionary<string, int>();

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    string _input = Console.ReadLine();

    int _sum = 0;
    foreach(char _value in _input)
    {
        if (char.IsDigit(_value)) _sum += _value - 48;
    }

    _dic.Add(_input, _sum);
}

var _sorted = _dic.OrderBy(x => x.Key.Length).ThenBy(x => x.Value).ThenBy(x => x.Key).ToList();
foreach(var _element in _sorted)
{
    Console.WriteLine(_element.Key);
}
```