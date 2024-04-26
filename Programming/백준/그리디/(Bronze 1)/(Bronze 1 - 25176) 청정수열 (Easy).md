---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/25176
```C#
// N이 5라면 1122334455 이런식으로 오는게
// 제일 점수가 낮기에 5!가 답이다.

int N = int.Parse(Console.ReadLine());
int _sum = 1;

for (int i = 1; i <= N; i++)
{
    _sum *= i;
}

Console.WriteLine(_sum);
```