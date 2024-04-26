---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/1789
- 1부터 증가 시키다가 같거나 넘어가면 -1 해주고 출력
```C#
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

long N = long.Parse(_sr.ReadLine());
long _sum = 0;

long _count = 0;
for (int i = 1; ; i++)
{
    _sum += i;

    if (_sum > N)
    {
        _count = --i;
        break;
    }
}

_sw.WriteLine(_count);

_sr.Close();
_sw.Close();
```