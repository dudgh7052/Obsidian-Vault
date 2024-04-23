---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1159
```C#
// Dictionary로 char키 int 값 만든 뒤
// 선수들의 앞글자만 본 뒤 값 더하기
// 마지막에 해당하는 키의 값이 5보다 크거나 같을 경우만 char[] 에 넣은 뒤 출력에 포함
using System.Text;
using System.Collections.Generic;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

var _dic = new Dictionary<char,int>();
var _list = new List<char>();

int N = int.Parse(_sr.ReadLine());
for (int i = 0; i < N; i++)
{
    string _str = _sr.ReadLine();

    if (!_dic.ContainsKey(_str[0]))
    {
        _dic.Add(_str[0], 1);
    }
    else
    {
        _dic[_str[0]]++;
    }
}

foreach (char _char in _dic.Keys)
{
    if (_dic[_char] >= 5)
    {
        _list.Add(_char);
    }
}

_list.Sort();

if (_list.Count == 0) _sw.WriteLine("PREDAJA");
else { _sw.WriteLine(new string(_list.ToArray())); }

_sw.Close();
_sr.Close();
```