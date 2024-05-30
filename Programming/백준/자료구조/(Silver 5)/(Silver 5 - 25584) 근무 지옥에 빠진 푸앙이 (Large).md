---
tags:
  - Baekjoon
  - Collection
  - Sort
---
https://www.acmicpc.net/problem/25584
```C#
var _dic = new Dictionary<string , int>();
int[] _arr = { 4, 6, 4, 10 };

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    for (int i = 0; i < 4; i++)
    {
        string[] _input = Console.ReadLine().Split();

        foreach(string _name in _input)
        {
            if (_name == "-") continue;

            if (_dic.ContainsKey(_name)) _dic[_name] += _arr[i];
            else _dic.Add(_name, _arr[i]);
        }
    }
}

if (_dic.Count == 0)
{
    Console.WriteLine("Yes");
    return;
}

var _list = _dic.OrderBy(x => x.Value).ToList();
int _min = _list.First().Value;
int _max = _list.Last().Value;

Console.WriteLine(_max - _min <= 12 ? "Yes" : "No");
```