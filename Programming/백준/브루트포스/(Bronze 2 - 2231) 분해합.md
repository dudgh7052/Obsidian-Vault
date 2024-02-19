---
tags:
  - Baekjoon
  - 브루트포스
---
https://www.acmicpc.net/problem/2231
```C#
// 0 ~ N까지 현재 수 + 현재 수의 숫자 합이 N과 같은걸 찾는거
int N = int.Parse(Console.ReadLine());

for (int i = 0; i <= N; i++)
{
    int _num = i;

    int _sum = _num; // 값 미리 넣어놓기
    while (true)
    {
        if (_num == 0) break;

        // 자릿수 구하기
        _sum += _num % 10;
        _num = _num / 10;
    }

    if (_sum == N)
    {
        Console.WriteLine(i);
        return;
    }
}

Console.WriteLine(0);
```