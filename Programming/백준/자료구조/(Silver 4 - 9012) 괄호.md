---
tags:
  - Baekjoon
  - 자료구조
---
https://www.acmicpc.net/problem/9012
```C#
// Stack<T>를 활용하여 '(' 면 넣고 ')'면 빼고
// 스택이 없는데 ')'가 오면 NO
// 다 돌았는데 스택이 있다면 NO, 없다면 YES
using System.Text;

StringBuilder _sb = new StringBuilder();
StringBuilder _answer = new StringBuilder();

int T = int.Parse(Console.ReadLine());

Stack<string> _stack = new Stack<string>();

bool _flag = false;
for (int i = 0; i < T; i++)
{
    _sb.Append(Console.ReadLine());

    for (int j = 0; j < _sb.Length; j++)
	{
        if (_sb[j].ToString() == "(")
        {
            _stack.Push(_sb[j].ToString());
        }
        else
        {
            if (_stack.Count != 0)
            {
                _stack.Pop();
            }
            else
            {
                _answer.Append("NO\n");
                _flag = true;
                break;
            }
        }
    }

    if (_flag)
    {
        _flag = false;
        _sb.Clear();
        _stack.Clear();
        continue;
    }

    if (_stack.Count == 0) { _answer.Append("YES\n"); }
    else { _answer.Append("NO\n"); }

    _sb.Clear();
    _stack.Clear();
}

Console.WriteLine(_answer);
```