# AFJ Language (FreeLang v11)

> 이 문서는 "AFJ Language"라는 언어 하나만 다룹니다. 저장소 문서가 이 언어의 다른 이름으로 "FreeLang v11"을 함께 적고 있어, 두 이름을 이 한 문서에서 다룹니다(자세한 이름 관계는 [v11.md](v11.md)).

## 1. 어디에 있나

| 위치 | 만든 때 (KST) | 마지막 커밋 | 비고 |
|---|---|---|---|
| kim27 `/home/kim/kim/platform/freelang-afj` | 첫 커밋 2026-04-03 20:08 | 2026-08-28 23:41 (master 가지) / 모든 가지 중 최신 2026-08-30 21:43 | 커밋 1,763개(master). 원격은 자체 Git 서버 Forgejo `kim/freelang-afj`. 커밋 안 된 변경 114건 |
| GitHub [freelang-v11](https://github.com/kimjindol2025/freelang-v11) | 저장소 생성 2026-04-19 23:48 | 2026-09-17 07:55 (마지막 푸시 2026-09-20 12:02) | 공개, 약 154MB. `package.json` 판 `11.7.11` |
| GitHub [freelang-v11-1](https://github.com/kimjindol2025/freelang-v11-1) | 2026-06-19 19:40 | 푸시 2026-06-20 21:01 | 약 149MB의 사본으로 보임(열어 보지 않음) |
| GitHub [freelang-afj](https://github.com/kimjindol2025/freelang-afj) | 2026-08-19 01:45 | — | **빈 저장소** |

- 사실 관찰: GitHub `freelang-v11`의 마지막 커밋(0235180, 2026-09-17 07:55 "feat: add AI-friendly JSON diagnostics and CLI docs")은 kim27 `freelang-afj`에 **없습니다**. 두 사본의 최신 상태가 서로 다릅니다.
- 함께 쓰는 실행 도구(같은 생태계, 별도 저장소): C로 만든 네이티브 실행기 [freelang-v11-fx](https://github.com/kimjindol2025/freelang-v11-fx)(kim27 `platform/freelang-v11-fx`, C 30개/8,888줄 + .fl 46개/9,591줄, 마지막 커밋 2026-09-24 09:34), [freelang-v11-fx2](https://github.com/kimjindol2025/freelang-v11-fx2)("AFJ Runtime", C, GitHub 생성 2026-07-06, 푸시 2026-09-20). 그 밖에 freelang-front(화면), AFL-Core-2(실행 계약), afl-db(저장소)가 README에 "관련 프로젝트"로 적혀 있습니다.

## 2. 무엇으로 만들었나 / 규모 (kim27 `freelang-afj` 기준)

- TypeScript 483개 / 136,760줄, 자바스크립트 281개 / 98,455줄, **FreeLang 코드(.fl) 681개 / 68,990줄**, C 16개 / 2,689줄.
- `self/` 폴더(540개 파일)에 언어 자신으로 쓴 컴파일러 작업이 있고, 이전 조사 기록에는 "자기 자신을 컴파일하는 단계(stage1)까지 됨"이라고 적혀 있습니다.
- `LANGUAGE_LOCK.md`의 구현 규칙(원문): "새 기능의 기본 구현 언어는 **AFJ Language / FreeLang**이다. JavaScript/TypeScript는 컴파일러, 런타임, 테스트, 빌드 도구를 유지할 때만 사용한다. C는 native compiler/runtime 경로에서만 사용한다."

## 3. 어떤 언어인가

- 문법 모양: **괄호 목록형(리스프 계열)**. `(defn 이름 [인자] 본문)`, `(fn [x] ...)`, `(define ...)`. 확장자 `.fl`, `.fds`, `.airc`.
- `LANGUAGE_LOCK.md`(원문):

> - 외부 표시명: **AFJ Language**
> - 역사적/호환 명칭: **FreeLang v11**
> - 이름 유래: **AFL = AI Free Language** … **AFJ**는 AFL에서 파생된 이름이며, J의 뜻은 정해지지 않았다.
> - 모토: **AI를 위한, AI에 의한, AI가 원한 언어.**

- README 한 줄 소개(원문): "Building a programming language by building real software."(실제 소프트웨어를 만들면서 언어를 만든다) / "AFJ는 완벽한 정적 언어를 목표로 하기보다, AI가 작성한 코드를 빠르게 검사하고 실행하며 수정할 수 있는 작업 흐름을 제공한다."
- 짧은 규칙(원문): "대화는 한국어. 구현은 AFJ/FreeLang. JS/TS는 도구. 검증은 실제 실행."
- `docs/OFFICIAL_LANGUAGE.md`: "FreeLang v11 — 공식 언어 선언", 선언일 2026-05-04, dclub 마이크로서비스·메일 시스템·AI 에이전트의 공식 언어로 지정.

실제 예제 (`examples/closure.fl`, 원문):

```lisp
(define double (fn [x] (* x 2)))
(println (double 5))

(defn make-adder [n]
  (fn [x] (+ n x)))
(define add5 (make-adder 5))
(println (add5 3))
```

## 4. 상태

- 이번 조사에서 GitHub `freelang-v11`을 조사용 상자에 얕게 복제해 **추가 설치 없이** `node bootstrap.js run examples/closure.fl` 실행 → `10, 8, true, false, 7` **정상 출력**. 직접 쓴 `(defn sq [x] (* x x)) (println (sq 7))` → **49**.
- 전체 테스트는 돌리지 않았습니다. 저장소 문서의 주장: "최종 검증: 2026-09-17 (좁은 범위 100/100 통과: parser·interpreter·core·lexer / 전체 스위트는 재측정 필요)". `reports/latest.md`: "실행 런타임 표기(`v11.1.1-dev`) 미정렬은 잔여".
- 활동: 이 목록 중 **유일하게 지금도 움직이는 언어**. kim27 기준 커밋 안 된 변경 114건, GitHub 푸시 2026-09-20, C 실행기 커밋 2026-09-24.

## 5. 다른 FreeLang 이름 언어와 구별되는 점

- 언어 자신(.fl)으로 쓴 코드가 7만 줄 가까이 되고, 규칙으로 "새 기능은 이 언어로"를 못 박아 둔 점.
- C 네이티브 실행기(fx/fx2), 화면 계층, 데이터 저장소, 실제 서비스(VPN·인증·부하분산기 실험 등)까지 **이 언어로 만든 주변 프로젝트가 있는 유일한 경우**.
- 사실 관찰: kim27 `freelang-afj`의 첫 커밋은 GitHub `freelang-v9`의 첫 커밋과 **같은 커밋**(f2ece2176a, 2026-04-03 20:08, "FreeLang v9: AI-Exclusive Programming Language - Complete Implementation")입니다. 이 저장소 안에서 "v11"을 처음 쓴 커밋은 2026-04-16 16:26 "chore: v11 Phase 1~5 자동 완성 … (v11.0.0)"입니다.

## 문서에 적힌 주장 (조사자 해석 아님)

- `LANGUAGE_LOCK.md`: "`FreeLang v11`은 이 언어의 역사적 계보와 기존 문서 호환 명칭이다."
- 커밋 `97730b11`(2026-04-17): "v11 공식 풀스택 언어로 CLAUDE.md 완전 개선 - v2~v10 폐기, v11 독점".
- `docs/PERFORMANCE.md`: "v9 → v10 → v11 진화" 표.
- 위 세 가지는 이 저장소 문서의 표현을 옮긴 것이며, 이 역사 코너는 각 이름을 따로인 언어로 다룹니다.
