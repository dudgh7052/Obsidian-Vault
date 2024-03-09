---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2495
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

string _input = string.Empty;
char _nowChar = default;
int _maxCount = 1;
int _nowCount = 1;

for (int i = 0; i < 3; i++)
{
    _input = Console.ReadLine();

    _nowChar = _input[0];
    for (int j = 1; j < 8; j++)
    {
        if (_nowChar == _input[j])
        {
            _nowCount++;

            if (IsMaxCount()) _maxCount = _nowCount;
        }
        else
        {
            // 같지 않다면 최대 카운트와 비교
            if (IsMaxCount()) _maxCount = _nowCount;

            _nowChar = _input[j];
            _nowCount = 1;
            continue;
        }
    }

    _sb.AppendLine(_maxCount.ToString());

    // Initialize
    _nowCount = 1;
    _maxCount = 1;
}

Console.WriteLine(_sb);

bool IsMaxCount() { return _nowCount > _maxCount; }
```