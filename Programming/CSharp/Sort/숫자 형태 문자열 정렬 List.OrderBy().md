---
tags:
  - CSharp
  - String
  - Sort
---
### List.OrderBy(s => s.Length).ThenBy(s => s)
- 문자열의 길이로 정렬 한 다음 크기로 비교 시 숫자 크기로 비교 한 결과와 똑같이 얻을 수 있음
- Reverse()시 내림차순으로도 가능
```C#
List<string> _list = new List<string>()
{
    "10", "1", "2", "3", "40", "123", "124",
};

_list = _list.OrderBy(s => s.Length).ThenBy(s => s).ToList();

foreach(string value in _list)
{
    Console.Write(value + " "); // 1 2 3 10 40 123 124
}
```