---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/2810
```C#
int N = int.Parse(Console.ReadLine());

string _str = Console.ReadLine();

int _count = 0; // 컵홀더 카운트
int _LCount = 0; // L이 연속으로 오는지 확인
for (int i = 0; i <_str.Length; i++)
{
    if (_str[i] == 'S')
    { 
        _count++;
    }
    else if (_str[i] == 'L')
    {
        _count++;
        _LCount++;

        if (_LCount == 2)
        {
            _count--;
            _LCount = 0;
        }
    }
}

_count++;

// 컵홀더의 갯수보다 좌석수가 많은지 체크
if (_count < _str.Length)
{
    Console.WriteLine(_count);
}
else
{
    Console.WriteLine(_str.Length);
}
```