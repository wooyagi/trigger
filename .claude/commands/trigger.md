새 투자 트리거를 index.html 의 SEED 배열에 추가하고 GitHub에 푸시한다.
사용법: /trigger {설명} (예: /trigger TSMC 애리조나 첨단 패키징 공장 착공)

[작업 순서]
1. 사용자가 준 설명을 바탕으로 아래 항목을 채운다. 모르는 것은 웹 검색으로 1차 자료(공시·규제기관·IR)에서 확인하고, 확인 못 하면 빈 문자열 또는 "일정 미정"으로 둔다. 추측·날조 금지.
   - theme: power / packaging / macro / other
   - type: 실적·가이던스 / 정책·규제 / 계약·수주 / 기술·마일스톤 / 수급·가격 / 매크로·이벤트
   - status: watch (기본) / soon / fired / dead
   - title: 한 줄. "무엇이 일어나면"이 분명하게
   - when: 예상 시점 (확정 일정이면 날짜, 아니면 "분기 실적 시" 같은 조건)
   - tickers: 관련 종목 (쉼표 구분)
   - signal: 사건 전에 보이는 선행 신호 (MOU·장비 발주·도킷 일정 등)
   - confirm: 발동 여부를 판정하는 방법과 1차 자료
   - link: 확인 소스 URL (공식 사이트 우선)
   - note: 무산 조건, 주의점
   - added: 오늘 날짜 YYYY-MM-DD
2. id는 "s-" + 영문 소문자 하이픈 slug. 기존 id와 중복되지 않게.
3. index.html 에서 `// NEW_TRIGGER_INSERT` 주석 바로 아래 줄에 객체 한 개를 삽입한다. 기존 항목은 건드리지 않는다.
4. 삽입 후 `node -e "..."` 등으로 SEED 배열 문법 오류가 없는지 확인한다 (중괄호·쉼표).
5. 커밋 메시지 "트리거 추가: {title}" 로 main에 푸시한다.

[삽입 형식]
  {id:"s-{slug}",theme:"{theme}",type:"{type}",status:"watch",
   title:"{title}",when:"{when}",tickers:"{tickers}",
   signal:"{signal}",
   confirm:"{confirm}",
   link:"{link}",note:"{note}",added:"{YYYY-MM-DD}"},
