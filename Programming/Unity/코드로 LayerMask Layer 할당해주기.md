---
tags:
  - CSharp
  - Unity
  - UnityEditor
---
### LayerMask.NameToLayer() 활용
- LayerMask.NameToLayer(LayerNameString)을 통해 레이어의 정수형 번호 반환
- '<<'(비트 시프트 연산자)를 통해 해당 레이어 인덱스 1로 바꿔주기
- 결굴 Obstacle 레이어를 체크하는 LayerMask 변수가 된다.
```C#
m_obstacleMask = 1 << LayerMask.NameToLayer("Obstacle");
```