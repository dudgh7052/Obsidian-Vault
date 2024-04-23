---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/11319
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int S = int.Parse(Console.ReadLine());

while(S-- > 0)
{
    string _input = Console.ReadLine().ToUpper();
    Check(_input);
}

Console.WriteLine(_result);

void Check(string argStr)
{
    int _consonantCount = 0;
    int _vowelCount = 0;

    foreach (char value in argStr)
    {
        if (!char.IsLetter(value)) continue;

        if (value == 'A' || value == 'E' || value == 'I' || value == 'O' || value == 'U')
        {
            _vowelCount++;
        }
        else _consonantCount++;
    }

    _result.AppendFormat("{0} {1}\n", _consonantCount, _vowelCount);
}
```