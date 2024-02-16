- 움직이게 될 Object에 넣고 설정 ex) Player, Monster 
![](https://i.imgur.com/DgM9chH.png)
### Property
- Agent Type - 지정하는 Type에 따라 갈 수 있는 곳과 없는 곳을 NavMeshSurface로 구분 가능하게 하는 Type
- Speed - 이동하는 속도 (초당 월드 단위)
- Augular Speed - 최대 회전 속도
- Acceleration - 최대 가속
- Stopping Dinstance - 목표 위치에 가까워졌을 때 정지하는 거리 -> Radius와 같게 하거나 이상으로 설정
- Radius - 장애물 사이를 통과하는 반경 설정 -> 캐릭터 몸통 정도 설정
- Height - 장애물 밑으로 지나가는 높이 설정
- Quality - 장애물 회피 품질 -> 낮출수록 CPU 절약
