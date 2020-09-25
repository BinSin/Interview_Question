# Git
- [취소하기](#취소하기)
- [About Error](#About-Error)


## 취소하기
### git add 취소하기
파일 상태를 Unstage로 변경하기

```
git reset HEAD <file>
```
명령어를 통해 git add를 취소할 수 있다.

뒤에 파일명이 없으면 add한 파일 전체를 취소한다.

### untracked 파일 삭제하기
git clean 명령은 추적 중이지 않은 파일만 지우는 게 기본 동작이다. 즉, .gitignore 에 명시하여 무시되는 파일은 지우지 않는다.
```
git clean -f 
// 디렉터리를 제외한 파일들만 삭제

$ git clean -f -d
// 디렉터리까지 삭제

$ git clean -f -d -x
// ignored 된 파일까지 삭제
```

### git commit 취소하기
#### commit을 취소하고 해당 파일들은 staged 상태로 워킹 디렉터리에 보존
```
git reset --soft HEAD^
```

#### commit을 취소하고 해당 파일들은 unstaged 상태로 워킹 디렉터리에 보존
```
git reset --mixed HEAD^ // 기본 옵션
git reset HEAD^ // 위와 동일
git reset HEAD~2 // 마지막 2개의 commit을 취소
```

#### commit을 취소하고 해당 파일들은 unstaged 상태로 워킹 디렉터리에서 삭제
```
git reset --hard HEAD^
```

#### commit message 변경하기
커밋 메세지를 잘못 적은 경우, 아래 명령어를 통해 메세지를 변경할 수 있다.
```
git commit --amend
```

### git push 취소하기
이 명령을 사용하면 자신의 local의 내용을 remote에 강제로 덮어쓰기를 하는 것이기 때문에 주의해야 한다.

되돌아간 commit 이후의 모든 commit 정보가 사라지기 때문에 주의해야 한다.
특히, 협업 프로젝트에서는 동기화 문제가 발생할 수 있으므로 팀원과 상의 후 진행하는 것이 좋다.

#### 가장 최근의 commit을 취소한다.
```
git reset HEAD^
// 가장 최근의 commit을 취소 (기본 옵션: --mixed)
```

#### 원하는 시점으로 워킹 디렉터리를 되돌린다.
```
// Reflog(브랜치와 HEAD가 지난 몇 달 동안에 가리켰었던 커밋) 목록 확인
git reflog 또는 $ git log -g

// 원하는 시점으로 워킹 디렉터리를 되돌린다.
git reset HEAD@{number} 또는 $ git reset [commit id]
```

#### 되돌려진 상태에서 다시 commit 한다.
```git commit -m "Write commit messages"
```

#### 원격 저장소에 강제로 push 한다.
```
git push -f origin [branch name]
```

출처: https://velog.io/@hidaehyunlee/Git-add-commit-push-%EC%B7%A8%EC%86%8C%ED%95%98%EA%B8%B0

## About Error
- CRLF will be replaced by LF
```
warning: CRLF will be replaced by LF in some/file.file.
The file will have its original line endings in your working directory.
```
이는 맥 또는 리눅스를 쓰는 개발자와 윈도우 쓰는 개발자가 Git으로 협업할 때 발생하는 **Whitespace** 에러다. 유닉스 시스템에서는 한 줄의 끝이 **LF(Line Feed)** 로 이루어지는 반면, 윈도우에서는 줄 하나가 **CR(Carriage Return)** 와 **LF(Line Feed)**, 즉 CRLF로 이루어지기 때문이다. 따라서 어느 한 쪽을 선택할지 Git에게 혼란이 온 것이다. 둘 중 뭐든간에 해결 방법은 같다. Git은 똑똑해서 이를 자동 변환해주는 core.autocrlf 라는 기능을 가지고 있는데, 이 기능을 켜주기만 하면 된다.
```git
git config --global core.autocrlf true
```
이 기능은 개발자가 git에 코드를 추가했을 때 (예컨대 커밋할 때)에는 CRLF를 LF로 변환해주고, git의 코드를 개발자가 조회할 때 (예컨대 clone한다거나 할 때)에는 LF를 CRLF로 변환해준다.

출처: https://blog.jaeyoon.io/2018/01/git-crlf.html
