---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/3028
```C#
string _input = Console.ReadLine();

int[] _cups = { 1, 0, 0 };
int _temp = 0; // 임시 저장 변수

for (int i = 0; i < _input.Length; i++)
{
    switch (_input[i])
    {
        case 'A': // 0번과 1번 인덱스 교체
            Change(0, 1);
            break;
        case 'B': // 1번과 2번 인덱스 교체
            Change(1, 2);
            break;
        case 'C': // 0번과 2번 인덱스 교체
            Change(0, 2);
            break;
    }
}

for (int i = 0; i < _cups.Length; i++)
{
    if (_cups[i] == 1)
    {
        Console.WriteLine(i + 1);
        break;
    }
}

void Change(int argfirstIndex, int argSecondIndex)
{
    _temp = _cups[argfirstIndex];
    _cups[argfirstIndex] = _cups[argSecondIndex];
    _cups[argSecondIndex] = _temp;
}
```