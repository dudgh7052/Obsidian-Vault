---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2744
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

string _input = Console.ReadLine();

for (int i = 0; i < _input.Length; i++)
{
    char _char = _input[i];
    // char struct의 IsUpper()와 ToLower(),ToUpper() 활용 
    _result.Append(char.IsUpper(_char) ? char.ToLower(_char) : char.ToUpper(_char));
}

Console.WriteLine(_result);
```

- 참고: https://learn.microsoft.com/ko-kr/dotnet/api/system.char?view=net-8.0