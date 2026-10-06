data/prices.json 의 주가 데이터를 갱신한다. 사용법: /prices [추가할 티커 ...]

1. data/cases.json 의 모든 tickers(supplier·adjacent·demand·benchmark)와 인자로 받은 티커를 합쳐 목록을 만든다.
2. 각 티커에 대해 Yahoo chart API 5년 주봉을 받는다:
   curl -s -A "Mozilla/5.0" "https://query1.finance.yahoo.com/v8/finance/chart/{TICKER}?range=5y&interval=1wk"
   → result[0].timestamp, indicators.quote[0].close 를 [YYYY-MM-DD, close] 배열로 변환 (null 제외, 소수 2자리).
3. {asof: 오늘, interval:"1wk", field:"close", series:{...}} 형식으로 data/prices.json 에 저장 (separators 압축).
4. 실패한 티커는 보고하고 기존 값을 유지한다.
5. 커밋 메시지 "주가 갱신 {날짜}" 로 main에 푸시.
