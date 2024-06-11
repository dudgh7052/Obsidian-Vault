---
tags:
  - Baekjoon
  - Sort
  - Collection
  - BinarySearch
---
https://www.acmicpc.net/problem/7795
```C#
using System.Text;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());
StringBuilder _result = new StringBuilder();


int T = int.Parse(_sr.ReadLine());
while(T-- > 0)
{
    int[] NM = _sr.ReadLine().Split().Select(int.Parse).ToArray();
    int[] A = _sr.ReadLine().Split().Select(int.Parse).ToArray();
    int[] B = _sr.ReadLine().Split().Select(int.Parse).ToArray();
    int _count = 0;

    Array.Sort(A);
    Array.Sort(B);

    foreach(int value in A)
    {
        _count += BinarySearch(B, value);
    }

    _result.AppendLine(_count.ToString());
}

_sw.WriteLine(_result);
_sr.Close();
_sw.Close();

int BinarySearch(int[] argArray, int argNum)
{
    int _start = 0;
    int _end = argArray.Length;

    while(_start < _end)
    {
        int _mid = (_start + _end) / 2;

        if (argArray[_mid] < argNum) _start = _mid + 1;
        else _end = _mid;
    }

    return _start;
}
```