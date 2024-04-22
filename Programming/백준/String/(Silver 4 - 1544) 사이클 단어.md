---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1544
```C#
using System.Text;

List<string> _list = new List<string>();

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    string _nowWord = Console.ReadLine();

    if (_list.Count == 0)
    {
        _list.Add(_nowWord);
        continue;
    }

    bool _flag = false;

    foreach (string value in _list)
    {
        if (Check(_nowWord, value))
        {
            _flag = true;
            break;
        }
    }

    if (!_flag) _list.Add(_nowWord);
}

Console.WriteLine(_list.Count);

bool Check(string argNowWord, string argListWord)
{
    StringBuilder _sb = new StringBuilder();

    int _startIndex = 0;
    int _length = argNowWord.Length;

    for (int i = 0; i < argNowWord.Length; i++)
    {
        _startIndex = i;

        for (int j = 0; j < _length; j++)
        {
            int _index = _startIndex + j;
            _sb.Append(_index >= _length ? argNowWord[_index - _length] : argNowWord[_index]);
        }

        if (_sb.ToString().Equals(argListWord)) return true;

        _sb.Clear();
    }

    return false;
}
```