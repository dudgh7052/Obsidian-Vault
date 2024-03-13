---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/6378
```C#
while (true)
{
    string _input = Console.ReadLine();

    if (_input == "0") break;

    Console.WriteLine(Digit(_input));
}

string Digit(string argStr)
{
    while (true)
    {
        int _sum = 0;

        for (int i = 0; i < argStr.Length; i++)
        {
            _sum += argStr[i] - 48;
        }

        if (_sum < 10)
        {
            return _sum.ToString();
        }

        argStr = _sum.ToString();
    }
}
```