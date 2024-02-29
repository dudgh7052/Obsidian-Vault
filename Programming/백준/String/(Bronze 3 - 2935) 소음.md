---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2935
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

char[] A = Console.ReadLine().ToCharArray();
char _char = char.Parse(Console.ReadLine());
char[] B = Console.ReadLine().ToCharArray();

switch (_char)
{
    case '+':
        if (A.Length == B.Length)
        {
            A[0] = '2';
            _sb.Append(new string(A));
        }
        else if (A.Length > B.Length)
        {
            A[A.Length - B.Length] = '1';
            _sb.Append(new string(A));
        }
        else
        {
            B[B.Length - A.Length] = '1';
            _sb.Append(new string(B));
        }
        break;
    case '*':
        _sb.Append("1");
        for (int i = 0; i < A.Length + B.Length - 2; i++)
        {
            _sb.Append("0");
        }
        break;
}

Console.WriteLine(_sb);
```