---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1551
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

int[] _input = Console.ReadLine().Split().Select(int.Parse).ToArray();
List<int> _list = Console.ReadLine().Split(',').Select(int.Parse).ToList();
List<int> _tmpList = new List<int>(); // 임시 저장용 리스트
int _index = _input[1];

while (true)
{
    if (_index == 0) break;

	for (int i = 0; i < _list.Count - 1; i++)
	{
		_tmpList.Add(_list[i + 1] - _list[i]);
	}

	// 리스트 초기화 후 임시 리스트에 있는 값 넣어주기
	// 다음 과정을 위한 임시 리스트 초기화
	_list.Clear();
	_list = _tmpList.ToList();
	_tmpList.Clear();

	_index--;
}

if (_list.Count == 1) // 리스트가 1개면 ,를 출력하면 안되기에 따로
{
	Console.WriteLine(_list[0]);
}
else
{
	_result.Append(_list[0]);
	for (int i = 1; i < _list.Count; i++)
	{
		_result.AppendFormat(",{0}", _list[i]);
	}

	Console.WriteLine(_result);
}
```