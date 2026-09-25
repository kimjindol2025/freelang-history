# 지시서: 킬 체인 ① V11 조용한 실패 전수 조사 v1.0

## 0. 참고 문서
- 킬 체인 분석: https://github.com/kimjindol2025/freelang-history/blob/main/analysis/2026-09-25-freelang-kill-chain-analysis.md
  (포제이오 원본: fg.dclub.kr/kim/freelang-history)
- 이 문서의 4-5절 "백엔드 약점 1. 조용한 실패"가 이번 작업 대상이다.

## 1. 목표
V11 해석기에서 실패가 오류로 드러나지 않고 null, false, [], 빈 문자열 등으로
숨겨지는 곳을 전부 찾아 목록으로 만든다. 이번 단계는 조사만 한다.

## 2. 대상
- 작업 폴더: kim27 /home/kim/kim/platform/freelang-afj
- 비교 기준: Forgejo kim/freelang-v11 커밋 31075c09
- 우선 볼 파일: src/eval-builtins.ts, src/eval-special-forms.ts,
  src/stdlib-*.ts, src/eval-ai-blocks.ts, src/stdlib-timer.ts

## 3. 이미 알려진 사례 (반드시 포함해서 재확인)
- eval-builtins.ts:398 read-file 실패 시 null
- eval-builtins.ts:399 write-file 실패 시 false
- eval-special-forms.ts:2096 parallel 안 오류를 catch { val = null }
- PAIN.fds:77 db-exec 첫 인자 종류에 따라 다른 DB에 조용히 연결
- 커밋 b098a14536 set_interval 콜백 오류를 stderr로만 출력 (고쳐졌는지 확인)
- 커밋 32e90f895a "조용히 []/null 반환" 관련 (고쳐졌는지 확인)

## 4. 할 일
1. 빈 catch, catch 후 null/false/[]/"" 반환, 오류를 stderr로만 찍고 넘어가는 곳을 모두 찾는다.
2. 각 곳마다 파일:줄, 함수 이름, 무엇을 숨기는지, 스크립트 쪽에서 보이는 결과를 적는다.
3. 위험도를 상/중/하로 매긴다. 기준: 데이터 손실·잘못된 연결 = 상, 디버깅 방해 = 중, 의도된 기본값 = 하.
4. "의도된 기본값"(예: file_read_or 같은 이름에 기본값이 드러난 함수)은 따로 구분한다.
5. freelang-afj와 freelang-v11(31075c09)에서 같은 곳이 다르면 차이를 적는다.
6. 이 목록을 고치면 영향을 받는 앱(ai-village-fl, reservation-app 등)이 있는지 grep으로만 확인한다.

## 5. 금지 사항
- 코드 수정 금지 (원인 목록 확정 전 수정 금지)
- git add/commit/push, reset, checkout, clean, stash 금지
- PM2 조작 금지
- 시간 제한 늘리기, 시험 건너뛰기 금지
- 저장소 통째 복제 금지 (필요한 파일만 읽기)
- 토큰 출력·저장·복사 금지

## 6. 검증
- 목록의 각 항목은 실제 줄을 열어 확인한 것만 올린다.
- 가능하면 작은 .fl 예제를 /tmp에서 실행해 "실패인데 오류가 안 나는" 것을 직접 보인다.
  실행하지 못한 항목은 "실행 확인 안 함"으로 표시한다.

## 7. 보고서
- 위치: freelang-afj/reports/2026-09-25-kill-chain-1-silent-failure-inventory-v1.0.md
  (보고서 파일 작성만 허용, 커밋은 하지 않음)
- 형식:
  - 상태: 완료 / 부분 완료 / 막힘
  - 요약 (3줄)
  - 전체 목록 표: 번호 | 파일:줄 | 함수 | 숨기는 것 | 위험도 | 실행 확인 여부
  - 상 위험 항목별 고치는 방향 제안 (제안만, 수정 아님)
  - freelang-afj와 v11 차이
  - 영향받는 앱
  - 확인하지 못한 것

## 8. 다음 단계
보고서를 사용자가 확인하고 승인하면 그때 ① 수정 지시서를 따로 낸다.
① 완료·검증 후에만 ② 전역 상태 문제로 넘어간다.
