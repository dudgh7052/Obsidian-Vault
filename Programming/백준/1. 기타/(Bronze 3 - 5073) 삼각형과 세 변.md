---
tags:
  - Baekjoon
---
https://www.acmicpc.net/problem/5073
```C#
using System.Collections.Generic;
using System.Text;

StringBuilder _sb = new StringBuilder();
StringBuilder _answer = new StringBuilder();

List<int> _lengthList = new List<int>();

while (true)
{
    //Init
    _sb.Clear();
    _lengthList.Clear();

    _sb.Append(Console.ReadLine());
    if (_sb.ToString() == "0 0 0")
    {
        Console.Write(_answer);
        return;
    } 

    _lengthList = _sb.ToString().Split().Select(x => int.Parse(x)).ToList();
    _lengthList.Sort();

    // 제일 큰값과 작은 두 값의 합이 작으면 삼각형 조건 만족 못 함
    if (_lengthList[0] + _lengthList[1] <= _lengthList[2])
    {
        _answer.Append("Invalid\n");
        continue;
    }

    if (_lengthList[0] == _lengthList[1] && _lengthList[1] == _lengthList[2])
    {
        _answer.Append("Equilateral\n");
    }
    else if (_lengthList[0] != _lengthList[1] && _lengthList[1] == _lengthList[2]
        || _lengthList[0] == _lengthList[1] && _lengthList[1] != _lengthList[2])
    {
        _answer.Append("Isosceles\n");
    }
    else
    {
        _answer.Append("Scalene\n");
    }
}
```