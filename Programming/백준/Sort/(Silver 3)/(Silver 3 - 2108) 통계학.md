---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/2108
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int _sum = 0;
var _list = new List<int>();
var _dic = new Dictionary<int, int>();

int N = int.Parse(Console.ReadLine());
while (N-- > 0)
{
    int _key = int.Parse(Console.ReadLine());

    _sum += _key;
    _list.Add(_key);
    if (!_dic.TryAdd(_key, 1)) _dic[_key]++;
}

_list.Sort();

// 산술평균
double _average = Math.Round((double)_sum / _list.Count, 0);
_result.AppendFormat("{0}\n", _average == -0 ? 0: _average);

// 중앙값
_result.AppendFormat("{0}\n", _list[(_list.Count / 2)]);

// 최빈값
int _max = _dic.Values.Max();
var _elements = _dic.Where(x => x.Value == _max).OrderBy(x => x.Key).ToList();
_result.AppendFormat("{0}\n", _elements.Count() > 1 ? _elements[1].Key : _elements[0].Key);

// 범위
_result.AppendFormat("{0}\n", _list.Max() - _list.Min());

Console.WriteLine(_result);
```