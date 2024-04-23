---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2153
```C#
string _input = Console.ReadLine();
int _sum = 0;
bool _isPrime = true;

// 합 구하기
foreach (char c in _input)
{
    if (char.IsUpper(c))
    {
        _sum += c - 38; // A(65) - 37 => 27
    }
    else
    {
        _sum += c - 96; // a(97) - 96 => 1
    }
}

// 제곱근 까지만 구하기
for (int i = 2; i * i <= _sum; i++)
{
    if (_sum % i != 0) continue;

    _isPrime = false;
    break;
}

Console.WriteLine(_isPrime == true ? "It is a prime word." : "It is not a prime word.");
```