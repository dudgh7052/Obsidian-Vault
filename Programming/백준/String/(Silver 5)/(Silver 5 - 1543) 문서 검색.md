---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1543
```C#
string _input = Console.ReadLine();
string _word = Console.ReadLine();
int _count = 0;

int _index = 0; // 인덱스 저장용 변수

while (true)
{
    // 현재 인덱스 + 단어 길이가 input의 길이보다 클 경우 종료
    if (_index + _word.Length > _input.Length)
    {
        break;
    }

    // 저장 한 인덱스부터 단어의 길이까지 가져와서 비교
    if (_word == _input.Substring(_index, _word.Length))
    {
        _count++;
        _index += _word.Length; // 같을 경우 길이만큼 인덱스 더하기
    }
    else
    {
        _index++; // 아닐 경우 한자리 이동
    }
}

Console.WriteLine(_count);
```