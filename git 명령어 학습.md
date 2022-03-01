# 🙉 git 명령어 학습
원활한 git 학습을 위해 정리 중입니다.



### git repository

Git Repository는 git으로 관리하는 프로젝트 저장소를 말합니다. 
- Local Repository : 본인의 컴퓨터에 저장된 로컬 버전의 프로젝트 저장소
- Remote Repository : 외부 서버 프로젝트 저장소. 프로젝트 코드 공유, 로컬 프로젝트 병합, 변경사항 적용 등 




### git repository 추가

``` git init```

프로젝트 폴더에 숨겨진 .git 폴더를 만들고 Git에서 repository에 대한 모든 변경사항 관리

- vi 파일명

파일명을 가진 임의의 파일을 생성




###  git repository 삭제 

1. git에 접속해서 해당 레포지토리에 들어간다. 
2. Settings - 하단 Danger Zone - Delete this repository 
3. please 뒤의 문구(제거할 레포지토리명) 작성 - delete 클릭
4. password 입력
5. 삭제 완료




### git repository에서 폴더 삭제

``` 
	git rm -rf [폴더 & 파일명]
	git commit -m "romove folder&file"
	git push origin main 
```

git rm -rf : 원격 저장소(remote repository)와 로컬 저장소(Local repository)를 모두 지우는 명령어
git rm -r --cached : 원격 저장소 내의 파일만 지우는 명령어



### git clone

```
명령어 정리해서 과정이랑 적어주세요.
```

원격 저장소를 내 컴퓨터에 복사해온다. 




### git 폴더 만들기

```
mkdir 폴더명
```



### git branch : 생성, 수정, 삭제, 이력 확인

```
git checkout branch_name : branch 변경, 변경하기전에 commit push를 진행해야 한다.
git branch : 모든 branch 출력
```

기본적으로 master 브랜치로 작업을 진행하게 된다. 브랜치의 경우, 각기 다른 작업을 할 때 용이합니다. 가상의 작업 환경이라 보면 좋습니다. 

- 깃에서는 한번에 하나의 브랜치에서만 작업이 가능합니다. 이를 HEAD 브랜치라고 부릅니다. 



### git refresh, git status

```
git fetch
git status 
```
git으로 작업 시 어떤 파일이 변경되었는지, 추가되었는지 등등 이력 확인. commit을 위해선 staging area에 추가해야한다. 위 명령어를 사용해서 git으로 관리/추적 안된 파일들을 확인하고 staging area에 추가할 수 있습니다.  입력시 빨간색으로 나오는 파일들을 추가해야 한다. 

status 명령어를 통해서 현재 git 상태를 확인한다. 

### git log --oneline
git branch을 가시적으로 확인한다. 



### local의 내용 git에 올리기 : git add  - commit -  push

commit 이란, 프로젝트의 현재 상태를 나타내는 체크포인트 정도로 보면 됩니다. 현재 버전의 코드를 커밋에 저장한다. 

#### 1. git add

- ```git add . ```
- ```git add '파일이름'```

폴더 내에 있는 파일 전체 add, '.'대신 파일명을 입력해준다면 해당 파일만 staging area에 추가합니다.  **파일명은** **' '** 으로 감싸줘야 합니다. 백틱이나 ""은 안 되는 것 같습니다. 커밋 메시지는 ""로 해도되나 헷갈릴 수 있으므로 걍 ''로 해줍니다. add는 내 컴퓨터에 작업한 파일을 스테이지에 추가하는 기능을 합니다. 

#### 2. git commit

- ``` git commit -m "커밋메시지" ```

커밋과 커밋메시지를 입력합니다. comiit은 스테이지에 올라온 파일들을 가지고 내 컴퓨터에 저장합니다. 

#### 3. git comit 취소, 되돌리기, 덮어쓰기

- **커밋 취소 reset**

  - ``` java
    git reset --hard COMMITID
    ```

    HEAD가 이전 커밋을 가리키도록 합니다. --hard 옵션은 현재 헤드에서 추가된 변경사항들을 모두 되돌려줍니다. git reflog 기능도 나중에 공부해보세요.

  - git에서 관리하지 않는 파일들까지 삭제하고자 하는 경우 git clean 명령어를 따로 실행해야 합니다.  여긴 이해가 안가서 나중에 따로 찾아보고 이해해야 할듯

    - ```git clean -n```
      - 삭제 대상 목록(Untracked files ) 확인

    - ```git clean -f```
      - Untracked files 파일 삭제

- **커밋 되돌리기 revert**

  - head 위치를 바꿔버려서 로컬 저장소의 상태를 커밋 이전 상태로 강제 변경해줍니다. 커밋을 push 해버린 경우에 실행하면 상태가 틀어져버립니다. 

  - ``` java
    git revert COMMITID
    ```

    기본 메시지를 그대로 저장하고 에디터를 종료합니다. 

  - https://www.lainyzine.com/ko/article/git-revert-reverting-commit-in-git-repository/
    링크를 통해서 심화학습을 진행해보세요.

- **커밋 덮어쓰기 amend**

  - 커밋의 내용을 덮어쓸 때는 amend 옵션을 사용합니다.

  - ``` java
    git commit --amend
    ```

    메시지 작성후 저장해주면 완료됩니다.  amend 옵션의 경우 스테이징에 추가된 내용을 반영해주는 동시에 커밋 메시지도 변경해줍니다. 따라서 변경 내용이 없을 때도 커밋 메시지를 변경하고 싶을때 사용합니다. 

    


#### 4. git push

- ``` git push ```

+보충 필요
add, commit을 마쳤다면, push를 해줍니다. commit된 내역을 원격 저장소(현 branch)에 업로드합니다. 

####  5. git log

프로젝트의 커밋 내역을 확인합니다. 각 커밋에 대한 정보(작성자, 해쉬값, 날짜, 시간, 커밋메시지 등등)을 담고 있습니다. 







### git branch가 숫자로 나오는 이유??



### git bash로 파일 삭제해보기?



### git merge(병합)

한 브랜치의 내용을 다른 브랜치에 반영할 때 사용한다. 





