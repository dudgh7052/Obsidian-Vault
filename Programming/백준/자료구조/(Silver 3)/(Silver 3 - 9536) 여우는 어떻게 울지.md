---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/9536
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
List<string> _sounds = new List<string>();
HashSet<string> _another = new HashSet<string>();

int T = int.Parse(Console.ReadLine());
while(T-- > 0)
{
    _sounds = Console.ReadLine().Split().ToList();

    for (int i = 0; i < 100; i++)
    {
        string[] _animal = Console.ReadLine().Split();

        if (_animal[0] == "what") break;

        _another.Add(_animal[2]);
    }

    foreach (string sound in _sounds)
    {
        if (!_another.Contains(sound)) _result.AppendFormat("{0} ", sound);
    }

    Console.WriteLine(_result);

    _sounds.Clear();
    _another.Clear();
    _result.Clear();
}
```