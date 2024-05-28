---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/11645
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
var _dic = new Dictionary<string, int>();

int T = int.Parse(Console.ReadLine());
while (T-- > 0)
{
    int N = int.Parse(Console.ReadLine());

    for (int i = 0; i < N; i++)
    {
        string _input = Console.ReadLine();
        if (!_dic.ContainsKey(_input)) _dic.Add(_input, 1);
    }

    _result.AppendLine(_dic.Count.ToString());
    _dic.Clear();
}

Console.WriteLine(_result);
```