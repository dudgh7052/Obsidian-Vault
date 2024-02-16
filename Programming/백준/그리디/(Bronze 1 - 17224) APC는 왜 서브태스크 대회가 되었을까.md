---
tags:
  - Baekjoon
  - Greedy
---
https://www.acmicpc.net/problem/17224
```C#
// 첫 줄에 문제 수 = N, 현정이의 역량 = L, 풀 수 있는 최대 갯수 = K
// 둘째 줄부터 N개의 줄에 걸쳐 1 ~ N번째 문제의 쉬운 버전의 난이도 sub1, 어려운 버전의 난이도 sub2 가 순서대로 주어진다.
// 어려운거부터 역량과 비교 후 되면 140점 추가, 안되면 쉬운버전 비교 후 100점 추가
int[] _input = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);
int N = _input[0];
int L = _input[1];
int K = _input[2];
int _increaseScore = 0;
int _score = 0;

int[] _input1 = new int[2];
List<Problem> _list = new List<Problem>();
for (int i = 0; i < N; i++)
{
    _input1 = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);
    _list.Add(new Problem(_input1[0], _input1[1]));
}

_list = _list.OrderBy(x => x._hard).ThenBy(x => x._easy).ToList();

for (int i = 0; i < _list.Count; i++)
{
    if (K == 0) break;
    if (L < _list[i]._hard && L < _list[i]._easy) continue;

    if (L >= _list[i]._easy)
    {
        _increaseScore = 100;

        if (L >= _list[i]._hard)
        {
            _increaseScore = 140;
        }
    }

    _score += _increaseScore;
    K--;
}

Console.WriteLine(_score);

class Problem
{
    public Problem(int argEasy, int argHard)
    {
        _easy = argEasy;
        _hard = argHard;
    }

    public int _easy = 0;
    public int _hard = 0;
}
```