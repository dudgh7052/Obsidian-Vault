- Joystick을 사용 하기 위해서는 [[Input System]]을 Project에 Import 해야 함 
### Input System Import 하기
1. Unity Editor 실행
2. Unity Tap - Window - Package Manager 클릭
3. Package Manager Tap - Packages - Unity Registry 클릭
4. Search 에서 ==Input System== 검색
5. Import 눌러서 Input System 프로젝트로 가져오기

### Joystick 가져오기 
1. Package Manager - In Project - Input System 클릭
2. Samples - =='On-Screen Controls Import'== -> 화면에서 Joystick, Button 조작이 포함된 Sample
3. Import 시 Samples - Input System - Version Folder - On-Screen Controls 폴더 열기
4. =='Stick''== Prefab을 사용 할 Canvas에 넣기
5. On-Screen Stick Component에서 Property 수정 후 사용

### On-screen Stick
![](https://i.imgur.com/22FIl6V.png)
 - ### Property
	- Movement Range - Stick의 최대 이동 거리
	- Control Path - 매치 시킬 Input Actions에 설정 한 Binding
