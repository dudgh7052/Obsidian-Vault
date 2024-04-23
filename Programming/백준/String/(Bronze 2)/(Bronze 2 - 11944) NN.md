---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/11944
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();
string[] _input = Console.ReadLine().Split();

int _N = int.Parse(_input[0]);
int _M = int.Parse(_input[1]);

for (int i = 0; i < _N; i++)
{
    if (_sb.Length > _M) break;

    _sb.Append(_input[0]);
}

// 출력길이가 M자리수보다 클 경우
if (_sb.Length > _M)
{
    // Substring(startIndex, Length) 이용해서 M자리수만 출력
    // 그냥 출력이 더 짧을수록 그냥 출력
    Console.WriteLine(_sb.ToString().Substring(0, _M));
}
else Console.WriteLine(_sb);
```