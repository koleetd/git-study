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


## Day 2

### HTML 기본 구조
- DTD 선언
- html 요소
- head 요소 (문서 제목 및 메타데이터 선언)
```html
<!DOCTYPE html>
<html lang="ko-KR">
<head>
    <meta charset="UTF-8">
    <title></title>
</head>
<body>
    
</body>
</html>
```

### HTML 요소
- 제목 요소: `<h1>~<h6>`
- 문단 요소: `<p>`
- 강조, 분위기 전환: `<b>`, `<i>`, `<strong>`, `<em>`
- 줄바꿈, 수평선 삽입: `<br>`, `<hr>`
- 목록 요소: `<ul>`, `<ol>`, `<li>`, `<dl>`, `<dt>`, `<dd>`
- 하이퍼링크: `<a href="" target="" title="">`
- 이미지: `<img src="" alt="">`

### CSS 개념 및 정의
- CSS: Cascading Style Sheet, 스타일을 정의하기 위한 언어
- 최신 표준: CSS3로 불리는 신규 모듈의 집합
- 중요한 개념: 겹칩, 상속, 우선순위
- 레이아웃 설계: float, position, flex 등의 속성 필요
- 기본 문법: 선택자 & 선언부로 구성
```css
    p {
        color: green;
        background-color; yellow;
    }
```

## Day 3