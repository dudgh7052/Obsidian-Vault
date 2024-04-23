---
tags:
  - Baekjoon
  - String
---
- 예를들어 '1'이 아스키코드로 49 이므로 그냥 숫자로 나타낼려면 49 - 48 = 1이 됨
- 각 자리별로 합계를 구해서 한번에 곱하기
```C#
string _input = Console.ReadLine();
string[] _splitStr = _input.Split();
long _sum = 0;
long _tempNum1 = 0;
long _tempNum2 = 0;

if (_input == "0") 
{
    Console.WriteLine("0");
    return;
}

// 아스키코드 활용
// 자릿수별로 누적해서 한번에 곱하기
for (int i = 0; i < _splitStr[0].Length; i++)
{
    _tempNum1 += _splitStr[0][i] - 48;   
}

for (int j = 0; j < _splitStr[1].Length; j++)
{
    _tempNum2 += _splitStr[1][j] - 48;   
}

_sum = _tempNum1 * _tempNum2;

Console.WriteLine(_sum);
```