---
tags:
  - CSharp
  - Pattern
  - Unity
---
### State Pattern 이란?
- Player나 Enemy 같이 상태에 따라 하는 행동이 달라지는 것들에 적용
- 상태별로 스크립트 관리가 용이해짐
![](https://i.imgur.com/AXBFC2E.png)

### State Pattern 구성 요소
- Enter() : 상태에 돌입 했을 때 호출 할 함수
- Tick(): 계속 업데이트 할 함수
- Exit(): 상태를 빠져나갈 때 호출 할 함수

### Examples
- Chase State
	- Enter()
		- Chase 애니메이션
	- Tick()
		- 플레이어한테 접근
		- 공격 할 수 있는 거리인지 체크 or 너무 멀 경우 순찰
	- Exit()
		- 없음