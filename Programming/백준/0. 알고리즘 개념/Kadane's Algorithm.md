---
tags:
  - Baekjoon
  - Kadane
---
### Kadane's Algorithm 이란?
- 연속된 부분 배열의 최대 합을 구하는데 매우 효율적인 알고리즘
- 핵심은 현재 위치에서 부분 배열을 다시 시작할지 아니면 이전 합계값을 이용할지 결정하는 것
- 로컬 최대값을 갱신하고 로컬 최대값을 이용해 전체 최대값을 갱신
- 쉽게 말하면 이전 합계에 현재 인덱스를 더 한 값과 현재 인덱스를 비교하여 다시 시작할지 결정
- https://www.acmicpc.net/problem/10211
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
        // 현재 인덱스 값과 현재 인덱스 + 이전 합계를 비교
        _localMax = Math.Max(_arr[i], _arr[i] + _localMax);

        // 로컬 최대값을 갱신하고 전체 최대값 갱신
        _globalMax = Math.Max(_globalMax, _localMax);
    }

    Console.WriteLine(_globalMax);
}
// 2 1 -2 3 -5
// 출력: 4
// 1에서 -2로 넘어갔을때 3 -2를 한 값에 -2 보다 크므로 이전 합계 더 한 값을 로컬로 저장 
```