---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/2358
```C#
var _dicX = new Dictionary<string, int>();
var _dicY = new Dictionary<string, int>();
int _count = 0;

int n = int.Parse(Console.ReadLine());
while(n--> 0)
{
    string[] _pos = Console.ReadLine().Split();

    if (_dicX.ContainsKey(_pos[0])) _dicX[_pos[0]]++;
    else _dicX.Add(_pos[0], 1);

    if (_dicY.ContainsKey(_pos[1])) _dicY[_pos[1]]++;
    else _dicY.Add(_pos[1], 1);
}

foreach(KeyValuePair<string, int> element in _dicX)
{
    if (element.Value >= 2) _count++;
}

foreach (KeyValuePair<string, int> element in _dicY)
{
    if (element.Value >= 2) _count++;
}

Console.WriteLine(_count);
```