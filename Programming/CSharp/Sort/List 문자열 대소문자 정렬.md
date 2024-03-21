---
tags:
  - CSharp
  - Sort
---
### List.Sort() 문자열 대소문자 구분없이  정렬

```C#
List<string> _list = new List<string>() { "apple", "Banana", "Orange", "grape" };

_list.Sort(StringComparer.OrdinalIgnoreCase);

foreach (string item in _list)
{
    Console.WriteLine(item); // apple, Banana, grape, Orange 순으로 정렬
}
```
### List.Sort() 문자열 대소문자 구분 정렬
- Sort() 안에서 'StringComparer.Ordinal' 넣어주면 대소문자 구분 오름차순 정렬
- 기본적으로 오름차순 정렬 시 대문자가 앞으로 나오므로 대문자 먼저 출력
```C#
List<string> _list = new List<string>() { "apple", "Banana", "Orange", "grape" };

_list.Sort(StringComparer.Ordinal);

foreach (string item in _list)
{
    Console.WriteLine(item); // Banana, Orange, apple, grape 순으로 정렬
}