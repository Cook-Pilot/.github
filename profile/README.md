# CookPilot

조리 화면에서만 동작하는 음성 기반 실시간 AI 조리 코치

CookPilot은 요리 초보자가 실제 조리 중 겪는 단계 진행, 타이밍, 간 조절, 재료 변경, 상태 판단 문제를 돕는 앱입니다. 사용자가 조리 화면에 있을 때만 STT/TTS 기반 음성 조리 모드를 켜고, 단순 명령은 로컬에서 처리하며, 판단이 필요한 예외 상황만 LLM이 현재 레시피 단계 맥락으로 피드백합니다.

조리 후에는 사용자의 결과 피드백을 개인 레시피 버전에 반영해, 같은 레시피를 다시 조리할 때 더 나은 "내 버전"을 제공합니다.

## MVP

2026-07-26까지의 1차 목표는 제한적이지만 실제 동작하는 앱 데모입니다.

```text
레시피 선택
-> 조리 시작
-> 현재 단계 표시 + TTS 안내
-> 단계별 타이머 자동 진행
-> 조리 중 STT 음성 명령 수신
-> 단순 명령은 로컬 처리
-> 예외 상황은 LLM 피드백
-> 조리 후 피드백 입력
-> 개인 레시피 버전 업데이트
-> 다음 조리 때 개인화 버전 제공
```

### 포함 범위

- 레시피 선택
- 조리 시작
- 조리 화면에서 현재 단계 표시
- TTS 단계 안내
- 단계별 타이머 자동 진행
- 조리 중 STT 음성 명령 수신
- 다음/이전/반복/타이머 연장 등 로컬 명령 처리
- "물이 안 끓어", "너무 짜", "덜 익었어", "재료가 없어" 같은 예외 상황 LLM 피드백
- 조리 후 피드백 입력
- 개인 레시피 버전 업데이트
- 다음 조리 때 개인화 버전 제공

### 제외 범위

- 인기 레시피
- 추천 알고리즘 고도화
- 남의 버전 추천
- 사진 기반 익힘/농도 판정
- 커뮤니티
- 장보기/냉장고 연동
- 백그라운드 음성 호출
- 커스텀 호출어
- 대규모 레시피 DB

## 음성 동작 원칙

CookPilot은 항상 사용자의 소리를 듣는 앱이 아닙니다. 음성 수신은 사용자가 조리 세션을 시작하고 조리 화면에 있을 때만 활성화됩니다.

```text
앱 실행
-> 레시피 선택
-> 조리 시작
-> 조리 화면 진입
-> 음성 조리 모드 ON
-> 조리 완료/중단/화면 이탈
-> 음성 조리 모드 OFF
```

단순 명령은 LLM을 호출하지 않고 앱 내부에서 처리합니다. LLM은 현재 단계 맥락이 필요한 예외 상황과 조리 후 개인화 반영에만 사용합니다.

## 문서

| 문서 | 설명 |
|---|---|
| [확정 MVP 설계서](https://github.com/Cook-Pilot/.github/blob/main/docs/confirmed-mvp-voice-loop-spec.md) | 2026-07-10 확정 MVP, STT/TTS 조리 모드, 개인화 루프 |
| [MVP 논의 로그](https://github.com/Cook-Pilot/.github/blob/main/docs/2026-07-10-cookpilot-mvp-conversation-log.md) | 2026-07-10 Codex/GStack 논의 기록 |

## 레포지토리

| 구분 | 레포 | 설명 |
|---|---|---|
| Frontend | [Cook-Pilot/frontend](https://github.com/Cook-Pilot/frontend) | CookPilot 앱 프론트엔드 |
| Backend | [Cook-Pilot/backend](https://github.com/Cook-Pilot/backend) | CookPilot API 및 도메인 서버 |
| Organization | [Cook-Pilot/.github](https://github.com/Cook-Pilot/.github) | 조직 프로필, 공통 문서, PR 템플릿 |

## 기술 스택 초안

- Frontend: Flutter
- Backend: Java / Spring
- AI: STT, TTS, LLM, structured command routing
- Data: recipe session, cook events, personal recipe versions

## 팀

AI·SW 마에스트로 제17기 프로젝트

| 이름 | 역할 |
|---|---|
| 이현우 | 팀장 |
| 전동훈 | 팀원 |
| 이요환 | 팀원 |
