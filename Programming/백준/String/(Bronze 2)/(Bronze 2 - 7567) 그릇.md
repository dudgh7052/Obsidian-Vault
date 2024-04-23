---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/7567
```C#
// 마지막으로 쌓았던 그릇이 같은 방향인지 체크
// 다르면 10 추가 같으면 5 추가
string _input = Console.ReadLine();
int _height = 10;

bool _isRight = (_input[0] == '(') ? true : false;

for (int i = 1; i < _input.Length; i++)
{
    if (_isRight) // 마지막 그릇이 오른쪽 일 경우
    {
        _height += _input[i] == '(' ? 5 : 10;
    }
    else if (!_isRight) // 왼쪽 일 경우
    {
        _height += _input[i] == ')' ? 5 : 10;
    }

    // 마지막 방향 기억
    _isRight = _input[i] == '(' ? true : false;
}

Console.WriteLine(_height);
```