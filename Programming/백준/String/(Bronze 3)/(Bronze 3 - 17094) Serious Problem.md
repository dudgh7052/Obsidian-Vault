---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/17094
```C#
// 92ms
// Linq 사용
int N = int.Parse(Console.ReadLine());
string _input = Console.ReadLine();

Console.WriteLine(Check());

string Check()
{
    return Count('2') switch
    {
        int value when value > Count('e') => "2",
        int value when value < Count('e') => "e",
        int value when value == Count('e') => "yee"
    };
}

int Count (char argFoundChar)
{
    return _input.Count(value => value == argFoundChar);
}
```

```C#
// 68 ms
// foreach문
int N = int.Parse(Console.ReadLine());
string _input = Console.ReadLine();

int _2Count = 0;
int _eCount = 0;

Count();
Console.WriteLine(Check());

string Check()
{
    return _2Count switch
    {
        int value when value > _eCount => "2",
        int value when value < _eCount => "e",
        int value when value == _eCount => "yee"
    };
}

void Count()
{
    foreach (char _char in _input)
    {
        switch (_char)
        {
            case '2':
                _2Count++;
                break;
            case 'e':
                _eCount++;
                break;
        }
    }
}
```