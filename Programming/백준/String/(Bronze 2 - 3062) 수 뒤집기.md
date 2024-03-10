---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/3062
- [[문자열 반전 (Reverse)]]의 Enumeable.Reverse 참고
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    // 수 두개 받아오기
    string _num1 = Console.ReadLine();
    // 기존 수 반전 한 뒤 배열로 만들고 다시 string 타입으로
    string _num2 = new string(_num1.Reverse().ToArray());

    string _value = (int.Parse(_num1) + int.Parse(_num2)).ToString();
    string _reverseValue = new string(_value.Reverse().ToArray());

    _result.AppendLine(_value == _reverseValue ? "YES" : "NO");
}

Console.WriteLine(_result);
```