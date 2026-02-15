# 03) 작업 분해 및 Worker 배정 프롬프트 (Manager 중심)

목표:
구현 전 실제 실행 가능한 작업 단위를 만들고, 범위를 겹치지 않게 배정한다.

입력으로:
- 01~02단계에서 확정된 SPEC/ARCHITECTURE/CONTRACTS/SCOPE_MAP

실행 프롬프트:

```
아래 규칙으로 작업 계획을 생성해줘:

1) 변경 항목을 최소 단위로 분해 (문서/코드/테스트로 분리)
2) 각 항목의 Owner scope를 지정한다(예: ui/api/data/infra/docs/qa)
3) 공유 파일은 우선순위를 낮춰 계획하고, 변경 필요 사유를 명시한다.
4) 각 작업별 의존성(선행/후행) 표기
5) 각 작업에 Planner/Implementer/Reviewer/Tester/Refactor 역할 제안

안전 가드:
- SCOPE_MAP.md 범위를 벗어나면 즉시 제외
- shared file 수정은 Manager 승인 루트 포함
- Tech Lead가 필요한 변경(아키텍처/보안/유지보수 리스크)은 별도 게이트 칸 지정

출력 형식:
- `작업목록`(체크리스트)
- `병렬 실행 가능 여부`(가능/불가 + 이유)
- `에스컬레이션 포인트`(필요 시)
```

