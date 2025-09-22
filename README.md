# 김개발 포트폴리오 (정적 웹사이트)

간단한 정적 포트폴리오 웹사이트입니다. HTML, CSS, JavaScript만으로 구성되어 있으며 반응형 UI, 타이핑 애니메이션, 스무스 스크롤, 스킬 바 애니메이션, 타임라인/프로젝트 카드 애니메이션, 간단한 폼 검증을 포함합니다.

## 시작하기
- 로컬에서 바로 실행: 브라우저로 `index.html`을 열면 됩니다.
- 권장 브라우저: 최신 Chrome/Edge/Safari/Firefox.

## 폴더/파일 구조
```
/ (프로젝트 루트)
├── index.html   # 페이지 마크업 (섹션 구성 및 콘텐츠)
├── style.css    # 전체 스타일, 반응형, 애니메이션, 레이아웃
└── script.js    # 네비 토글, 스크롤/타이핑/스킬바/폼 검증 로직
```

## 주요 기능
- 헤더/네비게이션: 고정 헤더, 활성 섹션에 따른 네비 링크 하이라이트, 모바일 햄버거 메뉴 토글
- 섹션: Home(히어로), About, Skills, Experience(타임라인), Projects, Contact
- 애니메이션/인터랙션:
  - 히어로 서브타이틀 멀티 타이핑 (`.typing-text`, `data-texts`)
  - 히어로 타이틀 단일 타이핑 (`.hero-title`)
  - 스크롤 시 스킬 바 채우기 (IntersectionObserver, `data-width`)
  - 타임라인/프로젝트/스킬 카테고리 페이드업
  - 전역 스무스 스크롤, 고정 헤더 오프셋 처리
- 폼 검증: Contact 폼 기본 유효성 검사 및 이메일 형식 체크(데모 동작: 알림 후 reset)

## 파일별 상세
- index.html
  - 시맨틱 섹션과 내비게이션 앵커(`#home`, `#about`, ...)
  - 히어로 섹션의 타이핑 문구는 `span.typing-text[data-texts="[...]"]` 속성으로 제어
- style.css
  - 그라디언트 히어로 배경, 카드/타임라인/버튼/태그 스타일
  - 반응형 분기: 768px, 480px 미디어쿼리
  - 스킬바 애니메이션 키프레임(`fillBar`) 및 시각 이펙트
- script.js
  - 모바일 메뉴 토글 및 외부 클릭/ESC/리사이즈로 닫기 처리
  - 스무스 스크롤 시 고정 헤더 높이만큼 보정
  - IntersectionObserver로 스킬바 최초 진입 시 너비 설정 + 애니메이션
  - 현재 뷰포트 섹션에 맞춰 내비 링크 `.active` 토글
  - 멀티 타이핑(`multiTypeWriter`)과 단일 타이핑(`typeWriter`)
  - 폼 기본 검증 및 성공 알림(데모)

## 커스터마이징 가이드
- 이름/타이틀 변경: `index.html`의 `.hero-name`, `.hero-title` 텍스트 수정
- 타이핑 문구 변경: `.typing-text`의 `data-texts` JSON 배열 수정
- 스킬 숙련도 변경: 각 `.skill-progress`의 `data-width`(예: `85%`)
- 프로젝트 카드 내용/링크 교체: `Projects` 섹션의 카드 텍스트와 버튼 `href` 수정
- 색상/테마 변경: `style.css`의 주요 색상 값(예: `#3498db`, `#2ecc71`) 변경
- 네비 항목 추가: `index.html`의 `.nav-menu`와 해당 섹션을 함께 추가

## 배포
- GitHub Pages
  1. 이 저장소를 GitHub에 푸시
  2. Settings → Pages → Branch를 `main`/`root`로 설정
  3. 제공된 URL로 접속
- 정적 호스팅 서비스(Cloudflare Pages, Netlify, Vercel 등)에 그대로 업로드 가능

## 접근성/UX 참고
- 키보드 대응: ESC로 모바일 메뉴 닫기 지원
- 포커스 스타일: 기본 브라우저 포커스 사용, 필요 시 `:focus` 스타일 추가 권장
- 색 대비: 텍스트/배경 대비 준수, 색상 커스터마이징 시 재검토 권장

## 성능 참고
- 스크롤 이벤트는 `throttle`로 최적화 예시 포함
- IntersectionObserver 사용으로 지연 애니메이션 처리
- 외부 빌드/번들 없음: 로드가 빠르고 유지보수 간단

## 한계/주의사항
- 연락처 폼은 데모용이며 서버 전송 기능이 없습니다
- `Projects`의 Demo/GitHub 링크는 플레이스홀더(`#`)이므로 실제 링크로 교체하세요

## 라이선스
- 개인 포트폴리오 예제로 자유롭게 수정/확장 가능합니다. 외부 폰트(구글 폰트)의 라이선스는 제공처를 따릅니다.
