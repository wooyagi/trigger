# trigger 데스크

병목 트리거 탐색·백테스트 단일 페이지(index.html) + 데이터(data/*.json). GitHub Pages.

[핵심 개념]
- T0 수요 쇼크 → T1 병목 공급사 CEO 첫 언급 → T2 2차 확인(고객·인접사·가격) → T3 컨센서스
- 행동 구간은 T1~T2. 병목은 전이한다(한 곳이 풀리면 다음 약한 고리로).

[원칙]
- 추측·날조 금지. 날짜·발언은 컨콜 전문/공시/IR로 확인한 것만 verified:true. 못 찾으면 verified:false 유지하고 note에 사유.
- 기존 사례·이벤트의 id는 바꾸지 않는다. 틀린 날짜·인용은 수정하되 source에 링크를 남긴다.
- LOI/MOU는 T1~T2 신호, 구속력 있는 계약·가격·수주 공시가 T2 확정 근거.
- 사용자가 언급한 인물(아센브레너, 수 멍)의 통찰은 원문(논문·글·13F)을 확보한 뒤에만 사례에 링크한다.

[data/cases.json 구조]
cases[]: {id, year, title, bottleneck, demandShock, firstMention{who,what,date}, tickers{supplier[],adjacent[],demand[]}, benchmark, events[{date,tier(0-3),who,quote,verified,source}], lesson}
candidates[]: {name, why, watch, status}
ceoWatch[]: {company, ceo, node, listen}
keywords[]: 컨콜 검색어

[data/prices.json]
{asof, interval:"1wk", field:"close", series:{TICKER:[[YYYY-MM-DD, close],...]}}
갱신: .claude/commands/prices.md 참고 (Yahoo chart API, 5y 주봉). 사례에 새 티커를 넣으면 반드시 여기에도 추가.

[index.html SEED]
보드 기본 항목. {id:"s-..", theme:"power|packaging|optics|memory|macro|other", tier:"0|1|2|3", status, title, when, tickers, signal, confirm, link, note, added}
새 항목은 `// NEW_TRIGGER_INSERT` 바로 아래 삽입. 수정 후 `node -e`로 SEED·script 문법 검사.

[명령어]
- /backtest — 사례 이벤트 검증·보정 (.claude/commands/backtest.md)
- /trigger  — 보드 항목 추가 (.claude/commands/trigger.md)
- /prices   — 주가 갱신 (.claude/commands/prices.md)
