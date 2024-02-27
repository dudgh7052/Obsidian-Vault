---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1259
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

while (true)
{
    string _input = Console.ReadLine();

    if (_input == "0") break;

    bool _isFlag = false;

    for (int i = 0; i < _input.Length / 2; i++) // 중간까지만 계산하면 되기에 길이 / 2
    {
        // 같으면 돌아가기
        if (_input[i] == _input[_input.Length - 1 - i]) continue;

        _isFlag = true; // 같지 않을 경우 true 만들기
    }

    // 판단부분
    if (_isFlag) _sb.Append("no");
    else _sb.Append("yes");

    _sb.Append("\n");
}

Console.WriteLine(_sb);
```