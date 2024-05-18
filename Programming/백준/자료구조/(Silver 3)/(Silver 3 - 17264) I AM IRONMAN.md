---
tags:
  - Baekjoon
  - Collection
---
https://www.acmicpc.net/problem/17264
```C#
var _winPlayer = new HashSet<string>();
var _losePlayer = new HashSet<string>();

bool _flag = false;
int _lp = 0;

int[] NP = Console.ReadLine().Split().Select(int.Parse).ToArray();
int[] WLG = Console.ReadLine().Split().Select(int.Parse).ToArray();

while (NP[1]--> 0)
{
    HackingPlayer();
}

while (NP[0]-- > 0)
{
    PlayGame();

    if (_lp >= WLG[2]) _flag = true;
}

Console.WriteLine(_flag == true ? "I AM NOT IRONMAN!!" : "I AM IRONMAN!!");

void HackingPlayer()
{
    string[] _player = Console.ReadLine().Split();

    switch (_player[1])
    {
        case "W":
            _winPlayer.Add(_player[0]);
            break;
        case "L":
            _losePlayer.Add(_player[0]);
            break;
    }
}

void PlayGame()
{
    string _player = Console.ReadLine();

    if (_winPlayer.Contains(_player))
    {
        _lp += WLG[0];
        return;
    }

    _lp -= WLG[1];
    if (_lp <= 0) _lp = 0;
}
```