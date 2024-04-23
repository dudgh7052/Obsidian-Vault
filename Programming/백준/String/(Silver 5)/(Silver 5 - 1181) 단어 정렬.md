---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1181
```C#
// List Class의 Distinct()로 중복 제거
// Sort()로 크기 순으로 오름차순 정렬
// OrderBy()로 요소의 길이 순으로 오름차순 정렬
using System.Text;
using System.IO;

StringBuilder _sb = new StringBuilder();
StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

int N = int.Parse(_sr.ReadLine());
List<string> _list = new List<string>();

for (int i = 0; i < N; i++)
{
    _list.Add(_sr.ReadLine());
}

_list = _list.Distinct().ToList();
_list.Sort();
_list = _list.OrderBy(x => x.Length).ToList();

foreach (string s in _list)
{
    _sb.AppendFormat("{0}\n", s);
}

_sw.WriteLine(_sb);

_sw.Close();
_sr.Close();
```