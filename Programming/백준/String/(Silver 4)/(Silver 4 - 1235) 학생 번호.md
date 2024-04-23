---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1235
```C#
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

List<string> _list = new List<string>();
List<string> _tempList = new List<string>();

int N = int.Parse(_sr.ReadLine());
for (int i = 0; i < N; i++)
{
    _list.Add(_sr.ReadLine());
}

Check(_list[0].Length - 1);
_sw.WriteLine(_tempList[0].Length);

_sr.Close();
_sw.Close();

void Check(int argIndex)
{
    bool _flag = false;

    while (true)
    {
        foreach (string value in _list)
        {
            string _subStr = value.Substring(argIndex);
            if (_tempList.Contains(_subStr))
            {
                _flag = true;
                break;
            }

            _tempList.Add(_subStr);
        }

        if (!_flag) break;

        argIndex--;
        _tempList.Clear();
        _flag = false;
    }
}
```