---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/29766
- IndexOf()로 인덱스 이동시키면서 하기
```C#
string _input = Console.ReadLine();
string _dksh = "DKSH";

Console.WriteLine(WordCount());

int WordCount()
{
    int _count = 0;
    int _index = 0;

    while (true)
    {
        _index = _input.IndexOf("DKSH", _index);

        if (_index == -1)
        {
            break;
        }

        _index += _dksh.Length;
        _count++;
    }

    return _count;
}
```
- Replace() 로 바꾼 뒤 그 문자 갯수세기
```C#
string _input = Console.ReadLine();

_input = _input.Replace("DKSH", " ");
Console.WriteLine(CharCount(_input));

int CharCount(string argStr)
{
    int _count = 0;

    foreach (char value in _input)
    {
        if (value == ' ') _count++;
    }

    return _count;
}
```