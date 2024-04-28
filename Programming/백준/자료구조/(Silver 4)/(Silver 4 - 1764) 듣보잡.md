---
tags:
  - Baekjoon
  - Collection
  - String
  - Sort
---
https://www.acmicpc.net/problem/1764
```C#
StreamReader _sr = new StreamReader(Console.OpenStandardInput(), bufferSize:65536);
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput(), bufferSize: 65536);

Dictionary<string, int> _dic = new Dictionary<string, int>();
List<string> _list = new List<string>();

int[] _split = _sr.ReadLine().Split().Select(int.Parse).ToArray();
for(int i = 0; i < _split[0]; i++)
{
    _dic.Add(_sr.ReadLine(), 1);
}

for (int i = 0; i < _split[1]; i++)
{
    string _name = _sr.ReadLine();
    if (_dic.ContainsKey(_name)) _list.Add(_name);
}

_list.Sort();

_sw.WriteLine(_list.Count);
foreach(string value in _list)
{
   _sw.WriteLine(value);
}

_sr.Close();
_sw.Close();
```