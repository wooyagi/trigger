data/cases.json 의 백테스트 사례를 1차 자료로 검증·보정하고 GitHub에 푸시한다.
사용법: /backtest {사례id | all | "새 사례 설명"} (예: /backtest cowos, /backtest all, /backtest 2021 차량용 MCU 병목)

[검증 작업 — 기존 사례]
1. 각 event에 대해 웹 검색으로 컨콜 전문(회사 IR, SEC 8-K Exhibit 99, Motley Fool/Seeking Alpha transcript 등)·공시·보도자료를 찾는다.
2. 확인되면: date를 실제 발표일로 보정, quote를 원문 발언(영문 원문 + 한국어 요약)으로 교체, source에 URL, verified:true.
3. 확인 못 하면: verified:false 유지, quote 끝에 "(확인 못 함: 사유)" 추가. 날짜를 지어내지 않는다.
4. 발언의 tier가 잘못 분류됐으면 조정한다. T1은 "병목 공급사 자신이 캐파 제약을 처음 공개적으로 말한 시점"이어야 한다. 더 이른 T1을 찾으면 firstMention도 갱신.
5. 새 티커가 추가되면 /prices 절차로 prices.json에도 추가.

[새 사례 추가]
- id는 영문 소문자 slug, 위 구조대로 작성. events 최소 3개(T0 또는 T1, T2, T3).
- benchmark는 수요측 대표 종목(없으면 "NVDA").
- lesson에는 "T1→T2 간격, 전이 경로, 무산 조건"을 적는다.

[사용자 참고 인물 자료]
- 아센브레너(Situational Awareness LP): 13F(SEC EDGAR)로 보유 종목·시점 확인. 'Situational Awareness' 에세이의 병목 관련 서술 인용.
- 수 멍: 사용자가 제공한 원문/글을 받아 CPO 사례 lesson에 링크. 원문 없이는 추정하지 않는다.

[마무리]
- python3 -c "import json;json.load(open('data/cases.json'))" 로 문법 확인
- 커밋 메시지 "백테스트 검증: {사례id}" 로 main에 푸시
