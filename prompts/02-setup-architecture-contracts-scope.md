# 02) 아키텍처·계약·소유권 동기화 프롬프트 (Manager + Tech Lead)

목표:
SSOT 1차 골격을 기술적 일관성 기준으로 정합한다.

입력으로:
- 01단계에서 정리한 Feature/요건

실행 프롬프트:

```
아래 순서로 작업 초안을 작성해줘.

1) ARCHITECTURE.md
- 시스템 타입, 구성요소, 의존성 규칙 초안
- 금지되는 의존성/계층 위반 사항

2) CONTRACTS.md
- 핵심 인터랙션(UI/Application/Data) 최소 계약 정의
- 에러 구조 기본 형식, 보안 관련 규칙(민감정보 노출 금지 등)

3) SCOPE_MAP.md
- 현재 저장소 경로 기준 실제 소유권 경로 반영
- 공유 파일(Manager-owned)과 임시 오너십 규칙 명시

4) DECISIONS.md
- 이번 초기 구조 설정과 관련한 DECISION-### 1건 생성
- 왜 이 구조가 채택됐는지 판단 근거 3줄 이상 기록

의사결정 체인:
- SSOT 문서 간 충돌 시: ARCHITECTURE > CONTRACTS > SPEC > SCOPE_MAP > DECISIONS
- 구조적 위험/보안/장기 유지보수성은 Tech Lead 게이트 통과 후 확정

산출물:
- 위 4개 문서를 수정 가능한 수준으로 모두 채움
- `DECISIONS.md`에 적용결정 + 영향범위 + 추적 ID를 남김
```

