---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/10527
```C#
var _domjudge = new Dictionary<string, int>();
var _kattis = new Dictionary<string, int>();
int _count = 0;

int N = int.Parse(Console.ReadLine());
for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();
    if (_domjudge.ContainsKey(_input)) _domjudge[_input]++;
    else _domjudge.Add(_input, 1);
}

for (int i = 0; i < N; i++)
{
    string _input = Console.ReadLine();
    if (_kattis.ContainsKey(_input)) _kattis[_input]++;
    else _kattis.Add(_input, 1);
}

foreach (var element in _domjudge)
{
    if (!_kattis.ContainsKey(element.Key)) continue;

    _count += Math.Min(element.Value, _kattis[element.Key]);
}

Console.WriteLine(_count);
```