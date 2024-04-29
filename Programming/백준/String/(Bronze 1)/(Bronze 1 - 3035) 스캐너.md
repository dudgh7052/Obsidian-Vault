---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/3035
```C#
using System.Text;

int[] _split = Console.ReadLine().Split().Select(int.Parse).ToArray();

var _list = new List<string>();
var _tmpList = new List<string>();

StringBuilder _result = new StringBuilder();

for(int i = 0; i < _split[0]; i++)
{
    _list.Add(Console.ReadLine());
}

foreach(string value in _list)
{
    for (int i = 0; i < _split[2]; i++)
    {
        _tmpList.Add(value);
    }
}

foreach (string value in _tmpList)
{
    for (int i = 0; i < value.Length; i++)
    {
        for (int j = 0; j < _split[3]; j++)
        {
            _result.Append(value[i]);
        }
    }

    _result.AppendFormat("\n");
}

Console.WriteLine(_result.ToString());
```