---
tags:
  - Baekjoon
  - Sort
---
https://www.acmicpc.net/problem/2535
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

var _list = new List<Student>();
var _countDic = new Dictionary<string, int>();

int N = int.Parse(Console.ReadLine());
while(N-- > 0)
{
    string[] _input = Console.ReadLine().Split();
    _list.Add(new Student(_input[0], _input[1], int.Parse(_input[2])));
}

_list = _list.OrderByDescending(x => x.m_score).ToList();

int _count = 0;
for(int i = 0; i < _list.Count; i++)
{
    if (_countDic.ContainsKey(_list[i].m_country))
    {
        if (_countDic[_list[i].m_country] == 2) continue;
        else
        {
            _countDic[_list[i].m_country]++;
            _result.AppendFormat("{0} {1}\n", _list[i].m_country, _list[i].m_number);
            _count++;
        }
    }
    else
    {
        _countDic.Add(_list[i].m_country, 1);
        _result.AppendFormat("{0} {1}\n", _list[i].m_country, _list[i].m_number);
        _count++;
    }

    if (_count == 3) break;
}

Console.WriteLine(_result);

class Student
{
    public string m_country;
    public string m_number;
    public int m_score;

    public Student(string country, string number, int score)
    {
        m_country = country;
        m_number = number;
        m_score = score;
    }
}
```