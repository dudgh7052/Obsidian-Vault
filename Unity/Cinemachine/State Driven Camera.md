---
tags:
  - Unity
  - UnityEditor
  - Cinemachine
---
### State Driven Camera란?
- 특정 상태나 조건에 따라 카메라의 동작을 제어 해줌
- 게임의 상황, 상태에 따라 위치, 회전, 확대/축소 등을 자동으로 조정해줌
- 'Animated Target' 에 넣어준 애니메이터의 애니메이션 기준으로 State에서 바꿔 줄 수 있음
![](https://i.imgur.com/j3E6vDX.png)
### Properties
Animated Target - 기준으로 삼을 애니메이터 컨트롤러
Layer - Animated Target에서 관찰 할 Layer
Default Blend - Virtual Camera끼리의 블렌드
State - 애니메이션 상태에 따라 사용 할 카메라 선택
Virtual Camera Children - StateDrivenCamera에서 사용 할 Camera 목록

### 참고
- https://docs.unity3d.com/Packages/com.unity.cinemachine@2.3/manual/CinemachineStateDrivenCamera.html
