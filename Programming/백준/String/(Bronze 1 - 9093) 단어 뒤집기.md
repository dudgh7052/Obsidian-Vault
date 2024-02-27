---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/9093
- 참고: https://www.techiedelight.com/ko/reverse-string-csharp/ (C#에서 문자열 뒤집기)
```C#
using System.Text;
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());
StringBuilder _sb = new StringBuilder();
StringBuilder _result = new StringBuilder();

List<string> _list = new List<string>();

int T = int.Parse(_sr.ReadLine());

for (int i = 0; i < T; i++)
{
    _sb.Append(_sr.ReadLine());

    ReverseWords(_sb.ToString());

    _sb.Clear();
}

_sw.WriteLine(_result);
_sw.Close();
_sr.Close();

void ReverseWords(string argInput)
{
    _list = argInput.Split().ToList();

    foreach (string word in _list)
    {
        for (int i = word.Length - 1; i >= 0; i--)
        {
            _result.Append(word[i]);
        }

        _result.Append(" ");
    }

    _result.Append("\n");
}
```