# trigger
병목 트리거 탐색·백테스트 데스크 — https://wooyagi.github.io/trigger/

병목에 선 공급사 CEO의 첫 언급(T1)을 잡고, 2차 신호(T2)에서 수요·공급을 판단해 비중을 올린다.
과거 병목 전이(CoWoS → HBM → 전력 → 광통신/CPO → NAND)로 규칙을 백테스트하고, 다음 병목 후보와 CEO 워치리스트를 추적한다.

- `index.html` — 단일 페이지. 신호 사다리 / 병목 전이 맵 / 백테스트(타임라인+지수화 차트+수익률) / 다음 병목 후보·CEO 워치 / 트리거 보드 / 메모
- `data/cases.json` — 백테스트 사례(이벤트·발언·검증 상태), 후보, CEO 워치리스트, 컨콜 검색어
- `data/prices.json` — Yahoo Finance 주간 종가 (5년). `/prices` 로 갱신
- 보드 기본 항목은 `index.html`의 `SEED` 배열 (`/trigger` 로 추가)

## 명령어
- `/backtest {사례id|all}` — cases.json 이벤트를 컨콜 전문·공시로 검증, 날짜·인용·출처 보정, verified=true
- `/trigger {설명}` — 보드에 새 트리거 추가
- `/prices` — 주가 데이터 갱신
