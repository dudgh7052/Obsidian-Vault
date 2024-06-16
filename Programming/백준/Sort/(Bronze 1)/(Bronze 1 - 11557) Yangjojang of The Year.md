---
tags:
  - Baekjoon
  - Sort
  - Collection
---
https://www.acmicpc.net/problem/11557
```C#
List<Univ> _list = new List<Univ>();

int T = int.Parse(Console.ReadLine());
while(T-- > 0)
{
    int N = int.Parse(Console.ReadLine());
    for (int i = 0; i < N; i++)
    {
        string[] _input = Console.ReadLine().Split();
        _list.Add(new Univ(_input[0], int.Parse(_input[1])));
    }

    _list = _list.OrderByDescending(x => x.m_value).ToList();
    Console.WriteLine(_list[0].m_name);

    _list.Clear();
}

class Univ
{
    public string m_name;
    public int m_value;

    public Univ(string argName, int argValue)
    {
        m_name = argName;
        m_value = argValue;
    }
}
```