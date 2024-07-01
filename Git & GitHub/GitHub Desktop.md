---
tags:
  - Git
  - GitHub
  - Unity
---
### GitHub Desktop이란?
- SourcesTree와 비교 했을 때 기능과 작업이 적다.
- 그러나, Unity or Unreal Engine 프로젝트 파일을 GitHub에 올리기에 적당

### GitHub와 GitHub Desktop 연동
1. 'GitHub Desktop' 실행
2. File - Clone repository 클릭
3. Your repositories에서 Repository 선택
4. 미리 폴더 만들어 놓고,  'Local Path'에서 해당 폴더 선택
5. 폴더에 [[UnityEvent로 커스텀 이벤트 만들기]] 프로젝트 복사 후 'Changes'에서 확인 가능
6. 'Summary'에 코멘트 달고, 'Commit to main' 클릭
7. 'Push Origin' 클릭 - GitHub에 업데이트
8. GitHub Push 완료

### GitHub Desktop Push
1. 'Summary'에 코멘트 달고, 'Commit to main' 클릭
2. 'Push Origin' 클릭 - GitHub에 업데이트
3. GitHub Push 완료

### Collaborating (협업 설정)
1. GitHub의 해당 'Repository' 열기
2. Setting -  Collaborators - Add people 순으로 클릭
3. 'Add people' 창의 Input Place에 'username or email' 입력
4. 'Select a collaborator above' 클릭
5. collaborator는 '이메일에서 초대 확인' 가능
### Collaborator Pull (파일 가져오기)
1. GitHub Desktop 실행
2. File - Clone repository - 해당 Repository 찾기 - 'Local path' 설정 - 'Clone' 클릭
3. UnityHub 에서 Project 열기
### Branch (나뭇가지 만들기)
1. GitHub Desktop 실행
2. Current Branch - Input Place에 branch 이름 설정 - New branch - Create branch
3. Publish branch 클릭 -> GitHub Repository branches 탭에서 확인 가능
### Pull request Merge (합치기)
1. =='GitHub'== 열기
2. =='Pull request'== 탭 클릭
3. =='New pull request'== 클릭
4. 'Compare  changes'에서 ==base:main <- compare: (해당 branch)== 설정
5. 변화 확인 (Comparing changes)
6. 'Create pull request' - Comment 설정 - 'Create pull request'
7. 'Merge pull request' - 'Confirm merge' 순 클릭으로 합치기
8. merge 완료 - =='Delete branch'== 클릭 시 branch 삭제 가능
9. =='GitHub Desktop'== 실행
10. =='Fetch origin'== - =='Pull origin'== 클릭으로 Local에 변경 사항 적용 후 프로젝트 진행

### Unity 프로젝트 공유 시 용량 절감하기
- Assets, Packages, ProjectSettings 빼고 다 삭제 