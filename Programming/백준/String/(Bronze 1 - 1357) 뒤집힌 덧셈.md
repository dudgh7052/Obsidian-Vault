---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1357
### 함수 정리 후
```C#
string[] _input = Console.ReadLine().Split();
string _str1 = _input[0];
string _str2 = _input[1];

int _sum = Reverse(_str1) + Reverse(_str2);

Console.WriteLine(Reverse(_sum.ToString()));

int Reverse(string argStr)
{
    char[] _temp = argStr.ToCharArray();
    Array.Reverse(_temp);

    return int.Parse(new string(_temp));
}
```
### 정리 전
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

string[] _input = Console.ReadLine().Split();
char[] _char1 = _input[0].ToCharArray();
char[] _char2 = _input[1].ToCharArray();

Array.Reverse(_char1);
Array.Reverse(_char2);

int _sum = int.Parse(new string(_char1)) + int.Parse(new string(_char2));

while (true)
{
    if (_sum == 0) break;

    _sb.Append(_sum % 10);
    _sum /= 10;
}

Console.WriteLine(int.Parse(_sb.ToString()));
```