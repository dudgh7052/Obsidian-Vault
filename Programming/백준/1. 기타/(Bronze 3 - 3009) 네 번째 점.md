---
tags:
  - Baekjoon
---
https://www.acmicpc.net/problem/3009
```C#
// 3개 중 x가 같은게 두개 있는지 체크
// 없으면 x는 그 수
// y도 똑같이 체크

int[] _input = new int[2];

List<MyVector2> _vectorList = new List<MyVector2>();
bool _isEvenX = false;

MyVector2 _dot = new MyVector2(0, 0);

for (int i = 0; i < 3; i++)
{
    _input = Array.ConvertAll(Console.ReadLine().Split(), int.Parse);
    _vectorList.Add(new MyVector2(_input[0], _input[1]));
}

if (_vectorList[0].X == _vectorList[1].X) _dot.X = _vectorList[2].X;
else if (_vectorList[0].X == _vectorList[2].X) _dot.X = _vectorList[1].X;
else _dot.X = _vectorList[0].X;

if (_vectorList[0].Y == _vectorList[1].Y) _dot.Y = _vectorList[2].Y;
else if (_vectorList[0].Y == _vectorList[2].Y) _dot.Y = _vectorList[1].Y;
else _dot.Y = _vectorList[0].Y;

Console.WriteLine("{0} {1}", _dot.X, _dot.Y);

class MyVector2
{
    public MyVector2(int argX, int argY)
    {
        X = argX;
        Y = argY;
    }

    public int X = 0;
    public int Y = 0;
}
```