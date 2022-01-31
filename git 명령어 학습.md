# git 명령어 학습
원활한 git 학습을 위해 정리 중입니다. 

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



### local에 정리한 내용 git add commit push

git add . 

git commit -m ""

git push
