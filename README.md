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

