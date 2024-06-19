---
tags:
  - Baekjoon
  - Sort
  - Greedy
---
https://www.acmicpc.net/problem/9237
```C#
int _day = 0;
int _left = 0;

int N = int.Parse(Console.ReadLine());
List<int> _list = Console.ReadLine().Split().Select(int.Parse).ToList();

// 자라는데 제일 오래걸리는 나무부터 심기 위해 내림차순
_list = _list.OrderByDescending(x => x).ToList();

for (int i = 0; i < _list.Count; i++)
{
    _day++; // 나무 한개 심을때마다 1 증가
    _left--; // 기존에 최대 오래걸리는 나무 1 빼기
    // 현재 심은 나무가 남은 일수보다 작은지 체크
    if (_list[i] > _left) _left = _list[i]; 
}

// 나무를 다 심고 다 자라는데까지 걸리는 시간, 다 자란 다음날로 1 추가
_day += _left + 1;
Console.WriteLine(_day);
```