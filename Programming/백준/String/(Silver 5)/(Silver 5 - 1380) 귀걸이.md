---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1380
```C#
using System.Text;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

int _nowIndex = 1;
StringBuilder _result = new StringBuilder();

List<string> _students = new List<string>();
List<int> _list = new List<int>();

while (true)
{
    int _count = int.Parse(_sr.ReadLine());

    if (_count == 0) break;

    for (int i = 0; i < _count; i++)
    {
        _students.Add(_sr.ReadLine());
        _list.Add(0);
    }

    for (int i = 0; i < 2 * _count - 1; i++)
    {
        string[] _input = _sr.ReadLine().Split();
        _list[int.Parse(_input[0]) - 1]++;
    }

    Check();

    _students.Clear();
    _list.Clear();
    _nowIndex++;
}

_sw.WriteLine(_result);
_sr.Close();
_sw.Close();

void Check()
{
    for (int i = 0; i < _list.Count; i++)
    {
        if (_list[i] == 2) continue;

        _result.AppendFormat("{0} {1}\n", _nowIndex, _students[i]);
    }
}
```