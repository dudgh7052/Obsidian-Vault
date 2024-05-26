---
tags:
  - Baekjoon
  - Collection
  - String
---
https://www.acmicpc.net/problem/15233
```C#
int[] ABG = Console.ReadLine().Split().Select(int.Parse).ToArray();
string[] _aTeam = Console.ReadLine().Split();
string[] _bTeam = Console.ReadLine().Split();
int _aGoal = 0;
int _bGoal = 0;

string[] _goalPlayer = Console.ReadLine().Split();
foreach (string _player in _goalPlayer)
{
    if (_aTeam.Contains(_player)) _aGoal++;
    else if (_bTeam.Contains(_player)) _bGoal++;
}

if (_aGoal == _bGoal) Console.WriteLine("TIE");
else { Console.WriteLine(_aGoal > _bGoal ? "A" : "B"); }
```