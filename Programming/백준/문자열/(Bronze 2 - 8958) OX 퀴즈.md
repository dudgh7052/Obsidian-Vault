---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/8958
```C#
using System.Text;

StringBuilder _sb = new StringBuilder();
StringBuilder _answer = new StringBuilder();

int _count = int.Parse(Console.ReadLine());

int _sum = 0;
int _index = 0;

for (int i = 0; i < _count; i++)
{
    _sb.Append(Console.ReadLine());

	for (int j = 0; j < _sb.Length; j++)
	{
		// X일 경우 초기화
		if (_sb[j] == 'X')
		{
			_index = 0;
		}
		else // O일 경우
		{
			_index++;
			_sum += _index; // 누적 시키기
		}
	}

	_answer.AppendFormat("{0}\n", _sum);

	// Init
	_sum = 0;
	_index = 0;
	_sb.Clear();
}

Console.WriteLine(_answer);
```
