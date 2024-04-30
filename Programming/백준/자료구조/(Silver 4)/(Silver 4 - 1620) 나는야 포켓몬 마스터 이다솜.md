---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/1620
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

var _dic1 = new Dictionary<string, int>();
var _dic2 = new Dictionary<int, string>();

int[] _split = Console.ReadLine().Split().Select(int.Parse).ToArray();
for (int i = 1; i <= _split[0]; i++)
{
    string _pokemon = Console.ReadLine();
    _dic1.Add(_pokemon, i);
    _dic2.Add(i, _pokemon);
}

while (_split[1]-- > 0)
{
    string _input = Console.ReadLine();

    if (char.IsLetter(_input[0])) { _result.AppendLine(_dic1[_input].ToString()); }
    else { _result.AppendLine(_dic2[int.Parse(_input)].ToString()); }
}

Console.WriteLine(_result);
```