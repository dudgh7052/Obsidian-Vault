---
tags:
  - Baekjoon
  - Collection
  - String
---
https://www.acmicpc.net/problem/2002
```C#
List<string> _list = new List<string>();
int _count = 0;

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    _list.Add(Console.ReadLine());
}

while(_list.Count != 0)
{
    string _input = Console.ReadLine();

    if (_list[0] == _input)
    {
        _list.RemoveAt(0);
    }
    else
    {
        int _index = _list.IndexOf(_input);
        _list.RemoveAt(_index);
        _count++;
    }
}

Console.WriteLine(_count);
```