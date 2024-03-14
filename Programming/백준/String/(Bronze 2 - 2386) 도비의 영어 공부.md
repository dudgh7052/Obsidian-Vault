---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2386
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine().ToLower();
    if (_input == "#") break;

    _result.AppendFormat("{0} {1}\n", _input[0], GetCharCount(_input));
}

Console.WriteLine(_result);


int GetCharCount(string argStr)
{
    int _count = 0;

    foreach (char _char in argStr.Substring(2))
    {
        if (_char == argStr[0]) _count++;
    }

    return _count;
}
```