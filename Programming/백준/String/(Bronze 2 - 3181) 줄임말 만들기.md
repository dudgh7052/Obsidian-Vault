---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/3181
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
string[] _pattern = { "i", "pa", "te", "ni", "niti", "a", "ali", "nego", "no", "ili" };

string[] _splitStr = Console.ReadLine().Split();

Abbreviation(_splitStr[0]);
for (int i = 1; i < _splitStr.Length; i++)
{
    if (_pattern.Contains(_splitStr[i])) continue;

    Abbreviation(_splitStr[i]);
}

Console.WriteLine(_result);

void Abbreviation(string argStr)
{
    _result.Append((char)(argStr[0] - 32));
}
```