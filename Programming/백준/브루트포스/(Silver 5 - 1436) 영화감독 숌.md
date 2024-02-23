---
tags:
  - Baekjoon
  - 브루트포스
---
https://www.acmicpc.net/problem/1436
```C#
int N = int.Parse(Console.ReadLine());
int _count = 1;
int _num = 666;
string _findStr = "666";

while(true)
{
    if (_count == N) break;

    _num++;

    if (_num.ToString().Contains(_findStr)) 
    {
        _count++;
    }
}

Console.WriteLine(_num);
```