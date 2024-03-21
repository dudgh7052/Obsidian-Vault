---
tags:
  - CSharp
  - Sort
---
- Sort()의 정렬은 오름차순 정렬이므로 Reverse()를 통해 순서를 뒤집어서 내림차순 정렬
```C#
List<int> _list = new List<int>() { 5, 2, 1, 3, 4 };

_list.Sort();
_list.Reverse();

foreach (int item in _list)
{
    Console.WriteLine(item); // 5, 4, 3, 2, 1 순으로 정렬
}