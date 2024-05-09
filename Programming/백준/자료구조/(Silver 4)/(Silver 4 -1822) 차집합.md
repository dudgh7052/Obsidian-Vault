---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/1822
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

var _dic = new Dictionary<int, int>();
var _list = new List<int>();

int[] NN = Console.ReadLine().Split().Select(int.Parse).ToArray();

int[] _aInput = Console.ReadLine().Split().Select(int.Parse).ToArray();
int[] _bInput = Console.ReadLine().Split().Select(int.Parse).ToArray();
foreach (int key in _bInput)
{
    _dic.Add(key, 1);
}

foreach(int key in _aInput)
{
    if (!_dic.ContainsKey(key))
    {
        _list.Add(key);
    }
}

if (_list.Count == 0)
{
    Console.WriteLine("0");
    return;
}

_list.Sort();

foreach (int key in _list)
{
    _result.AppendFormat("{0} ", key);
}

Console.WriteLine("{0}\n{1}", _list.Count, _result);
```