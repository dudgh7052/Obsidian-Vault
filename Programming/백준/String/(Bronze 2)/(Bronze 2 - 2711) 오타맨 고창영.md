---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/2711
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());

for (int i = 0; i < N; i++)
{
    string[] _input = Console.ReadLine().Split();

    // string의 Remove(index, count)로 StringBuilder에 한꺼번에 넣어서 출력
    _sb.AppendLine(_input[1].Remove(int.Parse(_input[0]) - 1 , 1));
}

Console.WriteLine(_sb);
```