---
tags:
  - CSharp
---
### switch expression이란?
- switch expression은 기존 switch문에서 case break 등을 생략하여 간결하고 표현력있는 코드를 작성하게 해줌.
- C# 8.0부터 도입
- 간결성, 패턴 매칭, 리턴값 활용 등의 장점이있다.

### 프로그래밍 스타일 예시
- 'Expression-bodied members'를 활용하여 메서드를 간결화하여 활용
```C#
string _characterType = Console.ReadLine();

Console.WriteLine(CharacterSetting(_characterType));

string CharacterSetting(string argType) => argType switch
{
    "Player" => "Player Setting..",
    "Monster" => "Monster Setting..",
    _ => "Wrong Type"
};
```

- return을 활용하여 switch expression 활용
```C#
string CharacterSetting(string argType)
{
    return argType switch
    {
        "Player" => "Player Setting..",
        "Monster" => "Monster Setting..",
        _ => "Wrong Type...",
    };
}

int _firstNum = 6;
int _secondNum = 3;
int _sum = 0;

char _operator = '+';

_sum = Operation();
Console.WriteLine(_sum); // 9 출력

int Operation()
{
    return _operator switch
    {
        '+' => _firstNum + _secondNum,
        '-' => _firstNum - _secondNum,
        '*' => _firstNum * _secondNum,
        '/' => _firstNum / _secondNum,
    };
}
```

### 참고
switch expression
- https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/operators/switch-expression
Expression-bodied members
- https://learn.microsoft.com/en-us/dotnet/csharp/programming-guide/statements-expressions-operators/expression-bodied-members#methods