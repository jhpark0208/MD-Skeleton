# 초기 세팅 프롬프트 모음

이 폴더는 프로젝트 초기 오케스트레이션 시작 시 사용할 순차 템플릿이다.

## 실행 순서

1. `00-bootstrap-read-context.md`
   - 문서 하이드레이션 + 현재 규칙 스냅샷
2. `01-define-goals-and-scope.md`
   - SPEC + CONTEXT로 목표/요건 고정
3. `02-setup-architecture-contracts-scope.md`
   - ARCHITECTURE / CONTRACTS / SCOPE_MAP / DECISIONS 초기 동기화
4. `03-plan-and-assign-workers.md`
   - 작업 분해, 오너십 할당, 병렬 실행 가이드
5. `04-start-coding-and-handoff.md`
   - 초기 구현 실행 및 handoff 템플릿 준수

각 프롬프트는 AGENTS 파이프라인(Manager → Tech Lead → Worker)을 전제로 작성되며,
필요하면 템플릿 안의 출력 형식을 그대로 사용해 바로 이어서 문서화하면 된다.

## 운영 후속 프롬프트

6. `05-mid-cycle-review-and-adjustment.md`
   - 중간 점검 및 범위 조정
7. `06-release-checklist-and-final-integration.md`
   - 최종 통합/릴리즈 준비 체크
8. `07-incident-response-and-debug-cycle.md`
   - 장애/실패 대응
9. `08-decision-log-and-retrospective.md`
   - 회고·의사결정 정리
