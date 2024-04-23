---
tags:
  - Baekjoon
  - String
  - Greedy
---
https://www.acmicpc.net/problem/1439
```C#
string _input = Console.ReadLine();

Console.WriteLine(Math.Min(Count('1'), Count('0')));

int Count(char argChar)
{
    int _count = 0;
    char _lastChar = default;

    foreach (char value in _input)
    {
        // 뒤집을 요소가 아닌 경우
        if (value == argChar) 
        {
            _lastChar = value;
            continue;
        }

        // 전 요소와 같지 않을 경우
        if (_lastChar != value)
        {
            _lastChar = value;
            _count++;
        }
        else _lastChar = value; // 같은 경우 현재요소 저장
    }

    return _count;
}
```