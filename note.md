# 입문자를 위한 Git과 HTML&CSS

## Day 1

### 개발환경 설정
- 강사 웹사이트: https://github.com/seulbinim
- Chrome 확장프로그램: Web developer, OpenWAX, HeadingsMap
- VS code 확장프로그램
    * Live Server: 로컬 서버 자동 구축
    * Prettier-Code Formatter
    * Auto Close Tag
    * Auto Rename Tag
    * vscode-icons: 확장자 별 아이콘 표시
    * Atom Keymap
    * Monokai-Contrast Theme

### CLI 명령어
- CLI: Command Line Interface, 명령어 입력으로 일련의 동작 실행
- 다중 명령: 명령어 사이에 `&&` 입력
- 텍스트 파일 생성
```
touch {filename}
echo {text} > {filename}   # 신규 파일
echo {text} >> {filename}  # 기존 파일
```
- 파일/디렉토리 삭제
```
rm {filename}
rm *                # wd 내 모든 파일 삭제
rm -r {directory}   # 디렉토리 내부 하위 파일 모두 삭제
rm -rf {directory}  # 위와 같음, 경고 나타내지 않음. pwd 확인 필수!
```
- 관리자 권한 실행: `sudo`

### git 활용
- Git 초기 설정: https://git-scm.com/book/ko/v1/시작하기-Git-최초-설정
```
git config --global user.name "username"
git config --global user.email koleetd@gmail.com
git config --global core.editor "code --wait"  # 편집기 VS code로 지정
git config --list  # 입력 내용 확인
```
- 로컬 저장소 생성: `git init`
- git의 영역: working directory, index, HEAD
    * working directory: 파일 저장
    * Index: 변경 이력 저장 (staging area)
    * HEAD: commit을 통한 확정본 생성
- 상태 확인 및 추적: `git status`
- 작업 내역 확인: `git log`
    * `--oneline`: 더 간단하게 보여줌
- wd > Index 이동: `git add {filename}`
- Index > wd 이동: `git rm --cached {filename}`
- Index > HEAD 이동: `git commit -m {comment}`
    * `-m`: message 남기기
- wd > Index > HEAD 이동: `git commit -am {comment}`
- commit log 수정: `git commit --amend`
- 이전 commit으로 돌아가기: `git reset --hard {ID}`
- 다시 최근 HEAD로 복구: `git reset --hard ORIG_HEAD`
- 로컬 저장소 변경 내용 되돌리기: `git checkout -- {filename}`
- 원격 저장소 생성 및 설정
    * README: 로컬 저장소 이미 생성했을 경우 하지 않음 (push 시 에러)
    * `git remote add {별칭} {원격 저장소 주소}`
        + 별칭: 보통 default인 `origin` 사용
        + 주소: 여러 개 사용 가능
- 원격서버로 발행(push): `git push origin {branch}`
    * `master` branch 지정 시 모든 내용을 push함
- 저장소 내용 가져오기(pull): `git clone {주소}`
- 원격 저장소 웹페이지 만들기
    * github 도메인: `{id}.github.io`
    * settings → GitHub Pages → Source를 master branch로 변경
    * 저장소 페이지: `{id}.github.io/{repo.name}`
    * 저장소 이름을 `{id}.github.io` 로 설정할 경우 자동으로 호스팅

### HTML의 기본 구조
```html
<!DOCTYPE html>
<html lang="ko-KR">
    <head>
        <meta charset="UTF-8">
        <title>입문자를 위한 Git과 HTML&CSS</title>
    </head>
    <body>
        <h1>HTML과 CSS 학습</h1>
    </body>
</html>
```

### VS code 단축키
- `Ctrl+Shift+K`: VS code에서 커서 있는 줄 삭제
- `Alt+Shift+↓`: 커서 있는 줄 복사

### 기타 Tip
- `Ctrl+LMB`: 새 탭에서 열기
- DOM: Document Object Model
- DOM Tree: DOM의 구조를 나타내는 것
- Windown의 cmd 창 비우기: `cls`
- DTD: Document Type Definition, 문서 형식 정의
    * VS code에서 첫줄에 `!!!` 입력 시 자동으로 `<!DOCTYPE html>`로 변환

### 유용한 사이트
- HTML5&CSS3 ebook: https://seulbinim.github.io/WSA/
- 생활코딩 '지옥에서 온 git': https://opentutorials.org/course/2708
- pro git: https://git-scm.com/book/ko/v2
- netlify: 온라인 클라우드 무료 호스팅 서비스


## Day 2

### HTML의 Contents model
- HTML5부터는 단위가 아닌 컨텐츠로 태그의 문법 적합성을 판단함
- transparent model: 제거/추가하더라도 구조에 영향을 주지 않음  ex. `<a>`
- interactive model: 동작과 동작 사이에 연관성이 있음  ex. `<button>`

### HTML-텍스트
- Semantic tag: 태그 자체가 의미를 가짐
- `<h1>`~`<h6>` 사용할 때는 계층구조를 지키는 것이 좋음
    * HeadingsMap 이용 시 해당 내용을 확인할 수 있음
    * 암묵적인 Outline 생성: 구조적 설계가 중요
- 명시적인 Outline 생성: `<section>`, `<article>`
    * 만약 암묵적인 Outline과 충돌한다면 해당 태그를 자동으로 수정
- `h1+p*3`: `<h1>`에 `<p>` 3개 생성
- presentation module: Semantic tag 아님, 표시를 위해 쓰는 태그
    * `<b>`, `<i>`, `<font ...>`, `<center>`, `<hr>` 등
    * HTML5에서는 강조, 분위기 전환 등의 의미를 가지는 의미로 쓰임
- 공백 추가하기
    * `&nbsp;`: non-breakable space → 사용 비권장
    * `<div>`, `<span>` 등으로 묶은 다음 CSS style로 수정
        ex. `<span style="margin-right: 50px">`  
        ※ `<p>` 안에는 `<span>`만 사용가능
    * `<br>`(HTML4.0): Line break (empty element) = `<br />`(XHTML1.0)
- 인용: `<q cite="isbn: ,url: ">`
- 약어: `<abbr title="전체내용">약어</abbr>`
- 사이트 연락처: `<address>` (footer에서만 사용)

### HTML-목록
- 순서 목록: `<ol>`(순서 있는 리스트) `<ul>`(순서 없는 리스트)
    * `<li>`: 리스트의 자식요소 (이것만 허용, div 등 금지!)
    * `ol>li*4{순서형목록$}`
        + `>`: 자식요소 지정
        + `$`: 자동으로 숫자 붙임
- 정의 목록: `<dl>`(list), `<dt>`(term), `<dd>`(description)
    * `<dt>`+`<dd>` 묶음에 한해서만 div 허용

### HTML-링크
- `<a>`: 반드시 `href` attribute 함께 사용해야 함
    * 주소: 절대경로/상대경로 둘 다 사용 가능
    * `mailto:`, `tel:` 프로토콜 사용 가능
    * `#id`: 페이지의 특정 부분에 링크 (해당 태그에 `id` attribute 적용 필요)
- 기타 attribute: `target`(`_self`,`_blank` 등), `title`

### HTML-이미지
- `<img>`: 반드시 `src` attribute 함께 사용해야 함
- `alt`: 대체 텍스트, 접근성에 매우 중요
    * 속하는 Block의 속성을 따라감!!(h2, p 등)
    * 즉, Heading에도 해당 텍스트를 표시
- `title`: 해당 내용 Tool tip으로 표기 but 비권장...
- 이미지 크기 변경: CSS 변경 권장 (지정하면 렌더링 속도 빨라짐)
- `<figure>`: 캡션을 함께 담기 위한 구조
    * `<figcaption>` 태그에 해당 내용 작성
    * 이미지, 동영상, 도표 등 모두 활용

### CSS 박스 내부 분석
- CSS: Cascading Style Sheet
    * 모듈 별 Level이 다름, 편의상 합쳐서 3.0이라 부름
    * 브라우저 엔진에 따라 지원 여부가 달라지는 모듈이 있음
- CSS의 주요 특징
    * Cascading: 겹침
    * Inheritance: 상속
    * specificity: 우선순위
- 레이아웃
    * Box model: Block, Inline
    * Float, Position
    * Flex, Grid
- 선형화 구조 (Normal flow)
    * Block: 부모 영역의 크기 전체를 차지하는 형태
    * Inline: 줄 안에서 특정 영역을 차지하는 형태
- 구조: selector(선택자) & declaration(선언)
    * `선택자{속성: 값;}`
    * `;`: 선언 하나가 끝남을 알림
    * 여러 개의 선택자, 여러 개의 선언 동시에 사용 가능
- 적용 방식
    * External: 별도의 *.css 파일 생성 후 HTML에 `<link>` → cache 이용 가능
    * Embedded: `<head>` 태그 안에 `<style>` 태그 이용하여 작성 → 이벤트성으로만...
    * Inline: `style` attribute 이용하여 코드 부여 → ARV(조립) 타입에서 주로 사용

### CSS 기타 내용
- user agent stylesheet: 브라우저에서 해당 태그 인식 시 자동 Style 지정
- `<div>`: agent stylesheet가 없을 때 style 지정하기 위해 사용
- 하늘색: content, 주황색: margin, 노란색: border, 초록색: padding
- margin: collapsing 발생 (큰 쪽으로 병합)
    * float, flex 구조일 경우 겹치지 않음!
- Display 요소: 검사 → Computed → Filter에 display 검색
- 글꼴 그룹 종류
    * serif: 삐침이 있음
    * sans-serif: 삐침이 없음
    * monospace: 모든 글자의 너비가 동일
    * `font-family: Arial, Verdana, sans-serif;`: Arial도 Verdana도 없으면 sans-serif 계열의 아무 글꼴을 호출

### Git
- log 구성: subject / body / footer (body, footer 생략 가능)
    * subject와 body 사이에 공백 1L
    * subject: 명령형, body: 72자 이하의 영문 또는 69자 이하의 한글
```
$ git commit -m "6월 11일 오전 수업 내용
>
> - 기본 구조 관련 템플릿 작성
> - 제목과 단락 관련 요소 실습
> - 목록 관련 요소 실습"
```
- Git bash를 VS code의 External terminal로 지정
    1. 설정 → Termianl > External: Windows Exec.
    2. 경로: C:\Program Files\Git\bin\bash.exe 변경
    3. 종료 후 재시작

### Encoding 수정 with VS code
1. head 안에 `<meta charset="UTF-8">` 입력 후 우측 하단 UTF-8 선택
2. Save with Encoding 선택 → UTF-8 선택
3. 코드 우클릭 → Open with Live Server 선택하여 복구 확인
- 주의! 깨진 상태를 복구하지 않고 저장하면 추후 복구 불가

### VS code 단축키
- 주석: `Ctrl+/`
- 표준 형식 자동 생성 Emmet: `!`
    * `<meta name="viewport" content="width=device-width, initial-scale=1.0">`: 모바일 환경 지원
    * `<meta http-equiv="X-UA-Compatible" content="ie=edge">`: 브라우저 엔진 강제 변환 렌더링
- 좌측 하단 설정 → 바로가기 키 에서 단축키 설정 가능
    * Emmet: 약어로 개별 줄 래핑 → `Ctrl+Shift+A`: 선택영역에 Emmet 적용
- Multi cursor 지정: `Alt+LMB`
- 문서 서식: `Shift+Alt+F` (= 보기 → 명령팔레트 → Prettier formatter 선택)
- 터미널 호출: `Ctrl+~`

### 기타 Tip
- 예전의 비표준 HTML에서는 EUC-KR encoding을 사용했음
- SEO: Search Engine Optimization, 검색 엔진 최적화
    * `<title>` 핵심 주제 노출이 중요
    * `<h1>` 등 제목 태그 사용 필요
- Markdown에서 여러줄 인용 ```{코드종류}: 언어 color와 indent 표시해줌
    * 코드종류: html, css 등등

### 유용한 사이트
- 표준 개발 기구(W3C): https://www.w3.org/
    * W3C validator: https://validator.w3.org/
- Emmet: https://emmet.io/
    * cheat sheet: https://docs.emmet.io/cheat-sheet/


## Day 3

### CSS-선택자
- `<head>` 영역에 `<link rel="stylesheet" href="파일경로">` 선언
- 방식: tag, class, #id
    * 태그 내 태그: `태그1 태그2`
    * 클래스 복수 개 지정 가능: `class="클래스1 클래스2"`
    * `#id`는 거의 사용하지 않음
- 선택자 종류가 정말 많다! p.238
    * 전체 선택자: `*`
    * 클래스 선택자: `.클래스`, `.클래스1.클래스2`...
- 우선순위
    * 직접 선택 > 상속
    * 값에 `inherit` 설정할 경우 상속값을 직접 선택한 것과 같음
    * Level: id > 클래스 > 요소 > 전체 선택자
    * 복수 개를 선택하면 우선순위 ↑  
        ex. `.class.note` > `h1.class` > `.class` > `h1`
    * 나중에 설정할수록 우선순위 ↑
    * 동일한 우선순위에서 `!important` 적용 시 우선순위 ↑
    * 우선순위가 밀리면 검사 시 취소선으로 표시
- 선택자 grouping: `선택자1, 선택자2, 선택자3 {선언}`

### CSS-색상
- 색상 단축 표기법: 16진법 6자리 헥사코드를 3자리로 단축  
    ex. #FFFF00 → #ff0
- 색상함수: `rgba`, `hsla`(hue, saturation, lightness, alpha)
- 상자 자체의 투명도: `opacity`
- CSS 주석: `/* 주석 */`

### CSS-박스모델
- BFC: Block Formatting Context (`display: block;`)
- IFC: Inline FC (`display: inline;`)
    * inline 속성에 block 속성을 적용할 경우 반영되지 않음
- Padding, Border, Margin (단축표기)
    * Padding: Border 안쪽  ex. `padding: 20px;`
    * Border: 테두리  ex. `border: 1px solid red;`
    * Margin: Border 바깥쪽  ex. `margin: 50px auto;`
        + `auto`: 부모의 크기 반영하여 정렬된 것처럼 설정
    * 여백 크기: 시계방향 순서로 입력 (상 우 하 좌)
- `box-sizing`: `content-box`, `border-box`
    * `content-box`: width=content, box 너비는 width, border, padding, margin 모두 더함
    * `border-box`: width=content+border+padding, 즉 box 너비는 width와 margin만 더함
        + 화면의 크기가 달라지더라도 border와 padding을 포함할 수 있음
- overflow: 박스크기가 넘치면 scroll 표시
    * overflow 표시하는 순간 독립적인 BFC 생성: 상속을 잃어버림  
        → 부모 영역에도 overflow 속성을 사용해야 함
    * `overflow: auto;`: content 크기가 크면 scroll 표시, 작으면 표시 X
- 박스 임시로 숨기기
    * `visibility: hidden;`: 영역은 유지하고 내용만 숨김
    * `opacity: 0`: 영역은 유지하고 투명도만 0으로 바꿈
    * `display: none;`: 영역을 없는 것처럼 숨김, 사용 시 주의
- `background-image: linear-gradient(각도deg,색상1,색상2);`

### CSS-레이아웃
- Normal flow: 마크업 순서대로 레이아웃을 정렬한 것
- 자주 쓰는 클래스 이름: header, main, aside, footer, wrapper, container ...
- float: 부모 개체의 왼쪽 또는 오른쪽으로 배치 가능 (가운데 불가)
    * float 개체를 제외한 영역에 별개의 line box를 새로 형성
    * 영역 자체는 다른 형제 개체와 겹칠 수 있음
    * 형제 개체의 컨텐츠는 line box 안, 즉 float 개체와 겹치지 않게 배치
    * float 영역이 부모 개체 영역보다 커지면 바깥으로 튕겨나감
    * 부모 개체에 `overflow: hidden;` 추가 시 float 높이로 자동 조절
    * `clear: both;`: float 영역과 겹치지 않도록 block에 margin 강제 추가 → 요즘 잘 안 씀
- flex: 자유롭게 block 배치하기 위한 요소
    * 부모 개체 flex-container, 자식 개체 flex-item 필요
    * 부모 개체에 `display: flex;` 코드 추가
    * 순서: default는 마크업 순서대로 행방향 배치(`order=0`)  
        → 부모 개체에 `flex-direction: row/column reverse` 등으로 조절 가능  
        → 자식 개체에 `order: -1` 추가 시 이 개체가 먼저 배치됨
    * 가로 여백: `justify-content: space-between/space-around` 등으로 조절
    * 세로 정렬: `align-items` 로 조절 (default: stretch, 부모와 같음)
    * 부모 개체보다 자식 개체의 영역이 크더라도 비율(flex shrink)대로 조절해서 레이아웃 유지  
        → 원하지 않을 경우 부모 개체에 `flex-wrap: wrap;` 추가
- grid: 구애받지 않고 자유롭게 배치할 수 있음... But IE 미지원
- height에는 `%` 단위 사용 불가! `vh` 단위 주로 사용 (browser height의 백분율)

### CSS-컨텐츠 배치
- 백그라운드 이미지 삽입
    * 정렬: `background-position`
        + 백분율 사용 시 개체의 width, height 크기 기준!  
            ex. `body`의 컨텐츠가 없을 경우 height 50% = 0 * 50% = 0px
        + center`: = 50%
    * 위치 고정: `background-attachment: fixed;`
        + 크기는 viewport size 기준
    * 보통 축약 표현으로 설정
        + ex. `background: yellow url("../img/chocolate-islands.jpg") 50% 50% /cover fixed;`
        + background-size 앞에는 `/` 붙임
    * 이미지 로딩 에러 콜백 위해 background-color 설정 권장
- `border-radius`: 테두리의 모양 바꾸기
    * `border-radius: 50%;`: 테두리가 원이 됨
- 컨텐츠 자체도 anonymous inline box를 가짐: `display: flex;` 적용 가능
- `.클래스:hover`: 마우스 올렸을 때의 행동

### HTML-레이아웃
- HTML5 신규 태그: `<header>`, `<main>`, `<aside>`, `<footer>`
    * 4단 레이아웃에 가장 많이 씀: `<div>`보다 의미부여 할 수 있어 유리
    * `<body>`에도 쓸 수 있고 `<section>`에도 쓸 수 있음
    * Emmet `header.header{헤더}+div.wrapper(>main.main{컨텐츠}+aside.aside{사이드바})+footer.footer{푸터}`

### VS code 단축키
- 코드 위치 변경: 영역 선택 → `Alt+이동화살표`
- Emmet `[]`: 태그 내 속성 지정, `{}`: 태그 안 컨텐츠 지정  
    ex. `ul>li*4>a[href="#"]{목록$}`
- Emmet `태그.클래스`: 클래스를 가진 태그 생성
- Emmet `w500px`: `width: 500px;`
- Emmet `m0`: `margin: 0;`

### 기타 Tip
- naming rule: Pascal, Camel, Snake, Kebob case
- CSS project naming rule: OOCSS, SMACSS, BEM

### 유용한 사이트
- CSS flex trick: https://css-tricks.com/snippets/css/a-guide-to-flexbox/
- CSS flex 익히기 게임: https://flexboxfroggy.com/
