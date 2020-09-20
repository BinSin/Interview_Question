# Git
- [About Error](#About-Error)

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
