# trigger 데스크

단일 페이지(index.html) GitHub Pages 사이트. 투자 트리거(주가를 움직일 사건)를 정의·추적한다.

[원칙]
- 기존 SEED 항목의 내용·id를 수정하지 않는다. 새 항목만 추가한다.
- 모든 트리거는 1차 자료(공시·규제기관 문서·IR)로 발동 여부를 판정할 수 있어야 한다.
- 날짜·수치는 확인된 것만 기입. 모르면 "일정 미정"으로 쓴다. 추측·날조 금지.
- LOI/MOU는 선행 신호(signal)에, 구속력 있는 계약은 확인 방법(confirm)에 쓴다. 섞지 않는다.

[데이터 구조 — index.html 의 SEED 배열]
{id:"s-{slug}", theme:"power|packaging|macro|other", type:"실적·가이던스|정책·규제|계약·수주|기술·마일스톤|수급·가격|매크로·이벤트",
 status:"watch|soon|fired|dead", title, when, tickers, signal, confirm, link, note, added:"YYYY-MM-DD"}

새 항목은 `// NEW_TRIGGER_INSERT` 주석 바로 아래에 삽입한다. id는 "s-" 접두사 필수(기본 항목 판별에 사용).

[명령어]
- /trigger — 새 트리거 추가 (.claude/commands/trigger.md)
