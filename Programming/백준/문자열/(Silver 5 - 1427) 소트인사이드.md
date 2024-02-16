---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1427
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

List<int> _list = new List<int>();

string _input = Console.ReadLine();

int _nowDigit = _input.Length - 1; // 큰 자릿수부터 몫을 구하기 위한 변수
int _remain = int.Parse(_input); // 남은 값을 저장 할 변수

for (int i = 0; i < _input.Length; i--)
{
    int _digit = (int)(MathF.Pow(10, _nowDigit)); // 자릿수에 맞게 셋팅

	// 1의 자리일 경우
    if (_nowDigit == 0)
    {
        _list.Add(_remain);
        break;
    }

    _list.Add(_remain / _digit); // 몫 리스트에 넣어주기
    _remain -= (_remain / _digit) * _digit; // 몫으로 빠진 값 빼주기

    _nowDigit--; // 자릿수 내리기
}

_list.Sort(); // 오름차순 정렬
_list.Reverse(); // Reverse()로 내림차순 정렬

// 순서대로 StringBuilder에 넣어서 한번에 출력하기
foreach (int i in _list)
{
    _sb.Append(i);
}

Console.WriteLine(_sb);
```