---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/11655
```C#
// Char.IsLetter() 통해 알파벳인지 파악
// 대문자인지 소문자인지 Char.IsUpper()로 파악
// 해당 Char를 13번 밀기
// z를 넘어갔다면 -26
using System.Text;

StringBuilder _sb = new StringBuilder();
string S = Console.ReadLine();

for (int i = 0; i < S.Length; i++)
{
    char _char = S[i];

    if (!char.IsLetter(_char))
    {
        _sb.Append(_char);
        continue;
    }
    else // 알파벳일 경우
    {
        if (char.IsUpper(_char))
        {
            _char += (char)13;

            if (_char > 'Z')
            {
                _char -= (char)26;
            }
        }
        else
        {
            _char += (char)13;

            if (_char > 'z')
            {
                _char -= (char)26;
            }
        }

        _sb.Append(_char);
    }
}

Console.WriteLine(_sb);
```