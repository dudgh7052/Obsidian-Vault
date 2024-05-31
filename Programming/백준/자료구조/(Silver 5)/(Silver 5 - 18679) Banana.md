---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/18679
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
var _dic = new Dictionary<string, string>();

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    string[] _input = Console.ReadLine().Split();
    _dic.Add(_input[0], _input[2]);
}

int T = int.Parse(Console.ReadLine());
while(T-- > 0)
{
    int K = int.Parse(Console.ReadLine());
    string[] _input = Console.ReadLine().Split();
    foreach(string _word in _input)
    {
        _result.AppendFormat("{0} ", _dic[_word]);
    }

    _result.AppendLine();
}

Console.WriteLine(_result);
```