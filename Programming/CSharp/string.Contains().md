---
tags:
  - CSharp
  - String
---
### 기본 사용법
- 기본적으로는 string 타입에 Contains(찾을 문자열) 을 넣어주면 True or False 반환
```C#
string _input = "Hello Wolrd";
if (_input.Contains("Hello")) // True 반환 
```
### 대소문자 구분없이 문자열 여부 체크
- Contains(찾으려는 문자열, StringComparision.OrdinalIgnoreCase) 를 넣어주면 됨
```C#
string _input = "Hello World!";
Console.WriteLine(_input.Contains("hello", StringComparison.OrdinalIgnoreCase)); // True 출력
```