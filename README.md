# kospi-signals

🌐 **라이브 대시보드: https://makalee63.github.io/kospi-signals**

**코스피 · 빅테크 · HBM 시그널 대시보드** — 하루 2회 자동 갱신 (08:00 KST 장 시작 전 / 17:00 KST 장 마감 후). 회차별 풀 대시보드는 불변 아카이브로 보존되고, 랜딩 페이지는 매 회차마다 재생성되는 회차 목록입니다.

## 파일 구조

```
/
├── index.html                       ← 회차 목록 (랜딩 페이지, 매 회차 재생성)
├── snapshots/                       ← 각 회차의 풀 대시보드 (불변 아카이브)
│   └── YYYY-MM-DD-HHMMUTC.html
├── data/
│   └── history.json                 ← 시계열 누적 (append-only)
└── README.md
```

각 실행은 (1) 새 회차 스냅샷 추가, (2) `data/history.json`에 한 항목 append, (3) `index.html`을 회차 목록으로 재생성. **`snapshots/`의 기존 파일과 `history.json`의 기존 항목은 절대 수정·삭제하지 않습니다.**

## 풀 대시보드 항목 (회차 스냅샷)

각 스냅샷은 다음을 포함합니다:

- 🚨 **RED FLAG** — 24시간 내 신규 변곡점 시그널
- **A. 한국 시장 시황** — KOSPI · 외국인 · VKOSPI · 환율 · 삼성·SK하이닉스
- **B. 미국 빅테크 capex 시그널** — MSFT/GOOGL/META/AMZN
- **C. 빅테크 재무 건전성** — FCF · 채권 · CDS
- **D. 변곡점 키워드 자동 탐지** — guidance/메모리/캐파 표현 추적
- **E. HBM 공급 과잉 6대 시그널** — 수율 · NVIDIA 퀄 · CXMT · 재고 · 가격 · 보고서
- **F. 매크로 / 지정학** — 미·중 · 중동 · 유가
- 📈 **시계열 차트** — 7일 추이

각 섹션마다 "이 지표는 왜 보고 코스피에 어떤 영향이 있나" 설명 패널 포함.

## 6대 RED FLAG 트리거

1. 빅테크 capex 가이던스 동결 또는 하향
2. 빅테크 실적 콜에서 메모리/컴포넌트 비용을 capex 상향 사유로 더 이상 인용하지 않음
3. "capacity constraint eased/resolved" / "캐파 제약 해소" 표현 등장
4. 삼성 HBM4 NVIDIA 퀄 통과 (이미 2025-12 통과 확인)
5. 중국 CXMT의 HBM 양산 진입
6. HBM 채널 재고 위크 수 4주 초과

## 데이터 무결성

- 모든 수치에 1차 출처 링크
- 추정치는 "추정" 명시
- 미확인 데이터는 "확인 필요" (추측치 금지)
- `data/history.json`은 append-only
- `snapshots/` 안의 기존 파일은 불변

## 데이터 소스

KRX · 네이버 금융 · 한경 · 이투데이 · 머니투데이 · 헤럴드경제 · 파이낸셜뉴스 · Bloomberg · Reuters · CNBC · Yahoo Finance · WSJ · FT · 각사 IR · TrendForce · SemiAnalysis · Counterpoint Research
