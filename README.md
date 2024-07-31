# Git

## 깃 명령어
- git branch 브랜치명 : 브랜치 생성
- git checkout 브랸치명 : 브랜치 설정
- git add . : 모든 파일 설정
- git commit -m '[#이슈번호] 설명' : 커밋 메시지
- git push origin 브런치명 : 커밋
- git status
- git init
- git pull origin 브랜치명 : 깃 코드 받아오기
- git fetch 는 확인만 한다
- git log : 커밋 히스토리
- git clone url : 원격 저장소로부터 복제
- git merge
  - git branch --merged 
  - git branch --no-merged
### 커밋 취소
* git reset HEAD^ : 마지막 커밋을 삭제
* git reset --hard HEAD :  마직막 커밋 상태로 되돌리기
* git reset HEAD * : 스테이징을 언스테이징으로 변경
---
## git-flow
git branch 관리 방식 중 하나로 협업 시 branch를 보다 효율적으로 관리하기 위해서 사용한다
## branch 구성
git-flow는 5가지의 브랜치로 구성되어있다.
master(main): 배포할 수 있는 브랜치(출시용)
develop: 개발용 브랜치로 feature에서 구현한 기능들을 합치는 브랜치
feature: 기능을 단위별로 나눠서 개발하는 브랜치
release: 출시할 버전에 이상이 없는지 확인하는 준비하는 브랜치
hotfix: 출시 후 버그 발생 시 긴급 수정하는 브랜치
