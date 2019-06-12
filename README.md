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

### CSS 선택자 및 박스모델
- 전체 선택자 (`*`)
- 요소 선택자 (`tag명`)
- class 선택자 (`.class명`)
- id 선택자 (`#id명`)
- `width`, `height` 속성: 박스의 가로 및 세로 크기
- `border`: 테두리
- `padding`: 안쪽 여백
- `margin`: 바깥쪽 여백 (`auto` 사용 가능)
- `box-sizing`: `content-box`, `border-box`
- `overflow`: box 크기와 컨텐츠 크기

### 레이아웃 관련 속성
- `float`
> `float` 속성은 `left`와 `right` 값을 사용할 수 있으며 일반적인 흐름(Normal flow)을 벗어나서 화면 위에 떠 있는 형태로 만들 수 있다. `left`나 `right` 값은 부모 영역을 기준으로 배치되며 각각 *line box* 안에서 배치된다는 특징이 있다. 또한 부모 요소는 float 된 높이를 잃어버리기 때문에 부모 요소에 `overflow: hidden`을 지정하여 문제를 해결할 수 있다.
- `display: flex;` ([CSS Tricks 참고자료](https://css-tricks.com/snippets/css/a-guide-to-flexbox/))
> *유연한 박스 모델*로 불린다. 배치하고자 하는 요소의 부모 요소에 `display: flex;`를 지정한다. 이 때 flex가 지정된 요소의 자식 요소는 *flex item*의 역할을 담당하게 되고 `flex-direction` 속성에 지정한 방향으로 배치된다.

### 배경 관련 속성
- `background-color`: 배경 색상
- `background-image`: 배경 이미지
- `background-repeat`: 배경 이미지 반복 여부
- `background-position`: 배경 이미지 위치
- `background-attachment`: 배경 이미지 고정 여부
- `background-size`: 배경 이미지 크기
- `background`: 배경 관련 단축 표기법