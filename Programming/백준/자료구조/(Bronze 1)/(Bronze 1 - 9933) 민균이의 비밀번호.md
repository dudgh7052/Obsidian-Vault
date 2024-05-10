---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/9933
```C#
List<string> _list = new List<string>();

int N = int.Parse(Console.ReadLine());
while (N-- > 0)
{
    string _input = Console.ReadLine();
    _list.Add(_input);
}

foreach (string value in _list)
{
    if (_list.Contains(Reverse(value)) || value == Reverse(value))
    {
        Console.WriteLine("{0} {1}", value.Length, value[value.Length / 2]);
        return;
    }
}

string Reverse(string argStr)
{
    char[] _char = argStr.ToCharArray();
    Array.Reverse(_char);

    return new string(_char);
}
```