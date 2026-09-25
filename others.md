# 번호가 없는 FreeLang 이름 저장소

본 저장소 fg.dclub.kr(계정 `kim`)의 저장소는 800개이고 그중 792개가 비공개입니다(공개 8개는 FreeLang과 무관한 이름). 이름에 `freelang`이 들어간 것은 **270개**입니다(2026-09-25 조회). GitHub 백업에는 267개가 있습니다. 모든 저장소의 fg.dclub.kr "만든 날"은 2026-08-21 무렵(745개)으로 몰려 있어 서버 이전일로 보입니다.

## 본 저장소와 백업의 차이 (FreeLang 관련 이름)

- **본 저장소에만 있음(17개)**: freelang-platform, freelang-load-balancer, freelang-owner-identity, freelang-owner-authority, freelang-key-custody, freelang-linux-keyring-bridge, freelang-web-gateway, freelang-json, freelang-v11-fx2-aarch64-verify, freelang-platform-structure, freelang-proof-app, freelang-script-ai-benchmark-v27, freelang-aios-core, freelang-v11-wl2-benchmark-evidence, freelang-v11-fx-p1-8-delimiter-repair, freelang-comm-mediator-round1, freelang-history.
- **GitHub 백업에만 있음(14개)**: [freelang](https://github.com/kimjindol2025/freelang)(FreeLang v1 명세서가 든 저장소), [freelang-langv4](https://github.com/kimjindol2025/freelang-langv4)(본 저장소 `freelang-v4`의 4/5 무렵 사본으로 보임), freelang-v11-fx2-arm-verify, freelang-light-clean, -freelang-light-v2, freelang-core, freelang-independent, freelang-secret-link, freelang-sovereign-naming, freelang-fx2-homepage, freelang-blog-posts, freelang-korean-, v2-freelang-ai-release, v2-freelang-ai-http.
- **GitHub에서는 빈 저장소인데 본 저장소에는 내용이 있는 것(주요)**: v3-freelang-ai(FreeLang v3), freelang-v8-ml(FreeLang v8), freelang-v10(FreeLang v10), freelang-v12·v12-alpha(FreeLang v12), freelang-v9-lang·freelang-v9-registry, FreeLang_v2_1, freelang-evolution(커밋 915개), freelang-native(커밋 1,479개), freelang-ledger-v1(커밋 28개) 등. GitHub에 6/19 무렵 이름만 만들어진 빈 저장소 다수가 본 저장소에서는 내용이 있습니다.

## 묶음

| 묶음 | 대표 저장소 (본 저장소 링크) | 메모 |
|---|---|---|
| K-FreeLang (한국어 문법) | [freelang-korean](https://fg.dclub.kr/kim/freelang-korean) | 본 저장소 기본 가지는 커밋 1개("K-FreeLang 독립 프로젝트 공식 시작", 2026-03-26)이고 가지 6개(develop, feature/korean-syntax 등). GitHub 백업 기본 가지 README: "K-FreeLang v1.0 — 한국 개발자를 위한 완전한 독립 프로그래밍 언어", `변수 이름 = "김철수"`, `함수 인사하기(이름: 문자열) { 출력(...) }` 같은 한글 문법 |
| 번호 없는 이름의 큰 기록 | [freelang-evolution](https://fg.dclub.kr/kim/freelang-evolution), [freelang-native](https://fg.dclub.kr/kim/freelang-native) | evolution은 첫 커밋이 FreeLang v2와 같음(915개, 4/5까지). native는 첫 커밋이 FreeLang v9·AFJ와 같음(1,479개, 5/25까지). 열어 보지 않음 |
| 번호 없는 이름의 언어 실험 | freelang-bootstrap, freelang-final, freelang-light, freelang-c(-final), freelang-to-c, freelang-independent-full | 2~3월 TypeScript·C 실험 |
| 러스트·Go 실행기·OS 실험 | freelang-runtime, freelang-os-kernel, freelang-vm, [freelang-compiler](https://fg.dclub.kr/kim/freelang-compiler)(본 저장소 언어 표시 Go, 약 30MB. 이전 조사 메모는 Rust), [freelang-gpt](https://fg.dclub.kr/kim/freelang-gpt)(약 1.9GB, Go) | 열어 보지 않음. freelang-gpt는 FreeLang v8 README "출처" 표에 "transformer 참조"로 나옴 |
| 표준 라이브러리 이식 | freelang-stdlib-axios, -lodash … | 34개, 수 KB짜리 뼈대 |
| "주권"·네이티브 웹 부품 | freelang-sovereign-*, freelang-native-web-forge, -rate-shield | 3월 미러 후 변경 없음. native-* 일부는 v2 부품 저장소와 크기(약 7.2MB)가 같음 |
| AFJ 생태계 부품·도구 | [freelang-front](https://fg.dclub.kr/kim/freelang-front), [freelang-script](https://fg.dclub.kr/kim/freelang-script), [freelang-aios-core](https://fg.dclub.kr/kim/freelang-aios-core), [freelang-decision-model](https://fg.dclub.kr/kim/freelang-decision-model), freelang-project-autopilot, AFL-Core-2, afl-db, 신원·키 보관·부하분산기 저장소들 | AFJ Language와 함께 쓰는 현재 프로젝트. 8~9월 활동 |
| fl-*/fx-* 작은 서비스 | fl-conformance, fl-press, fx-files … | 6~8월 |
| 기타 | freelang-ledger-v1(장부 앱, 3/24~4/1, TypeScript) | 이름에 v1이 있지만 FreeLang v1 언어와 관계없는 앱 |

- 이름에 숫자가 붙었지만 언어 이름이 아닌 것: `freelang-frontend-v9`, `handwash-pos-v9`, `v9-tunnel`, `fl-blog-v11`, `freelang-ledger-v1`, `fsm-saas-v10`, `v13-intent-probe` 등.
- 다른 이름의 자작 언어: CLAUDELang(freelang-v6-ai-sovereign 안), mindlang, zlang, Proof_ai, pyfree, gofree — FreeLang 이름이 아니거나 이름만 빌린 경우.
