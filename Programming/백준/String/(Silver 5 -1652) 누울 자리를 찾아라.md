---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1652
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int _horizontalCount = 0;
int _verticalCount = 0;

int N = int.Parse(Console.ReadLine());

int[] _verticalList = new int[N];
int[] _verticalTotalCount = new int[N];
bool[] _verticalCheck = new bool[N];

while (N-- > 0)
{
    string _input = Console.ReadLine();
    _sb.AppendLine(_input);

    _horizontalCount += HorizontalCheck(_input);
    VerticalCheck(_input);
}

foreach (int value in _verticalTotalCount)
{
    _verticalCount += value;
}

Console.WriteLine("{0} {1}", _horizontalCount, _verticalCount);

int HorizontalCheck(string argStr)
{
    int _count = 0;
    int _totalCount = 0;
    bool _flag = false;

    foreach (char value in argStr)
    {
        if (value == '.' && !_flag) _count++;
        else if (value == 'X')
        {
            _count = 0;
            _flag = false;
            continue;
        }

        if (_count == 2)
        {
            _totalCount++;
            
            _count = 0;
            _flag = true;
        }
    }

    return _totalCount;
}

void VerticalCheck(string argStr)
{
    for (int i = 0; i < argStr.Length; i++)
    {
        if (argStr[i] == '.' && !_verticalCheck[i]) _verticalList[i]++;
        else if (argStr[i] == 'X')
        {
            _verticalList[i] = 0;
            _verticalCheck[i] = false;
            continue;
        }

        if (_verticalList[i] == 2)
        {
            _verticalTotalCount[i]++;
            _verticalList[i] = 0;
            _verticalCheck[i] = true;
        }
    }
}
```