---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/2776
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
HashSet<string> _hashSet = new HashSet<string>();

int T = int.Parse(Console.ReadLine());
while (T-- > 0)
{
    int N = int.Parse(Console.ReadLine());
    string[] _nValues = Console.ReadLine().Split();
    foreach(string value in _nValues)
    {
        _hashSet.Add(value);
    }

    int M = int.Parse(Console.ReadLine());
    string[] _mValues = Console.ReadLine().Split();
    foreach(string value in _mValues)
    {
        _result.AppendFormat(_hashSet.Contains(value) ? "1\n" : "0\n");
    }

    _hashSet.Clear();
}

Console.WriteLine(_result);
```