# GitHub Copilot CLI 시작 가이드 (비개발자용)

> 마케팅, 세일즈, HR, 기획 등 개발자가 아닌 분들도 **딱 3단계**만 하면 시작할 수 있습니다.
> 명령어는 전부 **그대로 복사해서 붙여넣기**만 하면 동작합니다.

---

## 목차

1. [이게 뭔가요? — ChatGPT랑 뭐가 다르죠?](#1-이게-뭔가요--chatgpt랑-뭐가-다르죠)
2. [딱 3단계로 시작](#2-딱-3단계로-시작)
3. [3가지 모드 — Shift + Tab 으로 전환](#3-3가지-모드--shift--tab-으로-전환)
4. [꼭 지켜야 할 안전 수칙 5가지](#4-꼭-지켜야-할-안전-수칙-5가지)
5. [이제 직군별 예시로 실습](#5-이제-직군별-예시로-실습)
6. [설치/실행이 안 될 때](#6-설치실행이-안-될-때)
7. [자주 묻는 질문](#7-자주-묻는-질문)
8. [더 알아보고 싶다면](#8-더-알아보고-싶다면)

---

## 1. 이게 뭔가요? — ChatGPT랑 뭐가 다르죠?

한 마디로: **"내 컴퓨터에서 실제로 손발이 되어 움직이는 ChatGPT"** 입니다.

| | ChatGPT 웹 (chatgpt.com) | GitHub Copilot CLI |
|---|---|---|
| **어디서 쓰나** | 브라우저 | 내 컴퓨터의 터미널(검은 화면) |
| **내 파일 다루기** | 매번 하나씩 업로드 | 폴더에 있는 파일 **바로 읽음** |
| **결과** | "이렇게 하세요" 조언만 | **실제로 명령 실행 → 결과 파일 생성** |
| **GitHub·이슈·PR** | 링크로만 가능 | **자연어로 바로 조작** |

### 같은 요청, 어떻게 다른가

*"이 폴더 CSV 3개를 하나로 합쳐줘"* 라고 시켰을 때:

- **ChatGPT 웹**: "다음 Python 코드를 복사해서 실행하세요..." (내가 복붙해서 직접 실행해야 함)
- **Copilot CLI**: 폴더 스캔 → CSV 읽음 → 합치는 스크립트 만듦 → 실행 → `merged.csv` 생성 완료

즉, ChatGPT 한테 배워서 **내가 손으로 하던 걸** Copilot CLI 는 **대신 해줍니다.**

---

## 2. 딱 3단계로 시작

### 1단계 · 설치 (5분)

시작 메뉴에서 **Windows Terminal** 또는 **PowerShell** 을 여세요.

<img width="748" height="675" alt="image" src="https://github.com/user-attachments/assets/02b5f71f-ecfa-49f4-b95c-e6d252bf7bd9" />

> **PowerShell 7 이상 필수.** 확인: `$PSVersionTable.PSVersion` 입력해서 5.x 나오면 [PowerShell 7 설치](https://learn.microsoft.com/powershell/scripting/install/installing-powershell) 먼저.

아래 한 줄 붙여넣고 Enter:

```powershell
winget install GitHub.Copilot
```

<img width="717" height="197" alt="image" src="https://github.com/user-attachments/assets/d6904dbc-d4b1-4d2a-8508-f913beae3dc1" />

설치 끝나면 **터미널을 완전히 닫았다 다시 열고** 확인:

```powershell
copilot --version
```

버전 번호가 나오면 끝.

### 2단계 · 실행하고 GitHub 로그인 (2분, 최초 1회만)

터미널에 이거 하나만:

```bash
copilot
```
<img width="1465" height="741" alt="image" src="https://github.com/user-attachments/assets/67cca124-7590-4271-8ece-f7d5cbfd7605" />

1) 프롬프트가 뜨면 `/login` 입력


<img width="531" height="162" alt="image" src="https://github.com/user-attachments/assets/ebb2afc3-3ecf-41bd-b7a0-50a3f2df35b6" />

2) github.com > Sign with your browser (recommend) 를 Enter로 클릭

<img width="1460" height="228" alt="image" src="https://github.com/user-attachments/assets/2d5b8a1f-b5bc-4f37-b768-34c873f7f2f6" />

3) 화면에 나온 링크로 브라우저 접속  
<img width="577" height="747" alt="image" src="https://github.com/user-attachments/assets/2ef88796-9745-4f16-adad-355316d87a29" />

4) 코드 붙여넣기 → copilot을 부여받은 github 계정으로 로그인 후, Autorize gitub 해주세요.

**한 번만 하면 됩니다.** 다음부터는 자동 로그인.

### 3단계 · 한국어로 말하기

프롬프트에 원하는 걸 한국어로 그냥 말하세요:

<img width="1435" height="736" alt="image" src="https://github.com/user-attachments/assets/a5a08c6d-2e20-4291-85db-200ed0cbea71" />


```
> 이 폴더에 있는 csv 파일 목록 보여줘
> 이 pdf 3개 요약해서 한 페이지 문서로 만들어줘
> 파일 이름을 날짜순으로 정리해줘
```

명령을 실행할 때는 승인 창이 뜹니다:

```
Copilot would like to run: ls *.csv
1. Yes                              ← 이번 한 번만 허용
2. Yes, and approve for session     ← 이번 세션 동안 (권장)
3. No                               ← 거부하고 다른 방법 요청
```

**이게 전부입니다.** 보낼 땐 `Enter` 끝낼 땐 `/exit` 또는 `Ctrl + C` 두 번.

<img width="620" height="305" alt="image" src="https://github.com/user-attachments/assets/27d11edf-47f3-433f-b2fa-7333194c22cd" />

**Model을 바꿔보세요.** /model 입력하고, claude haiku 4.5 모델로 바꾼 후, 사용해보세요. 속도는 빠른데 성능이 좋습니다.

---

## 3. 3가지 모드 — Shift + Tab 으로 전환

대화 중에 **`Shift + Tab`** 을 누르면 모드가 순환하며 바뀝니다. 지금 어떤 모드인지는 화면 하단에 표시됩니다.

| 모드 | 뭐가 다른가 | 언제 쓰나 |
|---|---|---|
| **Ask/Execute** (기본) | 명령 실행 전 매번 승인 물어봄 | 처음 배울 때, 간단한 작업 |
| **Plan** | 먼저 계획을 세워서 보여주고 확인받은 후 실행 | 복잡하거나 여러 파일 건드리는 작업 |
| **Autopilot** | 승인 없이 알아서 다 실행 | 익숙해진 후, 신뢰할 수 있는 반복 작업 |

`Ask/Execute → Plan → Autopilot → Ask/Execute` 순서로 순환.

> **처음엔 무조건 Ask/Execute 로만 쓰세요.** Autopilot 은 잘못하면 파일이 지워질 수 있습니다.

---

## 4. 꼭 지켜야 할 안전 수칙 5가지

**하나만 어겨도 사고 납니다.** 진지하게 읽어주세요.

### 1) 홈 폴더·바탕화면 최상위에서는 실행 금지

Copilot 은 실행한 폴더의 **모든 파일을 읽을 수 있습니다.** 반드시 **작업 전용 폴더** 를 만들고 그 안에서만 실행하세요.

- 좋은 예: `바탕화면\copilot-작업\마케팅-2026-q3\`
- 나쁜 예: `바탕화면\` 최상위 · `내 문서\` 최상위 · `C:\Users\내이름\`

**폴더 만드는 법 (Windows)**: 바탕화면 우클릭 → 새로 만들기 → 폴더 → 이름 입력. 그 폴더 안에서 다시 우클릭 → **"터미널에서 열기"** 클릭.

### 2) "Trusted directory" 확인 창을 대충 넘기지 마세요

첫 실행 때 "이 폴더를 신뢰하시겠습니까?" 라고 물어봅니다.
- 내가 만든 작업 폴더면 → **Yes**
- 모르는 폴더면 → **No**

### 3) `--allow-all-tools` 옵션은 절대 쓰지 마세요

이 옵션을 켜면 **파일 삭제, git 강제 push, 시스템 명령** 을 승인 없이 다 실행합니다. 실수로 소중한 파일이 지워질 수 있습니다.

**초보자 추천 실행 옵션** — 파일 삭제와 git push 를 원천 차단:
```bash
copilot --deny-tool='shell(rm)' --deny-tool='shell(git push)'
```

### 4) 승인 창은 반드시 읽고 판단하세요

```
Copilot would like to run: rm -rf ./output
1. Yes    2. Yes, and approve for session    3. No
```

모르는 명령이면 **3번 (No)** 누르고 "이 명령 뭐 하는 건지 설명해줘" 라고 물어보세요.

### 5) 회사 기밀 파일 폴더에서는 회사 정책 먼저 확인

Copilot 은 파일 내용 일부를 **GitHub 서버로 전송** 합니다. 개인정보·계약서·비공개 재무 데이터가 있는 폴더에서 실행할 땐 회사 정책 확인이 우선. 필요 시 `/sandbox enable` 로 네트워크 노출 제한.

---

## 5. 이제 직군별 예시로 실습

시작 준비 완료. **본인 직군 폴더** 로 들어가서 Ch 1 → Ch 2 → Ch 3 순서로 따라 해보세요.

| 직군 | 폴더 | 대표 사용 사례 |
|---|---|---|
| **Marketing** | [`marketing/`](./marketing/) | 광고 CSV 통합, 이미지 리사이즈, 경쟁사 모니터링, GA4 임원 보고서 |
| **Sales** | [`sales/`](./sales/) | CRM 리드 정규화, 견적서 자동 생성, 계약서 조항 추출, 콜드 아웃리치 |
| **HR / Ops** | [`hr-ops/`](./hr-ops/) | 이력서 필드 추출, 폴더 리네이밍, 온보딩 체크리스트 |
| **PM / 기획** | [`pm-planning/`](./pm-planning/) | 이슈 → 리포트, 회의록 → 액션 아이템, 릴리스 노트 초안 |

**각 폴더 3챕터 구성**: Ch 1 사용법 (10분, 초급 ★☆☆) → Ch 2 활용 (30분, 중급 ★★☆) → Ch 3 현업 활용 (60분+, 고급 ★★★).

> **팁**: 다른 직군 폴더도 훑어보세요. 이름만 다를 뿐 재활용 가능한 프롬프트가 많습니다 (예: Marketing "CSV 통합" → 재무팀 월결산, HR "PDF 필드 추출" → 법무팀 계약서 검토).

---

## 6. 설치/실행이 안 될 때

| 증상 | 해결 |
|---|---|
| `command not found: copilot` | 터미널 완전히 닫았다 다시 열기 |
| PowerShell 5.x 로 실행됨 | [PowerShell 7 설치](https://learn.microsoft.com/powershell/scripting/install/installing-powershell) 후 그걸로 실행 |
| 회사 계정인데 로그인 안 됨 | GitHub 관리자에게 "Copilot CLI 정책 허용" 요청 |
| `npm : 스크립트 실행이 사용 안 함...` | 관리자 권한 PowerShell 에서 `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` |
| 매번 승인 요청이 반복됨 | 승인 창에서 옵션 **2** (approve for session) 선택 |
| 요금이 걱정됨 | `/model` 로 저비용 모델 선택 · `/context` 로 사용량 확인 |
| 답변이 지나치게 짧음 | 폴더 안에 관련 파일이 있는지 확인 후 재요청 |

---

## 7. 자주 묻는 질문

**Q. 회사 비밀 문서를 다뤄도 되나요?**
회사 정책을 먼저 확인하세요. Copilot 은 파일 내용 일부를 서버로 전송합니다. 필요 시 `/sandbox enable` 로 네트워크 노출 제한.

**Q. 요금이 얼마나 나오나요?**
Copilot 구독료에 포함. 요청마다 "프리미엄 요청" 크레딧 소비. `/context` 로 사용량 확인. 자세한 요금은 [Copilot 요금 안내](https://docs.github.com/copilot/managing-copilot/monitoring-usage-and-entitlements/about-premium-requests) 참고.

**Q. 인터넷 없이도 되나요?**
안 됩니다. AI 서버와 통신해서 사용합니다.

**Q. 결과가 마음에 안 들면?**
그 자리에서 "이 부분은 이렇게 바꿔줘" 라고 이어서 대화하세요. 처음부터 완벽한 프롬프트를 쓰려 하지 말고 **대화로 다듬어 가세요.**

**Q. 팀에 프롬프트를 공유하려면?**
`.md` 파일로 저장해서 팀 공유 폴더/Notion 에 올리기. `.github/copilot-instructions.md` 파일을 프로젝트 폴더에 두면 팀 전체가 같은 컨텍스트로 시작.

**Q. 업데이트하려면?**
`copilot update` 또는 `winget upgrade GitHub.Copilot`.

**Q. 다이어그램/표가 이상하게 보여요.**
이 문서는 GitHub 웹에서 열 때 예쁘게 렌더링됩니다. 로컬 텍스트 에디터에서는 코드로 보일 수 있어요.

---

## 8. 더 알아보고 싶다면

- [Copilot CLI 공식 소개](https://docs.github.com/en/copilot/concepts/agents/about-copilot-cli)
- [설치 가이드](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli)
- [명령어 레퍼런스](https://docs.github.com/en/copilot/reference/copilot-cli-reference/cli-command-reference)
- [Getting Started 튜토리얼](https://docs.github.com/en/copilot/how-tos/copilot-cli/cli-getting-started)
- [GitHub 공식 저장소 / 릴리스 노트](https://github.com/github/copilot-cli)
- [Copilot 요금제](https://github.com/features/copilot/plans)

### 기여하기

실제로 쓰고 있는 프롬프트, 실수해서 배운 팁, 특정 툴(Salesforce, HubSpot, GA4 등) 연동 예시를 **Issue** 또는 **Pull Request** 로 공유해 주세요. 팀 전체 자산으로 쌓아 갑시다.

---

**Happy Copiloting.**

*마지막 업데이트: 2026-07-28*
