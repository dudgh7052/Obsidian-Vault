---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/2839

```C#
int _value = int.Parse(Console.ReadLine());

int _answer = 0;

while (_value > 0)
{
    if (_value % 5 == 0)
    {
        _answer += (_value / 5);
        _value -= (_value / 5) * 5;
        continue;
    }

    _value -= 3;
    _answer++;
}

if (_value == 0)
{
    Console.WriteLine(_answer);
}
else
{
    Console.WriteLine(-1);
}
```
