---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/8949
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

string[] _input = Console.ReadLine().Split();
string _first = _input[0];
string _second = _input[1];

Stack<int> _queue =new Stack<int>();
int _firstIndex = _first.Length - 1;
int _secondIndex = _second.Length - 1;

while (_firstIndex >= 0 || _secondIndex >= 0)
{
    int _sum = 0;
    _sum += _firstIndex >= 0 ? (_first[_firstIndex] - 48) : 0;
    _sum += _secondIndex >= 0 ? (_second[_secondIndex] - 48) : 0;

    _queue.Push(_sum);

    _firstIndex--;
    _secondIndex--;
}

foreach (int value in _queue)
{
    _result.Append(value);
}

Console.WriteLine(_result);
```