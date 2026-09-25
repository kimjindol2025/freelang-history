# AFJ Language (FreeLang v11)

> 이 문서는 "AFJ Language"라는 언어 하나만 다룹니다. 저장소 문서가 이 언어의 다른 이름으로 "FreeLang v11"을 함께 적고 있어, 두 이름을 이 한 문서에서 다룹니다(자세한 이름 관계는 [v11.md](v11.md)).

## 1. 어디에 있나

| 구분 | 위치 | 첫 커밋 (KST) | 마지막 커밋 | 커밋 수 | 비고 |
|---|---|---|---|---|---|
| **본 저장소** | [fg.dclub.kr/kim/freelang-afj](https://fg.dclub.kr/kim/freelang-afj) | 2026-04-03 20:08 | **2026-08-30 02:25** (master, "feat: add isolated SSH PTY runtime") | 1,769 (master) | 약 167MB, 가지 5개 |
| **본 저장소** | [fg.dclub.kr/kim/freelang-v11](https://fg.dclub.kr/kim/freelang-v11) | 2026-04-03 20:08 | **2026-09-20 22:11** (master, "feat(cli): add safe parenthesis fixer") | 1,692 (master) | 약 158MB, 가지 28개. `package.json` 판 11.7.11(GitHub 백업판에서 확인) |
| 본 저장소 | [fg.dclub.kr/kim/freelang-v11-1](https://fg.dclub.kr/kim/freelang-v11-1) | 2026-04-03 20:08 | 2026-06-08 03:14 | 1,629 | 사본으로 보임 |
| 본 저장소 | [fg.dclub.kr/kim/freelang-native](https://fg.dclub.kr/kim/freelang-native) | 2026-04-03 20:08 | 2026-05-25 11:57 | 1,479 | 약 146MB. 이름에 번호가 없지만 첫 커밋이 같음 |
| kim27 작업본 | `/home/kim/kim/platform/freelang-afj` (원격: 본 저장소 `kim/freelang-afj`) | 2026-04-03 20:08 | 로컬 master 2026-08-28 23:41 | 1,763 | 로컬 master는 본 저장소 master(8/30)를 아직 받지 않은 상태. 커밋 안 된 변경 114건 |
| GitHub 백업 | [freelang-v11](https://github.com/kimjindol2025/freelang-v11) | — | 2026-09-17 07:55 | — | 공개. 이 커밋은 본 저장소 `freelang-v11`에 있고, 본 저장소에는 그 뒤 9/20 커밋까지 있음 → **백업이 늦음** |
| GitHub 백업 | [freelang-afj](https://github.com/kimjindol2025/freelang-afj) | — | — | 0 | **빈 저장소** |

- 사실 관찰: 본 저장소의 `freelang-afj`와 `freelang-v11`은 **첫 커밋이 같지만 최신 커밋이 서로 다릅니다**. `freelang-v11`의 9/20 커밋은 `freelang-afj`에 없습니다. 두 저장소가 따로 계속 쓰이고 있습니다(어느 쪽이 정본인지는 문서로 **확인 안 됨**. `freelang-afj` README는 자기 이름을 "freelang-afj (AFJ Language)"라고 적음).
- fg.dclub.kr의 저장소 "만든 날"은 모두 2026-08-21 무렵(서버 이전일로 보임)이라 커밋 날짜를 적었습니다.
- 함께 쓰는 실행 도구(같은 생태계, 별도 저장소): C 네이티브 실행기 [freelang-v11-fx](https://fg.dclub.kr/kim/freelang-v11-fx)(kim27 로컬 마지막 커밋 2026-09-24), [freelang-v11-fx2](https://fg.dclub.kr/kim/freelang-v11-fx2)("AFJ Runtime"), [freelang-v11-fx2-aarch64-verify](https://fg.dclub.kr/kim/freelang-v11-fx2-aarch64-verify)(본 저장소에만 있음). 그 밖에 freelang-front, AFL-Core-2, afl-db.

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

- 이번 조사에서 GitHub 백업 `freelang-v11`(9/17 판)을 조사용 컴퓨터에 얕게 복제해 **추가 설치 없이** `node bootstrap.js run examples/closure.fl` 실행 → `10, 8, true, false, 7` **정상 출력**. 직접 쓴 `(defn sq [x] (* x x)) (println (sq 7))` → **49**.
- 전체 테스트는 돌리지 않았습니다. 저장소 문서의 주장: "최종 검증: 2026-09-17 (좁은 범위 100/100 통과: parser·interpreter·core·lexer / 전체 스위트는 재측정 필요)". `reports/latest.md`: "실행 런타임 표기(`v11.1.1-dev`) 미정렬은 잔여".
- 활동: 이 목록 중 **유일하게 지금도 움직이는 언어**. 본 저장소 `freelang-v11` 커밋 2026-09-20, kim27 작업본 커밋 안 된 변경 114건, C 실행기 커밋 2026-09-24.

## 5. 다른 FreeLang 이름 언어와 구별되는 점

- 언어 자신(.fl)으로 쓴 코드가 7만 줄 가까이 되고, 규칙으로 "새 기능은 이 언어로"를 못 박아 둔 점.
- C 네이티브 실행기(fx/fx2), 화면 계층, 데이터 저장소, 실제 서비스(VPN·인증·부하분산기 실험 등)까지 **이 언어로 만든 주변 프로젝트가 있는 유일한 경우**.
- 사실 관찰: `freelang-afj`·`freelang-v11`의 첫 커밋은 `freelang-v9`의 첫 커밋과 **같은 커밋**(f2ece2176a, 2026-04-03 20:08, "FreeLang v9: AI-Exclusive Programming Language - Complete Implementation")입니다. 이 저장소 안에서 "v11"을 처음 쓴 커밋은 2026-04-16 16:26 "chore: v11 Phase 1~5 자동 완성 … (v11.0.0)"입니다.

## 문서에 적힌 주장 (조사자 해석 아님)

- `LANGUAGE_LOCK.md`: "`FreeLang v11`은 이 언어의 역사적 계보와 기존 문서 호환 명칭이다."
- 커밋 `97730b11`(2026-04-17): "v11 공식 풀스택 언어로 CLAUDE.md 완전 개선 - v2~v10 폐기, v11 독점".
- `docs/PERFORMANCE.md`: "v9 → v10 → v11 진화" 표.
- 위 세 가지는 이 저장소 문서의 표현을 옮긴 것이며, 이 역사 코너는 각 이름을 따로인 언어로 다룹니다.
