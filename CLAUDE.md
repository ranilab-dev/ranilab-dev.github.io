# CLAUDE.md: Rani 포트폴리오 사이트

이 저장소는 GitHub Pages로 배포되는 정적 사이트야. main에 push하면 1~2분 뒤 https://ranilab-dev.github.io 에 반영돼.
프로필은 https://ranilab-dev.github.io/profile/ 이고, 맨 위 주소(/)로 오면 프로필로 자동으로 넘어가.

## 사용자

- 코딩 초보야. 바꾼 내용은 쉬운 한국어로 짧게 설명해줘.
- 활동명은 Rani, GitHub 아이디는 ranilab-dev. 익명으로 활동하는 계정이야.

## 구조

- profile/index.html 하나에 HTML, CSS, 캐릭터 SVG가 다 들어 있어. 빌드 도구, 프레임워크, npm 없음. 이 구조를 유지해.
- 맨 위 index.html은 프로필로 넘겨주기만 하는 짧은 파일이야. 내용은 profile/index.html에 써.
- 외부 리소스는 Pretendard 폰트 CSS(jsDelivr) 하나만 써.
- rani-avatar.svg, rani-logo.svg는 원본 그림이고, 프로필 안의 캐릭터·로고와 같은 그림이야.
- 앱 사이트(/peekat, /synkat, /ringkat)는 이 저장소에 없어. 각 앱 저장소에서 만들고, 출시 때 그 앱의 공개 저장소 docs/ 폴더로 같은 주소에 떠. 이 저장소에 peekat/ 같은 폴더를 만들면 주소가 겹치니까 만들지 마.
  - 피캣 사이트 원본: 비공개 저장소 peekat-src 의 site/ (미리 보기 https://ranilab-dev.github.io/peekat-src/)

## 디자인 규칙

- 애플 제품 페이지 같은 넓은 여백, 큰 제목, 차분한 색.
- 브랜드 그라데이션: #7B5CFF, #2E95EA, #12A27C (다크 모드는 #C4B5FF, #9AD6FF, #9BF0D0).
- 색은 :root의 CSS 변수로만 쓰고, 다크 모드 값도 같이 맞춰.
- 핑크나 하트 같은 여리여리한 장식은 쓰지 않아.

## 작업 추가하기

- 작업 칸(#work)의 li 한 덩어리가 작업 하나야. "참여한 프로젝트"와 "만들고 있는 것" 두 묶음.
- 상태 칩 클래스: chip idea(구상 중), chip prep(준비 중), 팀 프로젝트는 chip team.
- 링크가 있으면 a 태그, 없으면 div class="static".

## 앱 카드 (#apps)

- 자기소개 바로 아래 "만들고 있는 앱"의 a class="app" 한 덩어리가 앱 하나야. 순서는 링캣, 피캣, 싱캣.
- 카드는 앱 사이트 최종 주소(../ringkat/, ../peekat/, ../synkat/)로 가. 앱이 출시되기 전엔 눌러도 404야.
- 상태 칩: chip prep(준비 중 · 출시 준비 중), chip dev(개발 중).
- 링캣 카드의 한 줄 소개는 비공개 저장소 Ringkat-src 의 website/SITE.md 1장 "한 줄 소개"에서 가져왔어. 그 파일의 내부 메모(0장 등)는 사이트에 옮기지 마.
- 아이콘: 피캣은 profile/peekat.png (피캣 저장소 docs/icon.png 복사본), 링캣은 profile/ringkat.png (Ringkat-src 의 website/icon.png 를 256px로 줄인 것). 싱캣은 아이콘이 생기기 전까지 글자(S) 칸이야. 아이콘이 생기면 span class="ic s" 대신 img class="ic".

## 지켜야 할 것

- 본명, 학교, 사는 지역, 개인 이메일(네이버·학교)은 사이트와 커밋 어디에도 넣지 마.
- tation은 비공개 저장소라 내용을 추가하지 마.
- 내용을 지우거나 크게 바꾸기 전에는 먼저 물어봐.
- 커밋 작성자는 항상 Rani와 noreply 메일이어야 해. 커밋 전에 확인하고, 다르면 이 저장소에만 설정해:

        git config user.name "Rani"
        git config user.email "101460577+ranilab-dev@users.noreply.github.com"

## 배포 순서

1. git pull로 웹이나 다른 곳에서 바뀐 내용을 먼저 받기
2. 수정한 뒤 브라우저로 profile/index.html을 열어서 라이트, 다크, 모바일 폭 확인
3. git add, git commit -m "무엇을 바꿨는지 한국어로", git push
4. 1~2분 뒤 사이트에서 반영됐는지 확인
