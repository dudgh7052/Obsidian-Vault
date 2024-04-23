---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2870
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
StringBuilder _sb = new StringBuilder();

List<string> _list = new List<string>();

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    CheckDigit();
}

// 문자열의 길이로 비교 후 문자열 크기로 비교
_list = _list.OrderBy(s => s.Length).ThenBy(s => s).ToList();

foreach (string value in _list)
{
    _result.AppendLine(value.ToString());
}

Console.WriteLine(_result);

void CheckDigit()
{
    string _input = Console.ReadLine();

    foreach (char value in _input)
    {
        if (!char.IsDigit(value))
        {
            if (_sb.Length != 0) AddDigit();
            continue;
        }

        _sb.Append(value);
    }

    if (_sb.Length != 0) AddDigit();
}

void AddDigit()
{
    // 002 인 경우 Trim()을 통해서 앞의 0 모두 제거
    string _str = _sb.ToString().TrimStart('0');
    _sb.Clear();

    // 0 일 경우 _str.Length가 0이 되기에 특수하게 0 추가해주기
    if (_str.Length == 0)
    {
        _list.Add("0");
        return;
    }

    _list.Add(_str);
}
```