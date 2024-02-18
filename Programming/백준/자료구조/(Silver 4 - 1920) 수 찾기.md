---
tags:
  - Baekjoon
  - 자료구조
  - BinarySearch
---
https://www.acmicpc.net/problem/1920
- 이분 탐색([[Binary Search]])은 [[List]]가 정렬이 되어있어야 함
- 참고: https://m42-orion.tistory.com/69
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());
List<int> _firstList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();

int M = int.Parse(Console.ReadLine());
List<int> _secondList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();

_firstList.Sort(); // 이분 탐색은 꼭 정렬을 해야 함

int _low = 0; // 찾는 곳의 최소 범위
int _high = _firstList.Count - 1; // 찾는 곳의 최대 범위
int _mid = 0; // 최소 최대 중간 인덱스
int _target = 0; // 찾는 값

for (int i = 0; i < _secondList.Count; i++)
{
    _target = _secondList[i];
    _low = 0;
    _high = _firstList.Count - 1;

    while (true)
    {
        _mid = (_low + _high) / 2;

        // 중간값이 같은지 확인
        if (_firstList[_mid] == _target)
        {
            _sb.AppendLine("1");
            break;
        }

        if (_target > _firstList[_mid]) // 찾는 값이 중간 값보다 큰 경우
        {
            _low = _mid + 1;
        }
        else if (_target < _firstList[_mid]) // 찾는 값이 중간 값보다 작은 경우
        {
            _high = _mid - 1;
        }

        if (_high < _low) // _high = 0, _low = 0 일때 까지만 확인하면 없으므로 종료
        {
            _sb.AppendLine("0");
            break;
        }
    }
}

Console.WriteLine(_sb);
```