# Marketing — GitHub Copilot CLI 학습 로드맵

> **캠페인 데이터 정리, 콘텐츠 운영, 경쟁사 모니터링, 리포트 자동화** 등 마케팅 실무를 CLI 로 자동화하는 3-챕터 코스.

이 폴더는 [메인 가이드](../README.md) 의 Marketing 편입니다. **먼저 [메인 README](../README.md) 의 1~8장(설치 · 인증 · 안전 수칙)을 완료**하고 오세요.

---

## 학습 흐름

```mermaid
flowchart LR
    Start(("메인 README<br/>설치 완료")) --> Ch1["Ch 1 · 사용법<br/>★☆☆ · 10분"]
    Ch1 --> Ch2["Ch 2 · 활용<br/>★★☆ · 30분"]
    Ch2 --> Ch3["Ch 3 · 현업 활용<br/>★★★ · 60분+"]
    Ch3 --> Done(("팀 자산화"))

    style Ch1 fill:#c8e6c9
    style Ch2 fill:#fff9c4
    style Ch3 fill:#ffccbc
```

## 챕터 목차

| # | 챕터 | 난이도 | 소요 | 파일 |
|---|---|---|---|---|
| Ch 1 | 사용법 — 처음 5분에 첫 성공 | 초급 ★☆☆ | 10분 | [`ch1-basics.md`](./ch1-basics.md) |
| Ch 2 | 활용 — 반복 업무 자동화 | 중급 ★★☆ | 30분 | [`ch2-application.md`](./ch2-application.md) |
| Ch 3 | 현업 활용 — 정기 리포트 자산화 | 고급 ★★★ | 60분+ | [`ch3-professional.md`](./ch3-professional.md) |

---

## 각 챕터에서 배우는 것

### Ch 1. 사용법 (초급)

**목표**: Copilot CLI 를 처음 켜서 마케터가 자주 다루는 파일에 "말을 걸어보는" 첫 경험.

다루는 예시:
- 폴더에 있는 CSV/이미지 개수 세기
- CSV 컬럼 구조 훑어보기
- 파일 5개 이름 앞에 날짜 붙이기

→ [Ch 1 시작하기](./ch1-basics.md)

### Ch 2. 활용 (중급)

**목표**: 여러 단계로 이뤄진 소규모 자동화. 결과 파일까지 생성.

다루는 예시:
- 이미지 30장 일괄 리사이즈 + 파일명 정리
- 뉴스레터 발송 리스트 클렌징
- 경쟁사 블로그 주간 요약

→ [Ch 2 시작하기](./ch2-application.md)

### Ch 3. 현업 활용 (고급)

**목표**: 여러 데이터 소스를 통합해 정기 리포트를 자동화. 프롬프트를 팀 자산으로.

다루는 예시:
- 광고 채널별 CSV 5개를 통합해서 UTM 성과 요약
- GA4 원본 export → 임원 보고서 초안
- 월간 마케팅 종합 대시보드 (전체 워크플로우)

→ [Ch 3 시작하기](./ch3-professional.md)

---

## 다른 직군

- [Sales — 리드 관리 & 영업 자동화](../sales/)
- [HR / Ops — 채용 & 운영](../hr-ops/)
- [PM / 기획 — 프로젝트 & 데이터](../pm-planning/)

## 관련 문서

- 메인 가이드: [../README.md](../README.md) — 설치 · 인증 · 안전 수칙 · FAQ

## 기여

새로운 마케팅 시나리오나 개선된 프롬프트가 있으면 Issue / PR 로 공유해 주세요.
