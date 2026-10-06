# trigger
투자 트리거 탐색 데스크 — https://wooyagi.github.io/trigger/

주가를 움직일 사건(트리거)을 미리 정의하고, 선행 신호와 확인 소스를 한 곳에 모은다.
전력(power)·패키징(packaging) 데스크의 논지가 실제로 작동하는 시점을 잡기 위한 레이더.

- `index.html` — 단일 페이지. 트리거 보드(검색·필터·상태), 유형 프레임워크, 탐색 소스, 체크리스트, 메모
- 기본 트리거는 `index.html`의 `SEED` 배열에서 관리 (`/trigger` 명령으로 추가)
- 브라우저에서 직접 추가한 항목·상태·체크·메모는 localStorage에만 저장됨 (내보내기 버튼으로 JSON 추출)
