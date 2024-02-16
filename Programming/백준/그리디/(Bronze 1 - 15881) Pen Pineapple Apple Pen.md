---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/15881
```C#
int n = int.Parse(Console.ReadLine());
string _input = Console.ReadLine();

string _pPAp = "pPAp";
int _count = 0;

for (int i = 0; i < _input.Length; i++)
{
    int _index = _input.IndexOf(_pPAp, i); // IndexOf 이용해서 i번부터 해당 문자열이 있는지 체크

    if (_index < 0) break;

    _count++;
    i = _index + 3;
}

Console.WriteLine(_count);
```