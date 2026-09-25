# 프리랭 역사 코너

여기 모은 FreeLang들은 **한국어, 영어, 일본어처럼 각각 따로인 언어**입니다. "v1", "v2" 같은 숫자는 **이름의 일부일 뿐**이고, 어느 언어가 다른 언어에서 나왔다거나 뒤를 잇는다는 뜻이 아닙니다. 그래서 이 코너는 각 언어를 나란히 놓고 비교만 합니다. 표는 이름순으로 정렬했고, 날짜는 그냥 한 칸의 정보입니다.

- 조사일: 2026-09-25. 날짜·시각은 모두 한국 시간(KST).
- 근거: GitHub 계정 kimjindol2025의 저장소(읽기 전용으로 복제해 파일·커밋을 셈)와 kim27 컴퓨터의 폴더(읽기만 함). 일부 언어는 조사용 컴퓨터에 복사해 실제로 실행해 봤고, 그 결과를 "상태"에 적었습니다.
- 증거를 찾지 못한 것은 "**확인 안 됨**"이라고 적었습니다. 저장소 문서가 언어들 사이의 관계를 주장하는 경우에는 각 문서 끝 "**문서에 적힌 주장**"에 원문 그대로 따로 옮겼습니다. 그것은 그 문서의 표현이지 이 코너의 설명이 아닙니다.
- 용어: **저장소**=코드를 모아 둔 곳, **커밋**=저장 기록 한 건, **해석기**=코드를 읽어 바로 실행하는 프로그램, **괄호 목록형(리스프 계열)**=`(함수 인자 인자)`처럼 모든 것을 괄호로 묶는 문법, **중괄호형**=`fn 이름() { ... }`처럼 C·자바스크립트와 비슷한 문법.

## 한눈에 비교

| 이름 | 위치 | 만든 시기 (KST) | 구현 언어 | 한 줄 설명 | 상태 | 자세히 |
|---|---|---|---|---|---|---|
| AFJ Language (FreeLang v11) | kim27 `platform/freelang-afj`, GitHub [freelang-v11](https://github.com/kimjindol2025/freelang-v11) | 첫 커밋 2026-04-03 / GitHub 2026-04-19 | TypeScript·JS + FreeLang 코드 7만 줄 + C 실행기 | 괄호 목록형(리스프 계열). "AI를 위한, AI에 의한, AI가 원한 언어." | **실행 확인**(예제 정상). 지금도 활동 중(9/20 푸시, 미커밋 114건) | [afj.md](versions/afj.md) |
| FreeLang v1 | 전용 저장소 없음. `freelang` 저장소 안 명세서뿐 | 명세서 2026-02-17 | 확인 안 됨 | 의도(intent)를 적는 들여쓰기형 명세 문법. "AI가 쉽게 쓸 수 있는 언어" | 코드 없음. 문서끼리 숫자가 다름 | [v1.md](versions/v1.md) |
| FreeLang v10 | `freelang-v9` 저장소 안 커밋 12개. `freelang-v10`은 빈 저장소 | 2026-04-16 (커밋) | TypeScript(v9 저장소 해석기 위) | 괄호 목록형 + `[FUNC]` 블록. "백엔드+프론트엔드+인프라를 한 언어로" | 전용 코드 없음 | [v10.md](versions/v10.md) |
| FreeLang v11 | = AFJ Language의 다른 이름(`LANGUAGE_LOCK.md`) | — | — | AFJ Language 문서 참고 | — | [v11.md](versions/v11.md) |
| FreeLang v12 | `freelang-v12`, `v12-alpha`(빈 저장소) + AFJ 저장소 안 설계 문서 | 2026-05-12 (설계 문서) | 없음 | 설계 문서뿐(Hot Reload 등) | 코드 없음 | [v12.md](versions/v12.md) |
| FreeLang v2 | [freelang-v2](https://github.com/kimjindol2025/freelang-v2), [v2-freelang-ai](https://github.com/kimjindol2025/v2-freelang-ai), [freelang](https://github.com/kimjindol2025/freelang) 등 | 첫 커밋 2026-02-15 | TypeScript (40만 줄대) | 중괄호형. "자기 자신의 소스를 컴파일 및 린트할 수 있는 제로 외부 의존성 AI 기반 프로그래밍 언어" | **실행 확인**(타입 오류 300건이지만 예제 정상). 마지막 3/13 | [v2.md](versions/v2.md) |
| FreeLang v3 | [v3-freelang-ai](https://github.com/kimjindol2025/v3-freelang-ai)(빈 저장소) | 2026-06-19 (빈 저장소) | 확인 안 됨 | 문서에 "CSI(Claude Self-Interrogation)" 언급만 | 코드 없음 | [v3.md](versions/v3.md) |
| FreeLang v4 | [freelang-v4](https://github.com/kimjindol2025/freelang-v4), [freelang-langv4](https://github.com/kimjindol2025/freelang-langv4) 등 | 첫 커밋 2026-02-19 | TypeScript (본체 약 1만 4천 줄) | 중괄호형 정적 타입 + 바이트코드 가상머신. "완전한 프로그래밍 언어" | **테스트 213/213 통과**, 예제 1개 실패. 마지막 4/5 | [v4.md](versions/v4.md) |
| FreeLang v5 | [freelang-v5-ai](https://github.com/kimjindol2025/freelang-v5-ai) | 2026-03-03 | TypeScript (약 8천 줄) | 의도 → TypeScript·C·Python·Go·Rust 코드 생성기. "Human 10% + AI 90%" | 실행하면 '데모 모드'로 빈 함수만 생성. 테스트 파일 없음 | [v5.md](versions/v5.md) |
| FreeLang v6 | [freelang-v6](https://github.com/kimjindol2025/freelang-v6) | 2026-03-01 | TypeScript + C 코드 생성 | 중괄호형, 모듈·enum·제네릭, C로 빌드. "Practical Programming Language" | **실행 확인**, 테스트 4,082 통과/135 실패. README에 '보관' 표시 | [v6.md](versions/v6.md) |
| FreeLang v7 | 없음 (AI 기억 파일에 한 줄) | 확인 안 됨 | 확인 안 됨 | "AI Automation Platform … Issue → Code → Compile → Execute" 언급만 | 찾지 못함 | [v7.md](versions/v7.md) |
| FreeLang v8 | [freelang-v8-ml](https://github.com/kimjindol2025/freelang-v8-ml)(빈 저장소) | 2026-06-19 (빈 저장소) | 확인 안 됨 | 내용 없음 | 빈 저장소 | [v8.md](versions/v8.md) |
| FreeLang v9 | [freelang-v9](https://github.com/kimjindol2025/freelang-v9) | 첫 커밋 2026-04-03 | TypeScript (약 12만 줄) + .fl | 괄호 목록형 + `[FUNC]`·`[ROUTE]` 블록, AI 호출 내장. "AI를 위한, AI에 의한, AI가 쓰고 싶은 언어." | 설치는 되나 **실행 실패**(절대 경로 박힘). 테스트 345 통과/154 실패. 마지막 5/9 | [v9.md](versions/v9.md) |

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
