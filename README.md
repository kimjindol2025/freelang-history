# 프리랭 역사 코너

여기 모은 FreeLang들은 **한국어, 영어, 일본어처럼 각각 따로인 언어**입니다. "v1", "v2" 같은 숫자는 **이름의 일부일 뿐**이고, 어느 언어가 다른 언어에서 나왔다거나 뒤를 잇는다는 뜻이 아닙니다. 그래서 이 코너는 각 언어를 나란히 놓고 비교만 합니다. 표는 이름순으로 정렬했고, 날짜는 그냥 한 칸의 정보입니다.

- 조사일: 2026-09-25. 날짜·시각은 모두 한국 시간(KST).
- **본 저장소는 사용자의 자체 Forgejo 서버 [fg.dclub.kr](https://fg.dclub.kr)(계정 `kim`, 저장소 800개 중 792개 비공개)** 이고, GitHub 계정 kimjindol2025는 **백업**입니다. 이번 판은 본 저장소를 기준으로 다시 조사했습니다. 링크는 비공개 저장소라 로그인해야 열립니다.
- 백업이 본 저장소와 다른 경우가 많습니다. FreeLang v3·v8·v10·v12는 **백업이 빈 저장소**이고 코드는 본 저장소에만 있습니다. v2·v4·v5·v6은 백업이 3월에 멈춰 있고 본 저장소에 커밋이 수십~백여 개 더 있습니다(백업에만 있는 커밋도 조금 있어 기록이 갈라져 있음). AFJ(v11)는 본 저장소가 9/20, 백업이 9/17입니다.
- fg.dclub.kr의 "만든 날"은 거의 모든 저장소가 2026-08-21 무렵(서버 이전일로 보임)이라, 시기는 **커밋 날짜**로 적었습니다.
- 근거: 본 저장소를 kim27에서 읽기 전용으로 조회·복제해 파일·커밋을 셈. GitHub 백업과 커밋을 하나하나 대조함. 일부 언어는 조사용 컴퓨터에 복사해 실제로 실행해 봤고, 그 결과를 "상태"에 적었습니다.
- 증거를 찾지 못한 것은 "**확인 안 됨**"이라고 적었습니다. 저장소 문서가 언어들 사이의 관계를 주장하는 경우에는 각 문서 끝 "**문서에 적힌 주장**"에 원문 그대로 따로 옮겼습니다. 그것은 그 문서의 표현이지 이 코너의 설명이 아닙니다.
- 용어: **저장소**=코드를 모아 둔 곳, **커밋**=저장 기록 한 건, **해석기**=코드를 읽어 바로 실행하는 프로그램, **괄호 목록형(리스프 계열)**=`(함수 인자 인자)`처럼 모든 것을 괄호로 묶는 문법, **중괄호형**=`fn 이름() { ... }`처럼 C·자바스크립트와 비슷한 문법.

## 한눈에 비교

| 이름 | 본 저장소 (fg.dclub.kr) | GitHub 백업 | 커밋 기간 (KST) | 구현 언어 | 한 줄 설명 | 상태 | 자세히 |
|---|---|---|---|---|---|---|---|
| AFJ Language (FreeLang v11) | [freelang-v11](https://fg.dclub.kr/kim/freelang-v11), [freelang-afj](https://fg.dclub.kr/kim/freelang-afj) (+ kim27 작업본) | [freelang-v11](https://github.com/kimjindol2025/freelang-v11) — 9/17에서 멈춤(**늦음**). freelang-afj는 빈 저장소 | 2026-04-03 ~ **2026-09-20** | TypeScript·JS + FreeLang 코드 7만 줄 + C 실행기 | 괄호 목록형(리스프 계열). "AI를 위한, AI에 의한, AI가 원한 언어." | **실행 확인**(예제 정상). 지금도 활동 중 | [afj.md](versions/afj.md) |
| FreeLang v1 | 없음 | [freelang](https://github.com/kimjindol2025/freelang) 안 명세서뿐(본 저장소에는 이 저장소 없음) | 명세서 2026-02-17 | 확인 안 됨 | 의도(intent)를 적는 들여쓰기형 명세 문법 | 코드 없음 | [v1.md](versions/v1.md) |
| FreeLang v10 | [freelang-v10](https://fg.dclub.kr/kim/freelang-v10) (+ freelang-v9 안 커밋 12개) | freelang-v10 **빈 저장소** | 2026-04-15 ~ 2026-04-21 | FreeLang(.fl) 8,386줄 + JS 2,416줄 | 괄호 목록형. 백엔드·화면·운영을 한 언어로 만드는 풀스택 업무 앱 | 실행 실패(불러 쓰는 v9 해석기의 절대 경로 문제) | [v10.md](versions/v10.md) |
| FreeLang v11 | = AFJ Language의 다른 이름. 부속 저장소 [freelang-v11-fx](https://fg.dclub.kr/kim/freelang-v11-fx) 등 | 일부 부속만 백업 | — | — | AFJ Language 문서 참고 | — | [v11.md](versions/v11.md) |
| FreeLang v12 | [freelang-v12](https://fg.dclub.kr/kim/freelang-v12), [v12-alpha](https://fg.dclub.kr/kim/v12-alpha) | 두 곳 모두 **빈 저장소** | 2026-05-01 ~ 2026-05-17 | FreeLang(.fl) 34개 + JS 실행기 | `[FUNC]` 블록 문법, 패키지(KPM) 엔진 | freelang-v12 **실행 확인**(49, 5 출력). v12-alpha는 실행 실패 | [v12.md](versions/v12.md) |
| FreeLang v2 | [freelang-v2](https://fg.dclub.kr/kim/freelang-v2), [v2-freelang-ai](https://fg.dclub.kr/kim/v2-freelang-ai), [FreeLang_v2_1](https://fg.dclub.kr/kim/FreeLang_v2_1) 등 | 3/12~13에서 멈춤, 본 저장소에만 117·173개. FreeLang_v2_1은 빈 저장소 | 2026-02-15 ~ **2026-04-15** | TypeScript (40만 줄대), v2_1은 C | 중괄호형. "자기 자신의 소스를 컴파일 및 린트할 수 있는 제로 외부 의존성 AI 기반 프로그래밍 언어" | **실행 확인**(백업판, 예제 정상) | [v2.md](versions/v2.md) |
| FreeLang v3 | [v3-freelang-ai](https://fg.dclub.kr/kim/v3-freelang-ai) | **빈 저장소** | 2026-02-18 ~ 2026-03-26 | TypeScript 약 5만 줄 | 파이썬식 들여쓰기 + 대문자 명령어(`INT x = 10`, `IF x > 5:`) | 실행은 되나 결과 "undefined". 시험 4개 중 3개 통과 | [v3.md](versions/v3.md) |
| FreeLang v4 | [freelang-v4](https://fg.dclub.kr/kim/freelang-v4) 등 | 3/26에서 멈춤, 본 저장소에만 81개. freelang-langv4는 본 저장소의 4/5 무렵 사본으로 보임 | 2026-02-19 ~ **2026-04-10** | TypeScript 약 2만 줄 + .fl 3만 7천 줄 | 중괄호형 정적 타입 + 바이트코드 가상머신 | 본 저장소판 테스트 266 통과/11 실패, 예제 1개 실패 | [v4.md](versions/v4.md) |
| FreeLang v5 | [freelang-v5-ai](https://fg.dclub.kr/kim/freelang-v5-ai) | 3/4에서 멈춤, 본 저장소에만 4개 | 2026-03-03 ~ 2026-03-26 | TypeScript 약 8천 줄 | 의도 → 여러 언어 코드 생성기. "Human 10% + AI 90%" | 백업판은 '데모 모드'로 빈 함수만 생성 | [v5.md](versions/v5.md) |
| FreeLang v6 | [freelang-v6](https://fg.dclub.kr/kim/freelang-v6) | 3/26에서 멈춤, 본 저장소에만 4개 | 2026-03-01 ~ 2026-04-05 | TypeScript + C 코드 생성 | 중괄호형, 모듈·enum·제네릭, C로 빌드 | **실행 확인**(백업판), 테스트 4,082 통과/135 실패 | [v6.md](versions/v6.md) |
| FreeLang v7 | 없음 | 없음 | 확인 안 됨 | 확인 안 됨 | 다른 저장소 문서에 이름만 나옴 | 찾지 못함 | [v7.md](versions/v7.md) |
| FreeLang v8 | [freelang-v8-ml](https://fg.dclub.kr/kim/freelang-v8-ml) | **빈 저장소** | 2026-03-24 하루(00:12 ~ 12:01) | TypeScript 약 5만 줄 + `.fl8` 23개 | 텐서를 기본 타입으로 둔 기계학습 언어 | 예제 **실행 확인**(hello.fl8 정상), `npm test` 실패 | [v8.md](versions/v8.md) |
| FreeLang v9 | [freelang-v9](https://fg.dclub.kr/kim/freelang-v9), [freelang-v9-lang](https://fg.dclub.kr/kim/freelang-v9-lang), [freelang-v9-registry](https://fg.dclub.kr/kim/freelang-v9-registry) | 본체 master는 같음(가지만 본 저장소에 6개 더). -lang·-registry는 빈 저장소 | 2026-04-03 ~ 2026-05-09 | TypeScript 약 12만 줄 + .fl | 괄호 목록형 + `[FUNC]`·`[ROUTE]` 블록, AI 호출 내장 | **실행 실패**(절대 경로 박힘). 테스트 345 통과/154 실패 | [v9.md](versions/v9.md) |

## 언어별 문서

- [AFJ Language (FreeLang v11)](versions/afj.md)
- [FreeLang v1](versions/v1.md)
- [FreeLang v10](versions/v10.md)
- [FreeLang v11](versions/v11.md)
- [FreeLang v12](versions/v12.md)
- [FreeLang v2](versions/v2.md)
- [FreeLang v3](versions/v3.md)
- [FreeLang v4](versions/v4.md)
- [FreeLang v5](versions/v5.md)
- [FreeLang v6](versions/v6.md)
- [FreeLang v7](versions/v7.md)
- [FreeLang v8](versions/v8.md)
- [FreeLang v9](versions/v9.md)
- [번호가 없는 FreeLang 이름 저장소](others.md)
