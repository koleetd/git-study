# 입문자를 위한 Git과 HTML&CSS

## Day 1

### 환경설정
- chrome 설치
- git 설치
- VS code 설치

### CLI 명령어
- 디렉토리 생성: `mkdir`
- 디렉토리 이동: `cd`
- 빈 파일 생성: `touch`
- 내용 있는 파일 생성: `echo`
- 파일 이동 or 이름 변경: `mv`
- 복사: `cp`
- 디렉토리 삭제: `rmdir`
- 비어있지 않은 디렉토리 or 파일 삭제: `rm`
- 목록 출력: `ls`
- 화면 지우기: `clear`

### git 명령어
- 저장소 초기화: `git init`
- 사용자명 등록: `git config --global user.name {"사용자명"}`
- 사용자 메일 등록: `git config --global user.email {메일주소}`
- 기본 편집기 지정: `git config --global core.editor "code --wait"`
- 현재 상태 확인: `git status`
- index 영역으로 이동: `git add`
- Commit 기록 생성: `git commit -m {"Commit 메시지"}`
- Commit 기록 수정: `git commit --amend`
- Commit log 조회: `git log`
- 되돌리기: `git reset --hard {CommitID}`
- 원격 저장소 등록: `git remote add origin {주소}`
- 발행하기: `git push origin master`
- 일반 저장소에서 호스팅 저장소로 변경하기: [Youtube 영상](https://youtu.be/SNnfbf-LJz4)
