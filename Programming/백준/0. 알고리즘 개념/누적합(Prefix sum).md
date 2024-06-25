---
tags:
  - Baekjoon
  - PrefixSum
---
참고: https://jow1025.tistory.com/47

### 누적합이란?
- 일반적으로 사용되는 인덱스를 하나씩 더해가는 방식은 최악의 경우 O(n^2) 시간복잡도
- 하지만 누적합 방식 사용시 O(N)으로 해결 가능
![](https://i.imgur.com/Q6VpCsl.png)
- 미리 구간별로 합을 구해놓기
- 예를 들어 2~3 까지의 합을 구하고 싶으면 1번 인덱스의 값을 빼주면 구간합이 나옴

```C#
int[] _arr = { 7, 6, 3, 2, 1 };
List<int> _prefix = new List<int>();

_prefix.Add(_arr[0]); // 0번 인덱스는 미리 넣기

// 누적합 넣어주기 (마지막 값 + 현재 인덱스 값) => 0 ~ 현재 인덱스 누적합
for(int i = 1; i < _arr.Length; i++)
{
    _prefix.Add(_prefix.Last() + _arr[i]);
}

// 예를 든 2(1번 인덱스)~ 3(2번 인덱스)번까지 값 구하기
Console.WriteLine(_prefix[3 - 1] - _prefix[2 - 2]); // 16 - 7 = 9 출력

// 만약에 첫 범위가 1 일 경우는 그냥 누적합 출력
// 1 ~ 5는 19이므로 19 출력
Console.WriteLine(_prefix[5 - 1]);
```