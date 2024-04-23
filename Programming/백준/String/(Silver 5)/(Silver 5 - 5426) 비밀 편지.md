---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5426
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();

    int _count = (int)Math.Sqrt(_input.Length); // 제곱근 반환
    Password(_input, _count);
}

Console.WriteLine(_result);

void Password(string argPassword, int argCount)
{
    for (int i = argCount - 1; i >= 0; i--)
    {
        for (int j = i; j < argPassword.Length; j += argCount)
        {
            _sb.Append(argPassword[j]);
        }
    }

    _result.AppendLine(_sb.ToString());
    _sb.Clear();
}
```