---
tags:
  - Baekjoon
  - Kadane
---
https://www.acmicpc.net/problem/10211
```C#
int T = int.Parse(Console.ReadLine());
while(T-- > 0)
{
    int N = int.Parse(Console.ReadLine());
    int[] _arr = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);

    int _globalMax = _arr[0];
    int _localMax = _arr[0];
    for (int i = 1; i < _arr.Length; i++)
    {
        // 부분배열을 다시 시작할지 이전 합계를 이용할지 결정
        _localMax = Math.Max(_arr[i], _arr[i] + _localMax);

        // 로컬 최대값을 갱신하고 전체 최대값 갱신
        _globalMax = Math.Max(_globalMax, _localMax);
    }

    Console.WriteLine(_globalMax);
}
```