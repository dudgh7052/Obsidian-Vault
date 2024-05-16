---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/1270
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
var _dic = new Dictionary<string, int>();

int n = int.Parse(Console.ReadLine());
while(n-- > 0)
{
    string[] _input = Console.ReadLine().Split();

    for (int i = 1; i < _input.Length; i++)
    {
        if (_dic.ContainsKey(_input[i])) _dic[_input[i]]++;
        else _dic.Add(_input[i], 1);
    }

    bool _flag = false;
    int _half = (_input.Length - 1) / 2;
    foreach(KeyValuePair<string, int> element in _dic)
    {
        if (element.Value > _half)
        {
            _flag = true;
            _result.AppendLine(element.Key);
            break;
        }
    }

    if (!_flag) _result.AppendLine("SYJKGW");

    _dic.Clear();
}

Console.WriteLine(_result);
```