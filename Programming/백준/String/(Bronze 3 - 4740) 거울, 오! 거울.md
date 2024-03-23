---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/4740
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine();

    if (_input == "***") break;

    _result.AppendLine(Reverse(_input));
}

Console.WriteLine(_result);

// Array.Reverse() 활용
string Reverse(string argStr)
{
    char[] _charArray = argStr.ToCharArray();
    Array.Reverse(_charArray);

    return new string(_charArray);
}

// IEnumeable.Reverse() 활용
string Reverse(string argStr)
{
    return new string(argStr.Reverse().ToArray());
}

// StringBuilder 활용
string Reverse(string argStr)
{
    StringBuilder _sb = new StringBuilder();

    for (int i = argStr.Length - 1; i >= 0; i--)
    {
        _sb.Append(argStr[i]);
    }

    return _sb.ToString();
}
```