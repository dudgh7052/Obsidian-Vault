---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2902
```C#
// -로 Split() 해주기
// 각 요소별 첫번째만 StringBuilder에 넣어주기
using System.Text;

StringBuilder _sb = new StringBuilder();

string[] _str = Console.ReadLine().Split('-').ToArray();

for (int i = 0; i < _str.Length; i++)
{
    _sb.Append(_str[i][0]);
}

Console.WriteLine(_sb);
```