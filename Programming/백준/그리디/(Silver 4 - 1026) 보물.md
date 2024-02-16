---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/1026
### 삥 둘러가서 만든 풀이
```C#
int _length = int.Parse(Console.ReadLine());

List<int> _firstList = new List<int>();
List<int> _secondList = new List<int>();

_firstList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();
_secondList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();

int _sum = 0;

// 오름차순으로 정렬
_firstList.Sort();

List<int> _tempList = _secondList.ToList();
List<int> _indexList = new List<int>();

int _tempMax = 0;
int _tempIndex = 0;

// B의 큰 값이 들어있는 인덱스 순서대로 기억하기
for (int i = 0; i < _length; i++)
{
	for (int j = 0; j < _tempList.Count; j++)
	{
		if (_tempList[j] > _tempMax)
		{
			_tempMax = _tempList[j];
			_tempIndex = j;
        }
	}

    _tempList[_tempIndex] = -1;
	_indexList.Add(_tempIndex);
    _tempMax = -1;
}

for (int i = 0; i < _length; i++)
{
	_sum += _firstList[i] * _secondList[_indexList[i]];
}

Console.WriteLine(_sum);
```

### 쉽게 만든 풀이 ㅠㅠ
- B 배열 정렬하지 말라해서 한 풀이
```C#
int _length = int.Parse(Console.ReadLine());

List<int> _firstList = new List<int>();
List<int> _secondList = new List<int>();

int _sum = 0;

_firstList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();
_secondList = Console.ReadLine().Split().Select(x => int.Parse(x)).ToList();

_firstList.Sort();
_secondList.Sort();
_secondList.Reverse();

for (int i = 0; i < _length; i++)
{
    _sum += _firstList[i] * _secondList[i];
}

Console.WriteLine(_sum);
```