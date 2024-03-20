---
tags:
  - CSharp
  - String
---
### string.Join() 으로 문자열 합치기
- stringClass의 Join() 메서드를 통해 붙일 수 있음
```C#
string[] _strArray = { "Sword", "Project" };
string _joinedStr = string.Join("", _strArray);
Console.WriteLine(_joinedStr); // "Sword,Project" 출력

string _joinedStr = string.Join(",", _strArray);
Console.WriteLine(_joinedStr); // "Sword,Project" 출력
```

### string.Concat()
```C#
string[] _strArray = { "Sword", "Project" };
string _concatStr = string.Concat(_strArray);
Console.WriteLine(_concatStr); // "SwordProject" 출력
```

### StringBuilder
- StringBuilder의 AppendFormat()을 사용하면 형식에 맞게 넣기도 가능
```C#
using System.Text;

StringBuilder _result = new StringBuilder();

string[] _strArray = { "Sword", "Art", "Online" };

foreach (string str in _strArray)
{
    _result.Append(str);
}

Console.WriteLine(_result.ToString()); // "SwordArtOnline" 출력
```
