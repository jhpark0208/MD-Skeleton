# 01) 프로젝트 목표·요건 정렬 프롬프트 (Manager 우선)

목표:
초기 SPEC/CONTEXT를 실제 작업 가능한 형태로 정리해, 구현 범위를 고정한다.

입력으로:
- 00단계에서 정리한 `Context Snapshot`

실행 프롬프트:

```
너는 Manager로서 다음 문서들을 업데이트할 준비를 해야 한다.
다음 질문에 대해 5줄 이하로 먼저 답변하고, 동의가 나면 문서를 채워줘:

1) 이번 프로젝트 Feature name과 핵심 목표를 한 문장으로 정의해줘.
2) 이번 스프린트에서 다룰 사용자 스토리를 3개 이하로 선별해줘.
3) Non-goals(이번 단계에서 하지 않을 일)를 5개 이하로 정의해줘.
4) 보안, 성능, 품질에서 이번 단계의 제약을 정리해줘.

규칙:
- SPEC.md의 Placeholder(<> 형식)는 반드시 실값으로 대체되어야 한다.
- `Do NOT implement speculative behavior` 규칙을 위반하지 않기.
- 필요시 CONTEXT.md의 "Current Focus"를 업데이트한다.

산출물:
- `SPEC.md`에 Feature/Actors/User Stories/FR/Success Criteria 최소 버전 반영
- `CONTEXT.md` Current Focus, Work Log (최신 항목)
- 미확정 항목은 `⚠` 접두사로 TODO화
```

