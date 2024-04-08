## <p style="text-align:center;">개발 입문 스터디 Quiz 1</p>

#### Example
GDSC는 무엇의 약자인지 적으시오.

- 답: Google Developer Student Clubs

### Q1
Git에서 파일의 상태는 크게 untracked와 tracked로 나눌 수 있다.  
그렇다면 tracked에는 어떤 상태가 있는지 모두 적으시오.

- 답: Staging area, local repo, remote repo 영역에서 파일은 tracked 상태로 존재한다. 
- git status로 파일 상태를 확인했을때, commit 또는 push를 기다리는 상태임을 볼 수 있다. (예-changes to be comitted..)

### Q2
Git에는 세 가지 영역이 있다.  
세 가지 영역을 모두 나열하시오.

- 답: Working directory, Staging area, Repository(local/repo)

### Q3
현재 우리는 ```main```브랜치에 있다.  
```develop```이라는 브랜치를 새로 만들고 이동까지 한번에 할 수 있는 명령어를 적으시오.

- 답: git checkout -b (branch이름)

### Q4
Working Directory에 있는 파일들을 모두 Staging Area에 추가할 수 있는 명령어를 적으시오.

- 답: git add .

### Q5
```
1. Create a merge commit
2. Squash and merge
3. Rebase and merge
```
위의 세 가지가 어떤 차이가 있는지 간단히 적으시오.

- 답:
- 1. merge 하려는 두 브랜치를 공통 부모로 하는 새로운 commit ‘’을 만든다. 커밋 이력과 branch 히스토리가 남는다.
- 2. 지난 커밋을 squash 하여, 하나의 새로운 커밋으로 main 브랜치로 병합한다.
- 3. merge 될 커밋의 base를 재설정하며, 모두 새로운 커밋으로 변경한다. 커밋 해시가 변경되어 충돌이 생길 위험이 큼.

### Q6
```git log --oneline```으로 commit의 기록을 확인해보니  
첫 줄에 ```a1s2d3f (HEAD -> develop) docs: readme 추가```라는 log가 찍혔다.
알 수 있는 사실을 모두 적으시오.

- 답: 가장 최근 commit id: a1s2d3f.... / 현재 작업중인 위치: develop / commit message: readme.md(문서 작업) 추가했음

### Q7
```git log --oneline```으로 commit의 기록을 확인해보니 아래와 같은 log를 확인 할 수 있었다.  
```
a1s2d3f (HEAD -> develop) fifth commit
s2d3f4g fourth commit
345hj26 third commit
7g8dg7f second commit
5g568vk first commit
```
이때, fourth commit까지 제거하고 fourth commit과 fifth commit의 변경 사항은
Staging Area에 남아 있길 바란다면 reset을 어떤 옵션과 함께 사용하면 되는지 적으시오.

- 답: 
- git reset --soft 345hj26 
- (4,5 커밋 취소, 변경 사항은 staging area로)

### Q8
```git log --oneline```으로 commit의 기록을 확인해보니 아래와 같은 log를 확인 할 수 있었다.
```
a1s2d3f (HEAD -> develop) fifth commit
s2d3f4g fourth commit
345hj26 third commit
7g8dg7f second commit
5g568vk first commit
```
reset은 너무 위험하니 revert를 사용하려고 하여 ```fifth commit```을 되돌리고 싶다면 
어떤 명령어를 사용하면 되는지 적으시오. 

- 답: git revert a1s2d3f

### Q9
여러 사람이 협업하는 프로젝트에서 커밋을 되돌려야 한다.  
reset과 revert 중에 어떤 것을 선택할 것인지를 그 이유와 함께 적으시오.

- 답: revert
- 커밋을 아예 삭제하는 단계를 거치는 리셋보다는, revert가 안전하기 때문이다. 