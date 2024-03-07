---
tags:
  - Unity
  - UnityEditor
---
### Sprite Library Asset이란?
- 'Sprite Library'  [[Component]]에서 'Sprite Library Asset'을 바꿔주면 스킨만 바꾸고 애니메이션 적용가능
- 기존 Animator를 사용해서 Animation을 여러개 만들 때와는 다르게 'Sprite Library Asset'만 바꿔주면 됨
### Sprite Library 생성
- Asset Tab - 마우스 오른쪽 클릭 - Create - 2D - Sprite Library Asset 클릭으로 생성
### Sprite Library 설정
- 기준이 될 'Main Library'를 설정해서 Inherited(상속) 해준다
- Inherited의 Category에 해당하는 Sprite들을 넣어준다
- Local은 해당 Sprite Library Asset에만 해당하는 Category용 
![](https://i.imgur.com/LvS3iei.png)
### Sprite Resolver 와 콜라보레이션
- 오브젝트에 'Sprite Library'을 넣어주면 '[[Sprite Resolver]]' 컴포넌트에서 Category를 변경 할 수 있음
![](https://i.imgur.com/CvXVzRp.png)
