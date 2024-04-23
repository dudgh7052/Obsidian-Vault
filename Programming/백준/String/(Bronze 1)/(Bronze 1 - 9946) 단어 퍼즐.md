---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/9946
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

Dictionary<char, int> _firstDic = new Dictionary<char, int>();
Dictionary<char, int> _secondDic = new Dictionary<char, int>();

int _index = 0;

while (true)
{
    string _firstInput = Console.ReadLine();
    string _secondInput = Console.ReadLine();

    if (_firstInput == "END" && _secondInput == "END") break;

    AddValueToDic(_firstInput, _firstDic);
    AddValueToDic(_secondInput, _secondDic);

    _result.AppendFormat("Case {0}: {1}\n", ++_index, (Check() == true ? "same" : "different"));
    
    _firstDic.Clear();
    _secondDic.Clear();
}

Console.WriteLine(_result);

bool Check()
{
    foreach (char _char in _firstDic.Keys)
    {
        if (!_secondDic.ContainsKey(_char)) // 키가 없는 경우
        {
            return false;
        }
        else // 키가 있는 경우 
        {
            if (_firstDic[_char] != _secondDic[_char])
            {
                return false;
            }
        }
    }

    return true;
}

void AddValueToDic (string argStr, Dictionary<char, int> argDictionary)
{
    foreach (char _char in argStr)
    {
        if (argDictionary.ContainsKey(_char))
        {
            argDictionary[_char]++;
        }
        else { argDictionary.Add(_char, 1); }
    }
} 
```