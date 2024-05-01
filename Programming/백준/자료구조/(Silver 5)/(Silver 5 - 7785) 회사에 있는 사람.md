---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/7785
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

var _dic = new Dictionary<string, int>();
List<string> _list = new List<string>();

int n = int.Parse(Console.ReadLine());
while(n-- > 0)
{
    string[] _split = Console.ReadLine().Split();

    if (_dic.ContainsKey(_split[0]))
    {
        _dic[_split[0]] += _split[1] == "enter" ? 1 : -1; 
    }
    else
    {
        _dic.Add(_split[0], _split[1] == "enter" ? 1 : -1);
    }
}

foreach(KeyValuePair<string,int> item in _dic)
{
    if (item.Value > 0) _list.Add(item.Key);
}

_list.Sort();
_list.Reverse();

foreach(string value in _list)
{
    _result.AppendLine(value);
}

Console.WriteLine(_result);
```