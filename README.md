# nudge-cases

**기울어진 바닥** — 명령하지 않고 행동을 바꾼 환경 8개 사례.

환경은 사람에게 직접 명령하지 않는다. 대신 어떤 행동은 쉽게, 어떤 행동은 어렵게 만들면서
선택의 방향을 바꾼다. 이 사이트는 그 사례 8개를 다이어그램과 수치로 정리한 단일 페이지다.

## 사례

| # | 사례 | 핵심 수치 |
|---|------|-----------|
| 1 | 장기기증 기본값 | 오스트리아 99.5% vs 독일 36% |
| 2 | 구글 → 애플 기본 검색엔진 | 연 $20B, 변경은 3탭 |
| 3 | 스히폴 공항 소변기의 파리 | 흘림 −80% (미검증 수치) |
| 4 | 캠든 벤치 | 금지 표지판 0장, 제거된 행동 5종 |
| 5 | 욕망의 길 | 1914년 열기구 관찰 후 포장 |
| 6 | 개방형 사무실 | 대면 −70%, 이메일 +56% |
| 7 | FTC Click-to-Cancel | 규제 대상은 거짓말이 아니라 클릭 수 |
| 8 | r/assholedesign | 게시물 1,002개가 연구 데이터로 |

## 구성상의 판단

- **반증을 숨기지 않았다.** 장기기증과 스히폴은 넛지 담론의 대표 사례지만 각각
  종단 연구로 반박되거나 원 수치가 검증된 적이 없다. 주황색 세로선으로 표시했다.
- **역방향 사례를 포함했다.** 욕망의 길과 r/assholedesign은 사람이 환경을 바꾼 경우다.
  "환경이 사람을 프로그래밍한다"는 명제의 반례로 넣었다.
- **출처를 1차/2차/참고로 구분했다.** 원논문·공식 자료·당사자 인터뷰는 `1차`,
  언론 보도와 비평은 `2차`, 해설과 백과는 `참고`로 태그를 달았다.

## 보기

빌드 과정이 없다. `index.html` 하나로 완결된다.

```bash
# 바로 열기
start index.html          # Windows
open index.html           # macOS

# 또는 로컬 서버
python -m http.server 8000
```

## GitHub Pages 배포

`main` 브랜치에 푸시하면 `.github/workflows/pages.yml`이 자동 배포한다.
최초 1회만 저장소 설정이 필요하다.

1. GitHub에 저장소 생성 후 푸시
2. **Settings → Pages → Build and deployment → Source** 를 **GitHub Actions** 로 변경
3. 이후 `main` 푸시마다 자동 배포. 주소는 `https://<사용자>.github.io/nudge-cases/`

`Source`를 `Deploy from a branch`로 두면 워크플로가 동작하지 않으니 반드시 위 2번을 먼저 한다.

## 기술

- 의존성 없음. 외부 스크립트 없음.
- 다이어그램 9개 전부 손으로 쓴 인라인 SVG (`currentColor` 기반이라 테마를 따라간다)
- 라이트/다크 양쪽 지원 — `prefers-color-scheme` + `data-theme` 속성
- 폰트: Bricolage Grotesque, IBM Plex Sans KR, IBM Plex Mono (Google Fonts)

## 주의

각 수치의 출처는 카드 하단에 링크로 달려 있으나, 웹 검색 결과를 교차 확인한 수준이며
모든 원문을 전수 확인하지는 않았다. 인용 전에는 특히 아래 세 건의 원문 확인을 권한다.

- Max Planck (2026) — 넛지 효과 없음이라는 반직관적 주장
- Works That Work — 스히폴 80%가 미검증이라는 유일한 근거
- Bernstein & Turban (2018) — *Phil. Trans. R. Soc. B* 원논문
