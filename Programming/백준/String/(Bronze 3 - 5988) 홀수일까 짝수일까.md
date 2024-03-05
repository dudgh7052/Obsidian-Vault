---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5988
```C#
// 맨 마지막 숫자가 2의 배수면 짝수, 아니면 홀수
// 이 문제의 함정은 10의 60승 Overflow Error가 나게 됨
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
string[] _input = new string[N];

for (int i = 0; i < _input.Length; i++)
{
    _input[i] = Console.ReadLine();
}

foreach (string _str in _input)
{
    // 맨 마지막 char 가져와서 48빼주기 0은 아스키코드로 48이기에 48 - 48 => 0 
    int _value = _str[_str.Length - 1] - 48;

    // 짝수 홀수 판단 - 2의 배수이면 짝수 아니면 홀수
    if (_value % 2 == 0) _sb.AppendLine("even");
    else _sb.AppendLine("odd");
}

Console.WriteLine(_sb.ToString());
```