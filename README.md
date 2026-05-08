# kospi-signals

**코스피 · 빅테크 · HBM 시그널 대시보드** — 하루 2회 자동 갱신 (08:00 KST 장 시작 전 / 17:00 KST 장 마감 후)

라이브 대시보드: **https://makalee63.github.io/kospi-signals**

## 구성

- `index.html` — 단일 페이지 대시보드 (RED FLAG · 한국 시장 · 빅테크 capex · 재무 건전성 · 변곡점 키워드 · HBM 6대 시그널 · 매크로)
- `data/history.json` — append-only 일일 스냅샷 (시계열 누적, 절대 수정·삭제 금지)

## 추적 시그널

1. **빅테크 capex 가이던스**: 동결·하향 시 사이클 정점 신호
2. **메모리/컴포넌트 비용 인용 변화**: 더이상 인용되지 않으면 공급 정상화 시그널
3. **"Capacity constraint eased/resolved"**: 캐파 제약 해소 표현 등장 추적
4. **삼성 HBM4 NVIDIA 퀄 통과** (2025-12 통과 확인됨)
5. **중국 CXMT HBM 양산 진입**
6. **HBM 채널 재고 위크 수** (>4주 시 공급과잉)

## 데이터 무결성

- 모든 수치에 1차 출처 링크 첨부
- 추정치는 "추정" 명시
- 미확인 데이터는 "확인 필요" 표기 (추측치 금지)
- `data/history.json`은 append-only
