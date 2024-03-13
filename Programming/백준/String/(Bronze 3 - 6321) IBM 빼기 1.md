---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/6321
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 1; i <= N; i++)
{
    string _input = Console.ReadLine();
    _result.AppendFormat("String #{0:D}\n{1}\n\n", i, PushStr(_input));
}

Console.WriteLine(_result);

string PushStr(string argStr)
{
    StringBuilder _sb = new StringBuilder();

    for (int i = 0; i < argStr.Length; i++)
    {
        if (argStr[i] < 'Z')
        {
            _sb.Append((char)(argStr[i] + 1));
        }
        else _sb.Append('A');
    }

    return _sb.ToString();
}
```