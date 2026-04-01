Auto Trading Bot
-------------------------
Python과 Upbit API를 활용한 암호화폐 자동 매매 프로그램



Tech Stack
--------------------------------
Python, pyupbit (Upbit API), pandas



주요 기능
--------------------------------
실시간 암호화폐 가격 조회

변동성 돌파 전략 기반 자동 매수/매도



프로젝트 구조
--------------------------------
bitcoinautotrade.py  -> 비트코인 자동매매 (기본 전략)

xrpautotrade.py      -> 리플 자동매매

ma.py                -> 이동평균 필터가 추가된 개선 전략


 
트레이딩 전략
--------------------------------
1. 변동성 돌파 전략

전일 가격 변동폭(high - low)을 기준으로 목표가 설정

현재 가격이 목표가를 돌파하면 매수

target_price = close + (high - low) * k

2. 이동 평균 필터 (ma.py)
   
15일 이동 평균선보다 현재 가격이 높을 때만 매수

상승장 필터링 역할 수행

ma15 < current_price



실행 로직
--------------------------------
오전 9시 ~ 다음날 8시 59분:
매수 조건 확인 후 시장가 매수
장 마감 직전에 보유 코인 전량 시장가 매도



실행 방법
---------------------------------
라이브러리 설치
pip install pyupbit pandas


각 파일 상단에 Upbit API 키 입력

access = "YOUR_ACCESS_KEY"

secret = "YOUR_SECRET_KEY"


실행

python bitcoinautotrade.py



실행 결과
---------------------------------
![AutoTradeBitCoin](https://github.com/user-attachments/assets/a1484532-fa5e-4684-9e6a-1aff0cd61739)



