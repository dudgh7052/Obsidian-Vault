---
tags:
  - Baekjoon
  - 브루트포스
---
https://www.acmicpc.net/problem/2798
```C#
// 하나씩 다 돌아보기
int[] _input = Console.ReadLine().Split().Select(x => int.Parse(x)).ToArray();
int N = _input[0];
int M = _input[1];

int _max = 0;

List<int> _cards = Console.ReadLine().Split().Select(int.Parse).ToList();

for (int i = 0; i < _cards.Count; i++)
{
    for (int j = i + 1; j < _cards.Count; j++)
    {
        for (int k = j + 1; k < _cards.Count; k++)
        {
            int _sum = _cards[i] + _cards[j] + _cards[k];
            
            if (_sum <= M && _sum > _max)
            {
                _max = _sum;
            }
        }
    }
}

Console.WriteLine(_max);
```