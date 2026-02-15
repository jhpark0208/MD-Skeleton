# 04) 초기 구현 시작 + 최초 Handoff 프롬프트 (Worker/Manager)

목표:
첫 구현 단위를 실행하고, 최초 통합이 가능한 형태로 handoff를 준비한다.

입력으로:
- 03단계 작업계획
- agents/* Role 가이드

실행 프롬프트:

```
너는 Worker(또는 Tech Lead 협업 하의 Planner/Implementer)다.
다음 규칙으로 첫 실행을 진행해:

1) 본인 scope만 변경
2) 코드 변경 전 SSOT/Scope ownership 확인
3) 변경 파일별로 HANDOFF_TEMPLATE.md의 항목을 미리 작성
4) Tech Lead 승인 필요 항목이면 gate 상태를 pending으로 명시
5) 변경 후 Validation 수행 (테스트/계약/아키텍처 점검)

작업 종료 시 다음 형식으로 handoff 초안 반환:
- Scope Information (scope, owned paths, changed files)
- Summary of Changes
- SSOT compliance 체크(ARCHITECTURE/CONTRACTS/SPEC/SCOPE_MAP/DECISIONS)
- Validation 결과
- Risk/Impact
- Required Manager/Tech Lead Actions
```

주의:
- `SSOT` 위반이 발견되면 즉시 중단하고 기존 계획을 수정 요청해야 한다.
- 구현 방식은 최소 변경 원칙을 유지한다.

