---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1264
```C#
int _count = 0;

while (true)
{
    _count = 0;
    string _input = Console.ReadLine().ToUpper();

    if (_input == "#") return;

    foreach (char value in _input)
    {
        if (value.Equals('A') || value.Equals('E') || value.Equals('I') || value.Equals('O') || value.Equals('U'))
        {
            _count++;
        }
    }

    Console.WriteLine(_count);
}
```