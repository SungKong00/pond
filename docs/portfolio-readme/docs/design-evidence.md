# 설계 근거

- **음원 준비:** 원본 `docs/architecture/system.md`의 2026-10-12·10-13 전달 개선과 사용자 결정 Q22를 `src/audio/assets.ts`, `shared/audio-assets.ts`, `public/_headers`로 대조했다. 첫 두 파일에 대한 37회→2회는 정상 경로에서 MP3 요청 수를 센 값이며 실제 시작 속도를 비교한 측정값은 아니다.
- **룸 명령·복구:** `docs/architecture/protocol.md`, `docs/planning/implementation/05-recovery.md`, `worker/room.ts`와 `src/audio/controller.ts`. 요청 접수·실행 결과·재합의는 별개이며, 동작 완료에 요청 ID·순번·플레이어 세대를 확인한다.
- **역할 분리:** 결정 Q25/Q27, `b64763d`(현장/테스트 세션 분리), `5f7bec5`(세션 연결 창), `e555bef`(관리자와 관객 채널 제어 공통화). `shared/sessions.ts`와 `src/screens/SessionConnectDialog.tsx`에서 기존 현장과 새 테스트 세션의 경계를 확인했다.
