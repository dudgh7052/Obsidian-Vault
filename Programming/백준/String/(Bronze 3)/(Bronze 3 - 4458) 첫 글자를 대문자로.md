---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/4458
#### charArray 활용
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
string[] _input = new string[N];

for (int i = 0; i < _input.Length; i++)
{
    _input[i] = Console.ReadLine();
}

foreach (string value in _input)
{
    char[] _char = value.ToCharArray();
    _char[0] = char.ToUpper(_char[0]);

    _sb.AppendLine(new string(_char));
}

Console.WriteLine(_sb);
```
#### Substring() 활용
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
string[] _input = new string[N];

for (int i = 0; i < _input.Length; i++)
{
    _input[i] = Console.ReadLine();
}

foreach (string value in _input)
{
    /// 첫 글자는 ToUpper로 나머지는 Substring(StartIndex) 통해서 가져와서 붙이기
    _sb.AppendLine(char.ToUpper(value[0]) + value.Substring(1)); 
}

Console.WriteLine(_sb);
```