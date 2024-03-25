# What i learned - week1
## Why Git
버전 관리 및 협업을 위함. 에러 발생 시 저장해둔 이전 버전의 코드로 돌려둔다거나(임시)        
코드 리뷰, Github Actions로 CI/CD, Projects로 프로젝트 업무 관리 등등..이 가능하다.   

## Git
### 영역
> Working Directory, Staging Area, Repository
* Working Directory:   
add-staging 전, 실제 작업장(내 컴퓨터(?))
* Staging Area(Index):   
Repository로 저장하기 전, 대기장소 
* Repository(.git directroy):   
버전들을 저장함   

### 상태
> Untracked / Unmodified, Modified, Staged
* Untracked:   
untrecked file은 git add 명령으로 Staged 상태로 이동하며, git에 tracked될 수 있음.   
(git status 명령 - 파일 상태 확인 가능)   
(레포지토리 영역에 존재하던 파일을 remove하면 untracked상태로 돌아갈수 있다.)   
* Unmodified <-> Modified   
수정하지 않은 <-> 수정한   
마지막 커밋후에 수정한적이 없는 파일 <-> 마지막 커밋후 수정이 일어난 파일   
(modified 파일을 commit하면 수정하지 않은(unmodified) 상태로 돌아간다.)   
* Staged   
커밋을 할때 버전으로 만들어질 파일(대기 중)   

### Repository : Local <-> Remote 
* Local Repository:   
자신의 컴퓨터   
* Remote Repository:   
로컬에서의 작업물을 원격(remote)로 push 해줘야, git의 Remote Repository 서버에 반영된다.     
*<span style="color:gray">-total step: 추가하고, local에 저장하고, remote에 업로드 해야한다.(add > commmit > push)</span>*
## Git file upload
> github 공간 만들기(git init) >>> 파일 작성 후 임시저장(git add) >>> local에 저장(commit) >>> remote에 업데이트(push)   

1. git init (디렉토리에 git 저장소 만들기)
2. git remote add origin 깃허브 주소
3. git add . (모든 파일 한 번에 등록)(get on stage)   
   git add 파일명 (하나씩 등록)    
   + git rm--cached 파일명 (unstage로 돌리기)   
4. git commit (파일 수정 후 로컬 저장소로 옮김) / git commit -m "커밋 메세지"
5. git push origin main

+ rm -r .git (git 깃 관리 그만두기)

### commit message 
> "type : subject" 형식을 추천한다.
* feat (새로운 기능을 추가한 경우) 
* refactor (기존 코드를 개선한 경우) 
* fix (버그 수정한 경우)
* chore (코드 외의 설정을 바꾼 경우)
* docs (문서화)
* test (테스트 코드)

<https://github.com/dkslel1225/dkslel1225>
