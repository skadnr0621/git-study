# git 명령어 학습
원활한 git 학습을 위해 정리 중입니다.

### git repository
Git Repository는 git으로 관리하는 프로젝트 저장소를 말합니다. 
- Local Repository : 본인의 컴퓨터에 저장된 로컬 버전의 프로젝트 저장소
- Remote Repository : 외부 서버 프로젝트 저장소. 프로젝트 코드 공유, 로컬 프로젝트 병합, 변경사항 적용 등 



### git repository 추가

- ``` git init```

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



mkdir 폴더명 : 폴더명으로 폴더 생성

git checkout 브랜치명 : 브랜치명으로 이동

git status 

git branch : 모든 branch 출력



### local에 정리한 내용 git add  - commit -  push

commit 이란, 프로젝트의 현재 상태를 나타내는 체크포인트 정도로 보면 됩니다. 현재 버전의 코드를 커밋에 저장한다. 

- ``` git status ```

git으로 작업 시 어떤 파일이 변경되었는지, 추가되었는지 등등 이력 확인. commit을 위해선 staging area에 추가해야한다. 위 명령어를 사용해서 git으로 관리/추적 안된 파일들을 확인하고 staging area에 추가할 수 있습니다.  입력시 빨간색으로 나오는 파일들을 추가해야 한다. 

#### git add

- ```git add . ```
- ```git add '파일이름'```

폴더 내에 있는 파일 전체 add, '.'대신 파일명을 입력해준다면 해당 파일만 staging area에 추가합니다.  **파일명은** **' '** 으로 감싸줘야 합니다. 백틱이나 ""은 안 되는 것 같습니다. 커밋 메시지는 ""로 해도되나 헷갈릴 수 있으므로 걍 ''로 해줍니다. 



#### git commit

- ``` git commit -m "커밋메시지" ```

커밋과 커밋메시지를 입력합니다. 



#### git push

- ``` git push ```

+보충 필요
add, commit을 마쳤다면, push를 해줍니다. 



####  git log

프로젝트의 커밋 내역을 확인합니다. 각 커밋에 대한 정보(작성자, 해쉬값, 날짜, 시간, 커밋메시지 등등)을 담고 있습니다. 





### git branch가 숫자로 나오는 이유??



### git branch 생성, 수정, 삭제 



### git bash로 파일 삭제해보기?



### git merge란 무엇인가



### git 브랜치 이력 확인하기 

