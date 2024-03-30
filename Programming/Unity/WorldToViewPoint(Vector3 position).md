---
tags:
  - Unity
  - CSharp
---
### WorldToViewPoint(Vector3 position) 란?
- 게임 오브젝트의 월드 좌표를 카메라의 뷰포트 좌표로 변환해주는 함수
- x, y가 0보다 작을 경우와 1보다 클 경우에는 카메라 화면 밖에 위치하고 있다는 것
- 특정 조건의 게임 오브젝트만 모아두고 구하면 될듯
### 제일 가까운 타겟 구하기
```C#
Target _closestTarget = null; // 제일 가까운 타겟 저장용 변수
float _closestTargetDistance = Mathf.Infinity; // 제일 가까운 타겟거리 저장용, 부동소수점 최대값 저장

foreach (Target target in m_targets)
{
    // Viewport 밖에 있는지 체크 x, y가 0보다 작을 경우와 1보다 클 경우 Viewport 밖 나타냄
    Vector2 _viewPos = m_mainCamera.WorldToViewportPoint(target.transform.position);

    if (_viewPos.x < 0 || _viewPos.x > 1 || _viewPos.y < 0 || _viewPos.y > 1) continue;

    // camera의 센터(0.5f, 0.5f)에서의 거리 구하기
    // new Vector2(0.5f, 0.5f)가 뷰포트의 중앙을 나타냄 
    Vector2 _toCenter = _viewPos - new Vector2(0.5f, 0.5f);

    // sqrManitude를 통해서 벡터의 제곱값을 기존 타겟의 거리와 비교 후 바꿔주기
    if(_toCenter.sqrMagnitude < _closestTargetDistance)
    {
        _closestTarget = target;
        _closestTargetDistance = _toCenter.sqrMagnitude;
    }
}
```