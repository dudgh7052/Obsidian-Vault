---
tags:
  - CSharp
  - Sort
---
```C#
// BubbleSort
using System.Text;
using System.IO;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

StringBuilder _sb = new StringBuilder();

int N = int.Parse(_sr.ReadLine());
List<int> _list = new List<int>();
int _temp = 0;

for (int i = 0; i < N; i++)
{
    _list.Add(int.Parse(_sr.ReadLine()));
}

BubbleSort(_list);

foreach (int i in _list)
{
    _sb.AppendLine(i.ToString());
}

_sw.WriteLine(_sb);

_sw.Close();
_sr.Close();

void BubbleSort(List<int> argList)
{
    for (int i = 0; i < _list.Count - 1; i++)
    {
        for (int j = 0; j < _list.Count - 1 - i; j++)
        {
            if (_list[j] > _list[j + 1])
            {
                _temp = _list[j];
                _list[j] = _list[j + 1];
                _list[j + 1] = _temp;
            }
        }
    }
}
```