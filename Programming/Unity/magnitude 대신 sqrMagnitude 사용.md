---
tags:
  - Unity
  - CSharp
---
- 높은 정밀도를 요구하는 상황이 아니면 'sqrMagnitude'를 사용
- 'magnitude' 는 제곱근, 'sqrMagnitude'는 제곱값 반환 Property
```C#
Vector3 a = new Vector3(10f, 5f, 20f);
Vector3 b = new Vector3(20f, 30f, 50f);
Vector3 c = new Vector3(20f, 50f, 10f);

// 느림
if ((b - a).magnitude < (c - a).magnitude){}

// 빠름
if ((b - a).sqrMagnitude < (c - a).sqrMagnitude){}

// 메소드의 경우
float _magnitude = Vector3.Distance(a , b);
float _sqrMagnitude = Vector3.sqrMagnitude(b - a); // 빠름
```

![](https://i.imgur.com/ZSQ6gE2.png)
- sqrMagnitude는 루트 부분을 계산 안하기에 빨라진다.