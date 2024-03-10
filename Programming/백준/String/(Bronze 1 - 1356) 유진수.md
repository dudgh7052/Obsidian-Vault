---
tags:
  - Baekjoon
  - String
---
https://www.acmicpc.net/problem/1356
```C#
string _input = Console.ReadLine();

int _index = 0;
int _sum1 = 0;
int _sum2 = 0;
bool _flag = false;

while (true)
{
    if (_index > _input.Length - 2) break;

    // 0번 부터 현재 인덱스의 + 1까지 가져오기
    char[] _char1 = _input.Substring(0, _index + 1).ToCharArray();
    // 그 나머지 가져오기
    char[] _char2 = _input.Substring(_index + 1, _input.Length - (_index + 1)).ToCharArray();
    _sum1 = Multiple(_char1);
    _sum2 = Multiple(_char2);

    // 같은게 있으면 빠져나오기 없으면 계속 반복
    if (_sum1 == _sum2)
    {
        _flag = true;
        break;
    }

    _index++;
}

if (_flag) Console.WriteLine("YES");
else Console.WriteLine("NO");

int Multiple(char[] argCharArray)
{
    int _tmpSum = 1;
    foreach (char _char in argCharArray)
    {
        // 아스키코드 이용해서 바꿈없이 바로 곱해주기
        _tmpSum *= _char - 48;
    }

    return _tmpSum;
}
```