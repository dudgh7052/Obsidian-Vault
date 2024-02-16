---
tags:
  - CSharp
---
### Null conditinal operator
- 객체의 [[Method]]나 [[Property]] 사용하기 전에 객체가 null 인지 체크하는 경우가 많음
- C# 6.0부터 ? Null 조건 연산자를 추가
- Null 조건 연산자는 ? 앞에 있는 객체가 null인지 체크해서 null이면 null 리턴
- 아니면 다음의 [[Property]]나 [[Method]] 실행
- 따로 if문을 통해서 null 체크 할 필요 없어서 축약 가능
```C#
int? _count = _list?.Count; // _list

// 기존 null 체크
if (m_gunManager != null)
{
   m_gunManager.Shoot();
}

// Null 조건 연산자 이용 null 체크
m_gunManager?.Shoot(); // m_gunManager가 null이 아닐때만 Shoot() 호출
```

### ?? 연산자와 같이 사용
- Null 조건 연산자만 사용 시 리턴 변수는 항상 Nullable Type이여야 한다
- ?? 연산자와 사용 시 null 리턴을 막을 수 있음
- 그리고 리턴 변수형이 Nullalbe Type 일 필요가 없어짐
```C#
int _count = _list?.Count ?? 0; // _list가 null이 아니면 _list.Count 리턴 null 이면 0 리턴
```
