---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/4796
```C#
using System.IO;
using System.Text;

StreamReader _sr = new StreamReader(Console.OpenStandardInput());
StreamWriter _sw = new StreamWriter(Console.OpenStandardOutput());

StringBuilder _sb = new StringBuilder();
StringBuilder _answer = new StringBuilder();
int[] _input = new int[3];

int L = 0;
int P = 0;
int V = 0;

int _sum = 0;

int _index = 0;
while (true)
{
    _sb.Append(Console.ReadLine());

    if (_sb.ToString() == "0 0 0")
    {
        Console.WriteLine(_answer);
        return;
    }
    

    _index++;

    _input = Array.ConvertAll(_sb.ToString().Split(), int.Parse);
    L = _input[0];
    P = _input[1];
    V = _input[2];

    _sum = (V / P) * L;
    V %= P;
    _sum += V < L ? V : L; // 남은 일수가 사용 가능한 숫자보다 작으면 남은 일수 넣고 아니면 사용 가능 일수 넣기

    _answer.AppendFormat("Case {0}: {1}\n", _index, _sum);

    // Init
    _sb.Clear();
    _sum = 0;
}
```