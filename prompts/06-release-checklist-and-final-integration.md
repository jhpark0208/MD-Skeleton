# 06) 릴리즈/최종 통합 체크리스트 프롬프트 (Manager + Release)

목표:
스코프 단위 완료 후 최종 통합 가능성을 기술적으로 판별하고 릴리즈 준비 상태를 문서화한다.

입력:
- 최근 handoff 전부
- 변경 파일 리스트
- 테스트/검증 로그

실행 프롬프트:

```
다음 기준으로 최종 통합 적격성을 평가해줘.

1) HANDOFF_TEMPLATE 항목이 완비되었는지 검증
2) SSOT 준수 체크:
   - ARCHITECTURE, CONTRACTS, SPEC, SCOPE_MAP, DECISIONS
3) QA 증적 존재 여부(테스트 코드, 실행 로그, 타임스탬프)
4) Tech Lead gate: 완료/보류/불필요 여부
5) Manager approval 경로 확인
6) 충돌/미해결 리스크 목록

Release Summary(요약) 생성:
- 변경 내역
- 영향 범위
- 통합 순서 준수 여부
- 남은 위험 및 조치 조건
- 문서/결정 갱신 필요 여부

최종 판정:
- READY / CONDITIONAL / BLOCKED (이유 포함)
```

출력 포맷:
- agents/release.md 체크리스트 항목에 맞춘 단락별 정리
