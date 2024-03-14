---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1871
```C#
int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string[] _input = Console.ReadLine().Split('-');

    int _diff = Math.Abs(GetValue(_input[0]) - int.Parse(_input[1]));
    switch (_diff)
    {
        case int value when value <= 100:
            Console.WriteLine("nice");
            break;
        case int value when value > 100:
            Console.WriteLine("not nice");
            break;
    }
}

int GetValue(string argStr)
{
    int _sum = 0;
    int _index = 2;

    for (int i = 0; i < argStr.Length; i++)
    {
        _sum += (argStr[i] - 65) * (int)MathF.Pow(26, _index);
        _index--;
    }

    return _sum;
}
```