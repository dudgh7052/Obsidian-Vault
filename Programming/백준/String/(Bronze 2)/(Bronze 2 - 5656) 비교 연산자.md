---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5656
```C#
using System.Text;

StringBuilder _result = new StringBuilder();
int _index = 0;

while (true)
{
    string[] _input = Console.ReadLine().Split();

    if (_input[1] == "E") break;

    int _num1 = int.Parse(_input[0]);
    int _num2 = int.Parse(_input[2]);

    _index++;

    _result.AppendFormat("Case {0}: {1}\n", _index, Check(_num1, _num2, _input[1]));
}

Console.WriteLine(_result);

string Check(int argFirstNum, int argSecondNum, string argCompareStr)
{
    bool _flag = false;

    switch (argCompareStr)
    {
        case ">":
            _flag = argFirstNum > argSecondNum;
            break;
        case ">=":
            _flag = argFirstNum >= argSecondNum;
            break;
        case "<":
            _flag = argFirstNum < argSecondNum;
            break;
        case "<=":
            _flag = argFirstNum <= argSecondNum;
            break;
        case "==":
            _flag = argFirstNum == argSecondNum;
            break;
        case "!=":
            _flag = argFirstNum != argSecondNum;
            break;
    }

    return _flag == true ? "true" : "false";
}
```