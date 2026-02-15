# 08) 의사결정 정리 및 회고 프롬프트 (Manager + Tech Lead)

목표:
스프린트 종료 또는 큰 설계 변경 직후, 결정 이력과 운영 학습을 축적한다.

입력:
- DECISIONS 변경 이력
- 완료된 handoff
- CONTEXT Work Log

실행 프롬프트:

```
최근 작업을 기반으로 회고 가능한 포맷으로 정리해줘.

1) 이번 주/스프린트 핵심 결정 3개 정리
2) 각 결정의 배경/옵션/선택 근거 재기록
3) 실제 효과(예상 vs 실제)
4) 발생한 리스크 3개 이하 및 재발 방지안
5) CONTEXT.md 갱신 포인트
6) 다음 사이클을 위한 개선안(프로세스/문서/도구)

회고 산출물을 DECISIONS.md에 기록 가능한 Decision Record 형태로 정리:
- DECISION-### 추가 또는 Supersede
- 영향 범위 + 후속 조치

또한 CONTEXT.md Lessons Learned 항목에 반영할 1개 이상 문장 생성.
```

규칙:
- 가정이 아닌 실제 근거 기반으로만 기록
- 필요 시 DECISIONS의 Superseded/Deprecated를 사용해 이력 관리
