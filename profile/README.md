# CookPilot

요리할수록 사용자의 입맛을 기억하는 실시간 AI 조리 코치

초보 요리자가 조리 중 겪는 타이밍, 불 조절, 간 조절, 상태 판단 문제를 음성 대화로 지원하는 AI 조리 코치입니다. 조리 세션의 행동, 수정 메모, 결과 평가를 개인 레시피 메모리에 축적하고, 다음 조리 시 개인화된 단계·시간·간 조절을 추천합니다.

<!-- 데모 링크 / 시연 영상 / 스크린샷 추가 예정 -->

## 주요 기능

- **실시간 음성 조리 코치** — 사용자의 발화에 대해 현재 단계와 레시피 상태를 기준으로 다음 행동, 타이머, 주의사항을 음성으로 안내
- **개인 레시피 메모리** — 맛, 익힘 정도, 실패 원인, 실제 소요 시간 등을 저장하여 반복 조리 시 사용자 고유의 레시피 버전을 축적
- **개인화 재조리 추천** — 지난 조리 기록을 바탕으로 다음 조리에 적용할 간·시간·순서 조정안을 제안

## 시스템 구성

```
사용자 접점 (PWA · 음성 UI)
        │
API 계층 (인증 · 조리 세션 · 레시피 관리)
        │
AI 오케스트레이션 (LLM Agent · STT/TTS · RAG · Function Calling)
        │
도메인 엔진 (조리 세션 상태 머신 · 레시피 태스크 그래프 · 개인화 추천)
        │
데이터 계층 (PostgreSQL · Vector DB · Object Storage)
```

<!-- 시스템 구성도 이미지(Fig 2)를 docs/ 에 추가 후 아래로 교체 권장 -->
<!-- ![시스템 구성도](docs/architecture.png) -->

## 레포지토리 구성

| 구분 | 레포 | 설명 |
|------|------|------|
| Frontend | [cookpilot-frontend](https://github.com/Cook-Pilot/frontend) |  |
| Backend | [cookpilot-backend](https://github.com/Cook-Pilot/backend) |  |

<!-- 조직이름 부분을 실제 레포 주소로 교체 -->

## 기술 스택

- **Frontend** — Flutter
- **Backend** — Java/Spring
- **AI** — LLM(GPT-4o), STT/TTS, RAG, Function Calling, Agent Orchestration
<!-- 백엔드 언어/프레임워크 및 사용 Vector DB 확정 후 기입 -->

## 시작하기

각 레포의 README를 참고합니다. 아래는 작성 예정 항목입니다.

```bash
# 작성 예정
# 1. 레포 클론
# 2. 환경 변수 설정 (.env)
# 3. 의존성 설치
# 4. 실행
```

<!-- 프론트/백 로컬 실행 방법, 필요한 .env 키 목록(OPENAI_API_KEY 등) 정리 -->

## 팀 구성 (B1P3)

| 이름 | 역할 |
|------|------|
| 이현우 | 팀장 |
| 전동훈 |  |
| 이요환 | |

<!-- 필요 시 각 팀원 GitHub 프로필 링크 추가 -->


<!--
추후 추가 권장 항목
- 라이선스 (LICENSE) — 상업화/출시 계획 시 신중히 결정
- 스크린샷 / 데모
- API 문서 링크 (Swagger/Postman)
- 컨벤션 문서 (커밋 규칙, 브랜치 전략, PR 템플릿)
- 기여 가이드 (CONTRIBUTING.md)
- 배포 주소
-->

AI·SW 마에스트로 제17기 프로젝트
