---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/5218
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();

int N = int.Parse(Console.ReadLine());

for (int i = 0; i < N; i++)
{
    string[] _input = Console.ReadLine().Split();

	_sb.Append("Distances:");

	for (int j = 0; j < _input[0].Length; j++)
	{
		int _num1 = _input[0][j] - 64;
		int _num2 = _input[1][j] - 64;

		int _distance = _num1 > _num2 ? (_num2 + 26) - _num1 : _num2 - _num1;
		_sb.AppendFormat(" {0}", _distance);
	}

	_sb.Append("\n");
}

Console.WriteLine(_sb);
```