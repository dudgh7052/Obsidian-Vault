---
tags:
  - Baekjoon
---
https://www.acmicpc.net/problem/1406
- 참고: https://code-piggy.tistory.com/397
- https://code-piggy.tistory.com/entry/C-LinkedListNode-%EA%B0%9C%EB%85%90-%ED%94%84%EB%A1%9C%ED%8D%BC%ED%8B%B0-%EB%A9%94%EC%84%9C%EB%93%9C-%EC%84%A4%EB%AA%85
```C#
using System.Text;

string _input = Console.ReadLine();
int M = int.Parse(Console.ReadLine());

LinkedList<char> _list = new LinkedList<char>(_input);
_list.AddLast(' ');
LinkedListNode<char> _cursor = _list.Last;

for (int i = 0; i < M; i++)
{
    string _command = Console.ReadLine();

    switch(_command[0])
    {
        case 'L':
            if (_cursor.Previous != null)
                _cursor = _cursor.Previous; // 이전 노드 가져오기
            break;
        case 'D':
            if (_cursor.Next != null)
                _cursor = _cursor.Next; // 다음 노드 가져오기
            break;
        case 'B':
            if (_cursor.Previous != null)
            {
                _list.Remove(_cursor.Previous);
            }
            break;
        case 'P':
            _list.AddBefore(_cursor, _command[2]);
            break;
    }
}
_list.RemoveLast();

StringBuilder _result = new StringBuilder();
foreach (char value in _list)
{
    _result.Append(value);
}

Console.WriteLine(_result.ToString());
```