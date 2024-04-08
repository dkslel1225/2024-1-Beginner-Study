# What i learned - week3
## 사전지식
### git log
 commit 기록을 최신 순으로 확인, commit id의 맨 앞 7자리 확인 가능   
 --oneline 옵션을 사용하면 각 커밋을 한 줄에 요약   
### Commit ID
commit의 식별을 위해 사용하는 40자 길이의 16진수     
SHA-1 해시 함수를 사용하여 생성됨   
### HEAD
HEAD -> 현재 작업 중인 위치를 가리킴   
현재 작업중인 브랜치의 가장 최근 commit    
다음 commit의 base가 되는 commit   
새로운 commit이 생기면 HEAD도 변경(최신 커밋이 현재 작업중인 위치일테니까)   
## git status
> Changes to be committed:      (in staging area / commit 필요)   
> Changes not staged for commit:(modfied / add 필요)   
> Untracked files:              (in working directory / add 필요)
> 영역: working directory, staging area, repository

## 커밋 되돌리기
### amend
> git commit --amend

마지막 commit의 내용에 변경이 있을 때 사용   
완전히 새로운 commit으로 대체 >> commit id가 바뀜     

- git commit --amend -m “커밋 메시지”
‘-m’ option으로 vim 진입 없이 commit 메시지 수정하기    
- git commit --amend --no-edit
‘--no-edit’ option으로 commit 메시지 수정 없이 commit 수정  
### reset
> git reset --

commit을 아예 '제거'하는 데 사용   
돌아갈 commit의 id를 사용
  
#### reset의 3가지 옵션
< soft, mixed(default), hard >   

- reset --soft : 커밋만 취소, 변경 사항이 로컬레포에서 Staging Area로 돌아감 (changes to be comitted..)
- reset --mixed : 커밋을 취소, 변경 사항이 working directory로 돌아감 (changes not staged for commit..)
- reset --hard : 커밋 취소, 변경 사항을 모두 제거하고 이전 커밋으로 돌아감 
> ex) git reset --soft a1s2d3f 
### revert
> git revert --

commit을 제거하지 않고, 되돌림   
되돌리기 위한 새로운 commit이 생성됨       
--edit 옵션이 default    
> ex) git revert --no edit "commit id" >>  편집기 진입 없이 바로 revert 
> ex) git revert --no commit  "commit id" >>  직접 커밋하지 않고,  revert 내용을 staging area에 올림 

### reset vs revert
reset은 commit을 삭제함
revert는 commit을 삭제하기보다 생성하여 되돌림
reset이라면 A가 그냥 없어졌겠지만.. revert는 A'로 남는다.
, 주로 revert를 사용하게됨(리셋은 충돌 위험이 있어서)
