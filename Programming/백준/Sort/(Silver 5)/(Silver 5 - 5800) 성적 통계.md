---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/5800
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int K = int.Parse(Console.ReadLine());
for(int i = 1; i <= K; i++)
{
    _result.AppendFormat("Class {0}\n", i);

    List<int> _list = Console.ReadLine().Split().Select(int.Parse).ToList();
    _list.RemoveAt(0);

    _list.Sort();
    _list.Reverse();

    int _min = _list[_list.Count - 1];
    int _max = _list[0];
    int _gap = 0;
    for (int j = 0; j < _list.Count - 1; j++)
    {
        int _temp = _list[j] - _list[j + 1];
        if (_temp > _gap) _gap = _temp;
    }

    _result.AppendFormat("Max {0}, Min {1}, Largest gap {2}\n", _max, _min, _gap);
}

Console.WriteLine(_result);
```