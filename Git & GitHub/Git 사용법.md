---
tags:
  - Git
  - GitHub
---
#### Git 설치 및 초기 설정
1. https://git-scm.com/ 접속
2. Git사이트의 Downloads 클릭 후 Windows 버전 설치
3. 설치 후 **Git Bash** 실행
4. 명령어 창에 이름 이메일 설정
- `git config --global core.autocrlf true`  -> Window면 true, Mac이면 input
	- Window는 CRLF로 저장했다가 LF로 전환 해줌 
- `git config --global user.name "유저이름"` 
- `git config --global user.email "깃허브 이메일"`
- `git config --list` -> 잘 들어갔나 확인 가능

#### VS Code GitHub에 파일 올리기
1. VS code에서 Terminal - New Terminal
2. Terminal탭에서 `git init` 명령어로 초기화
3. `git add .` -> GitHub에 올릴 파일 보기 `.`은 모든 파일 추가를 의미
- `git status` - 상태 알려주는 명령어
4. `git commit -m "(commit 이름)"` - Commit 하기 , Commit 히스토리 만드는 작업
5. `git remote add origin https://github.com/dudgh7052/(repository 이름).git` - GitHub와 연결
6. `git push origin master` - 보내기

#### Git 명령어
`git init` - 명령어 초기화
`git add .` - 올릴 파일 모두 추가 
`git add (File Name)` - 지정 파일 추가
`git commit -m (commit Name)` - Commit
`git remote add origin (repository Path)`-  GitHub과 연결
`git push origin master`-  보내기
`git status` - 추가 된 파일 상태 보기
`rm -rf .git` - .git 파일 삭제

##### "Does not have a commit checked out" - 에러 해결
- 이 에러는  repository 내의 다른 폴더에 ==.git 폴더==가 중복 하기 때문에 발생
- .git 폴더를 찾으려는 폴더에 들어가 숨긴 파일 표시 후 제거
  

 