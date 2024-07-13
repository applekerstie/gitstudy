# git

# 1. 설치
```
https://git-scm.com
https://www.sourcetreeapp.com
```

# 2.
```
git --version

git config --global user.name "applekerstie"
git config --global user.email "applekerstie@gmail.com"
git config --global --list

git init
ls -a
```

# 3. .gitignore
```
저장소 폴더 최상위 디렉터리에 위치
dbinfo.php
*.obj

# config.php는 제외하면 안됨
!config.php

/readme.txt

writable/

# doc 다랙터리 아래 모든 .txt파일 무시
doc/**/*.txt
```

# 4. 스테이지 영역에 파일 등록 (tracked 상태)
```
git add .

# 상태확인
git status

# 파일등록취소
git rm --cached index.htm

# 커밋을 한번이라도 한 파일이라면 reset으로 커밋을 정리한다
git reset HEAD index.htm
```

# 5. 파일 이름을 변경
```
git mv index.htm home.htm

=

mv index.htm home.htm
git rm index.htm
git add home.htm
```

# 6. 커밋
```
git commit -m 'commit message'

# 스테이지 영역으로 파일 등록하고 커밋
git commit -am 'commit message'

# 커밋 로그 확인
git log

# 커밋 메세지를 작성하지 않고 커밋
git commit --allow-empty-message -m ""
```

# 7. 수정한 파일을 이전 커밋으로 되돌리는 명령어
```
git checkout -- index.htm

소스트리: 파일변경사항폐기
```

# 8. 
```
# 첫번째 커밋 메세지만 출력하여 로그 확인
git log --pretty=short

# 특정파일의 커밋 로그 확인
git log index.htm
```

# 9.
```
# 스테이지와 워킹디렉터리 비교
git diff

# 스테이지에 등록한 후 스테이지와 최신 커밋과 비교
git diff head
```

# 10. 원격저장소에 연결
```
git remote add origin 원격저장소url

# 원격 저장소 목록 확인
git remote -v

#등록한 원격 저장소 삭제
git remote rm origin
```

# 11. 서버 전송
```
git push origin master
```

# 12. clone : 복제
```
mkdir gitstudy_clone 
cd gitstudy_clone

git clone https://github.com/applekerstie/gitstudy.git .

$ git remote -v
origin  https://github.com/applekerstie/gitstudy.git (fetch)
origin  https://github.com/applekerstie/gitstudy.git (push)
```

# 13. 서버에서 내려받기
```
# pull : 내려 받은 최신 커밋들을 현재 브랜치로 자동으로 병합처리
git pull

# fetch : 커밋된 코드들을 임시 브랜치로 내려받고 현재 브랜치와 자동 병합하지 않음
git fetch
git merge origin/master 
```

# 14-1. 브랜치
```
# 현재 브랜치 확인
git branch -v

참고) 해당 브랜치의 커밋 해시값 확인
git rev-parse 브랜치이름

# 지정한 커밋 ID 기준으로 브랜치 생성
git branch 브랜치이름 커밋ID

# 가장 마지막 커밋을 기준으로 브랜치 생성
git branch 브랜치이름
```

# 14-2. 브랜치
```
# 브랜치 이동
git checkout 브랜치이름

참고) 커밋하지 않고 다른 브랜치로 체크아웃하면 브랜치 이동이 제한됨
작업된 워킹디렉터리를 커밋하지 않고 브랜치를 변경할때는 스태시 기능 이용

# 로그를 텍스트 그래프로 출력
git log --graph --all 

# (현재브랜치 기준으로) 새 브랜치를 생성하며 체크아웃 하기
git checkout -b 브랜치이름

# 지정한 커밋위치로 체크아웃
git checkout 커밋해시키
```

# 15-1. 리모트브랜치
```
# 로컬에서 브랜치 생성 후 푸시하여 리모트브랜치 생성
git branch real
git push origin real

# 업스트림
git push -u origin real
로컬real을 원격origin의 real에 push하면서 upstream으로 설정함

upstream : 현재 브랜치와 연결된 원격 브랜치를 설정함
git push -u origin master 이후 git push, git pull 실행시 origin master 생략가능

# 로컬의 feature를 원격의 function 브랜치로 푸시
git push origin feature:function
```

# 15-2. 리모트브랜치
```
# 리모트브랜치 내용으로 로컬 저장소에 새 브랜치 생성
git checkout -b 브랜치이름 origin/브랜치이름

# 원격브랜치와 동일한 이름의 로컬브랜치를 생성
git checkout --track origin/브랜치이름

# 리모트 브랜치 목록 보기
git branch -r

# 로컬과 리모트 브랜치 목록 모두 보기
git branch -a
```

# 16. 브랜치
```
# 로컬 브랜치 삭제
git branch -d 브랜치이름

# 커밋이 있는 로컬 브랜치 삭제
git branch -D 브랜치이름

# 리모트 브랜치 삭제
git push origin --delete 리모트브랜치이름
```




