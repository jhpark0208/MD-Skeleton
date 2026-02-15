# 00) 프로젝트 시작 프롬프트: 컨텍스트 하이드레이션

목표:
최초로 프로젝트를 건드리기 전, Codex/에이전트가 반드시 읽어야 할 핵심 규칙을 1회 정렬한다.

입력으로:
- 이 저장소의 루트 폴더

실행 프롬프트:

```
다음 순서로 문서를 먼저 읽고 요약해줘:
1) AGENTS.md
2) ARCHITECTURE.md
3) CONTRACTS.md
4) SPEC.md
5) SCOPE_MAP.md
6) DECISIONS.md
7) PARALLEL.md
8) HANDOFF_TEMPLATE.md
9) agents/00-shared.md
10) agents/manager.md
11) agents/tech_lead.md

읽은 내용은 다음 형태로 정리해줘:
- 오케스트레이션 모델(Manager/Tech Lead/Worker)
- SSOT 파일의 현재 상태
- 공유 파일/공유 규칙
- 현재 적용 중인 승인/에스컬레이션 규칙(필수 확인 지점 3개 이상)
- 프로젝트 현재 작업 상태(진행 중인 결정/미완료 항목/모호한 항목)
```

산출물:
- `Context Snapshot` 한 장
- `즉시 질문 5개 이하`로 모호한 부분만 추려서 다음 단계에서 정리

