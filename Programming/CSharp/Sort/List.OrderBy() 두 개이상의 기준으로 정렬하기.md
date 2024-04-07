---
tags:
  - CSharp
  - Sort
---
### List.OrderBy() 두 개이상의 기준으로 정렬하기
- OrderBy() 다음 ThenBy(), ThenByDescending()를 붙여주면 된다.
- ThenBy()는 오름차순으로 ThenByDescending()은 내림차순으로 해준다.
```C#
List<(int, int)> _list = new List<(int, int)>();

int N = int.Parse(_sr.ReadLine());
for (int i = 0; i < N; i++)
{
    _input = Array.ConvertAll(_sr.ReadLine().Split(),int.Parse);
    _list.Add((_input[0], _input[1]));
}

_list = _list.OrderBy(x => x.Item1).ThenBy(x => x.Item2).ToList();
```