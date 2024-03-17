---
tags:
  - CSharp
  - String
---
### 1. string.Format()
- Console.WriteLine()도 string.Format() 기반임
- [[Addressable]] 의 폴더 형식을 미리 string 타입에 저장해두고 불러올 때 활용 가능
```C#
string _format = string.Format("{0}{1}{2}", _value0, _value1, _value2); // ','뒤에 순서대로 넣어주기
Console.WriteLine(_format);
string _format = _value.ToString("F2"); // Tostring()도 가능

// 미리 string타입으로 형식 지정해놓고 사용
string m_loadKey = "Assets/ImageData/{0:G}/{0:G}Lib/{0:G}_{1:D}.spriteLib";
public string GetAddressableKey (KeyType.Type argKeyType, LoadType.TYPE argLoadType, int argLoadIndex)
{
    return string.Format(m_loadKey, argLoadType.ToString(), argLoadIndex);
}
```

### 2. 문자열 보간
- '$'를 앞에 붙이고 '{ }'사이에 변수를 넣어주면 된다.
- C# 6.0부터 도입
```C#
string _format = string.Format($"{_value}"); // '$'를 넣어 보간
Console.WriteLine(_format);
```

### 3. 문자열 서식 지정
```C#
string _format = string.Foramt("{0:형식지정}" , _value) // string.Format도 똑같이 지정해주면 됨
$"{_value: 10}" // 10칸 범위 내에서 우측 정렬
$"{_value: -10}" // 10칸 범위 내에서 좌측 정렬
$"{_value:000}" // 자릿수 지정, 세번째 자리까지 채워서 표현(빈 칸은 0으로 채움), 실수는 반올림 후 정수표현
$"{_value:0.00}" // 정수는 첫째자리까지 반드시 표현, 소수는 둘째자리까지 반드시 표현
$"{_value:X}" // 16진수 표현, 정수 아닐 시 예외, 알파벳 대문자로 표현, 63 -> 3F
$"{_value:x}" // 16진수 표현, 정수 아닐 시 예외, 알파벳 소문자로 표현, 63 -> 3f
$"{_value:X5}" // 대문자  16진수 표현, 자릿수 지정, 63 -> "0003F" 출력
$"{_value:F2}" // 정수, 실수를 F뒤의 숫자 자릿수까지 소수점 출력, 100 -> "100.00" 출력
$"{_value:N2}" // 세 자리수 구분자 표현, 소수자리도 숫자에 따라서, _value = 1000 -> "1,000.00" 출력
$"{_value:00.00%}" // 백분율 표현, 값에 100을 곱한 후 표현, 0.245 -> "24.50%", 5 -> "500.00%" 출력
("{0:#.##}", _value) // 1234.5678 -> 1234.56 출력
("{0:#,#.##}", _value) // 1234.5678 -> 1,234.56 출력, 자릿수 지정 및, 소수점 두자리 표현
("{0:0,0.00}" _value) // 1234.5678 -> 1,234.56 출력, 자릿수 지정 및, 소수점 두자리 표현
```

### 4. 자릿수 지정을 변수로 
```C#
// "{0, 자릿수}" 이 부분을 + 연산자로 이어붙이기 하여 자릿수 지정가능
int _variableLength = 15;
string _str = string.Format("{0," + _variableLength + "}", "IsekaiElf");
Console.WriteLine(_str); // "      IsekaiElf" 출력
```