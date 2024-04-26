---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/2217
```C#
// 줄 중에서 (제일 낮은 중량 * 최대로 사용한 갯수)와 비교
// (그 다음 낮은 중량 * 사용한 갯수)를 
// 제일 큰 값을 찾은 후 출력
using System.Collections.Generic;
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

int _input = int.Parse(_sr.ReadLine());
List<int> _lopeList = new List<int>();

// 로프 별 중량 리스트에 넣기
for (int i = 0; i < _input; i++)
{
    _lopeList.Add(int.Parse(_sr.ReadLine()));
}

_lopeList.Sort(); // 오름차순 정렬

int _max = 0; // 감당 가능한 최대 중량
int _lopeCount = _lopeList.Count + 1; // 사용 할 로프 갯수
for (int i = 0; i < _lopeList.Count; i++)
{
    _lopeCount--;

    if (_lopeCount * _lopeList[i] < _max) continue;

    // 현재 로프의 중량 * 로프 갯수가 클 경우
    _max = _lopeCount * _lopeList[i];
}

_sw.WriteLine(_max);

_sr.Close();
_sw.Close();
```