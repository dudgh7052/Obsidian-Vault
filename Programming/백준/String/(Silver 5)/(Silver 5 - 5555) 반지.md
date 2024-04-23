---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5555
### 이어붙이기 방법
- "BCXXXXXXXA" 에서 "ABC"를 찾는다면 이어붙여서 "BCXXXXXXX(ABC)XXXXXXXA" 만들고 패턴 찾기
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

string _word = Console.ReadLine();
int _count = 0;

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    _sb.Append(Console.ReadLine());
    _sb.Append(_sb.ToString());

    if (_sb.ToString().Contains(_word))
    {
        _count++;
    }

    _sb.Clear();
}

Console.WriteLine(_count);
```
### 한 문자씩 더해가면서 한 풀이
```C#
using System.Text;

string _word = Console.ReadLine();
int _count = 0;

int N = int.Parse(Console.ReadLine());
while (N-- > 0)
{
    string _ringPattern = Console.ReadLine();
    Check(_ringPattern);
}

Console.WriteLine(_count);

void Check(string argRingPattern)
{
    StringBuilder _sb = new StringBuilder();
    int _startIndex = 0;

    while (true)
    {
        _startIndex = argRingPattern.IndexOf(_word[0], _startIndex);

        if (_startIndex == -1) break;

        for (int i = 0; i < _word.Length; i++)
        {
            int _index = _startIndex + i < 10 ? _startIndex + i : (_startIndex + i) - 10;
            if (argRingPattern[_index] != _word[i])
            {
                _sb.Clear();
                break;
            }

            _sb.Append(argRingPattern[_index]);
        }

        if (_sb.ToString() == _word)
        {
            _count++;
            return;
        }

        _startIndex++;
    }
}
```
