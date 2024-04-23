---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/status?user_id=youngho7052&problem_id=2789&from_mine=1
```C#
List<char> _char = Console.ReadLine().ToUpper().ToList();

for (int i = 0; i < _char.Count; i++)
{
    if (_char[i] == 'C' || _char[i] == 'A' || _char[i] == 'M' ||
        _char[i] == 'B' || _char[i] == 'R' || _char[i] == 'I' ||
        _char[i] == 'D' || _char[i] == 'G' || _char[i] == 'E')
    {
        _char.Remove(_char[i]);
        i--;
    } 
}

Console.WriteLine(new string(_char.ToArray()));
```
- Where을 사용해서 해당하는게 없는 것만 리턴하기
```C#
char[] _char = Console.ReadLine().Where(value => !"CAMBRIDGE".Contains(value)).ToArray();
Console.WriteLine(_char);
```