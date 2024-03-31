# What i learned - week2
## Fork
다른 사용자의 Repository를 자신의 계정으로 복사하여 독립적으로 수정하고 관리하는 것이다.    
오픈 소스 프로젝트를 공부하거나 기여자가 되고 싶을 때, 해당 원격 저장소(remote repository)를 복사해올 수 있다.
## Star
킵해두고 싶은 Repository나 프로젝트에 star를 눌러서 "북마크"와 같이 관리할수 있다.   
## Issue
Repository에서 작업 계획, 토론 및 추적을 위해 활용   
(어떠한 이슈가 있었는지..)
## Branch 
기존 브랜치(main)에서 분기되어 생성되는 별도의 작업 공간   
> <관련 명령어>
> * git branch              : 현재 브랜치 확인
> * git branch -a           : 모든 브랜치 확인
> * git branch "branch name.."      : 브랜치 생성
> * git checkout "branch name.."    : 브랜치 이동
> * git checkout -b "branch name.." : 브랜치 생성 후 이동
> * git branch -D "branch name.."                 : 로컬 브랜치 삭제
> * git push 원격저장소이름(주로origin) -d 브랜치이름..   : 원격 브랜치 삭제
### Branch Naming Convention
“type/<issue 번호>-<간략한 설명>”   
이번 실습의 경우, (문서작업)/1(이슈 번호)-(설명), docs/1-readme로 작성함
### Pull Request
분기되어있는 브랜치를 병합한다     
새로운 변경을 제안하거나 병합 시 발생하는 충돌을 해결함(당장 Merge를 하지 않을 수 있다)   
Merge 전 코드 리뷰 가능
## Merge
> 옵션 3가지: Create a merge commit / Squash and merge / Rebase and merge
> 
> Merge하다 충돌 생기는 경우가 많아서.. 모르겠을때는 Create a merge commit을 추천..
1. Create a merge commit : A,B,C..커밋들을 새로운 커밋으로 합친다. 즉, 두 브랜치를 공통 부모로 하는 새로운 commit ‘E’를 만든다.(main 브랜치로 병합)
2. Squash and merge : main 브랜치에 있는 하나의 커밋으로 합친다.
3. Rebase and merge : A,B,C.. 커밋들의 base를 재설정한다. main 브랜치로 가지만 모두 새로운 커밋으로 변경된다.   
commit hash가 변경되기에 merge후 충돌 발생 위험이 크다.    
참고:: commit hash==commit id(commit 식별 주소), SHA-1 해시 함수를 사용

## 2주차 실습
> git log : 지난 커밋 메세지 확인 가능
1. issue 만들어보기
2. main에서 분기되는 branch 만들기(docs/1-readme) - 그 브랜치에 README.md 작성 - add, commit, push -
3. Pull Request 만들어서 base:main으로 docs/1-readme 를 Merge 하기
> 실습 일지
> "main and - are entirely different commit histories." 오류를 해결하는 과정에서
> origin 과 main, main을 기반으로 분기되어 나오는 branch의 개념을 직접 이해할수 있었다... 

## 실습 링크
https://github.com/dkslel1225/2024-1-Beginner-Study/pull/2
