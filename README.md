# Amazon Quick 실전 워크샵

> 채팅으로 만드는 나만의 업무 자동화 도구

이 워크샵은 Amazon Quick의 핵심 기능(Skills, Connection, Scheduled Agent, Apps, Knowledge Graph, Browser)을 실습으로 익히는 과정입니다. 코드를 직접 작성하지 않고 채팅으로 지시하는 방식으로, 재사용 가능한 Skill을 만들고 실제 업무에 바로 적용해봅니다.

---

# Amazon Quick Hands-on Workshop (English)

> Build your own work automation tools through chat.

This workshop is a hands-on program for learning Amazon Quick's core features (Skills, Connection, Scheduled Agent, Apps, Knowledge Graph, Browser). Instead of writing code yourself, you'll give instructions through chat, build reusable Skills, and apply them directly to real work.

---

## 준비 (시작 전 확인)

**1. Quick Desktop 로그인**

Quick Desktop 앱을 실행하면 로그인 화면이 뜹니다. **"Internal login"** 버튼을 눌러 회사 계정으로 로그인해 주세요. (외부 계정으로 진행할 경우 아래 **"Continue with"** 옵션 중 하나를 골라도 됩니다.)

<figure><img src="images/quick-login-signin.png" alt="Amazon Quick 로그인 화면"><figcaption>Amazon Quick 로그인 화면</figcaption></figure>

로그인이 완료되면 아래 화면이 뜹니다. 창을 닫고 Quick Desktop 앱으로 돌아오시면 됩니다.

<figure><img src="images/quick-login-success.png" alt="로그인 완료 화면"><figcaption>로그인이 완료된 상태 — 창을 닫고 Quick으로 돌아오면 됩니다</figcaption></figure>

**2. 어시스턴트 확인**

채팅 창 왼쪽 위 어시스턴트가 **"Quick"** 으로 선택돼 있는지 확인합니다.

<figure><img src="images/quick-assistant-select.png" alt="어시스턴트 선택"><figcaption>어시스턴트 선택</figcaption></figure>

**3. 채팅 모드**

채팅 모드는 Fast / Balanced / Smart 세 가지 중 **Smart** 로 두고 시작합니다 (기본값이자 가장 품질이 좋음). 좀 더 깊게 생각하게 하려면 **Thinking** 토글도 함께 켜주세요.

---

## Preparation (Before you start) — English

**1. Sign in to Quick Desktop**

Launch the Quick Desktop app and the sign-in screen appears. Click **"Internal login"** to sign in with your corporate account. (If you're using an external account, pick one of the **"Continue with"** options below.)

<figure><img src="images/quick-login-signin.png" alt="Amazon Quick sign-in screen"><figcaption>Amazon Quick sign-in screen</figcaption></figure>

Once signed in, the screen below appears. Close the window and return to the Quick Desktop app.

<figure><img src="images/quick-login-success.png" alt="Sign-in complete screen"><figcaption>Sign-in complete — close the window and return to Quick</figcaption></figure>

**2. Check the assistant**

Confirm that the assistant at the top-left of the chat window is set to **"Quick"**.

<figure><img src="images/quick-assistant-select.png" alt="Assistant selection"><figcaption>Assistant selection</figcaption></figure>

**3. Chat mode**

Among the three chat modes — Fast / Balanced / Smart — start with **Smart** (the default and highest quality). To make it think more deeply, also turn on the **Thinking** toggle.

---

## 워크샵에서 쓰는 데이터

실습용으로 미리 준비된 Sales 샘플 데이터입니다. 
> **📥 다운로드:** [quick-workshop-data.zip](https://github.com/parkminju20211126/gitbook-quick-workshop/raw/master/quick-workshop-data.zip)
>
> zip을 받아서 원하는 위치에 압축을 풀어주세요. 그런 다음 채팅 입력창 왼쪽 아래의 **`+` 버튼 → Quick knowledge → Choose a folder** 를 눌러 방금 압축을 푼 폴더를 지정하면 됩니다. 이후 실습에 나오는 `./` 경로는 전부 이 폴더 기준이에요.

<figure><img src="images/quick-choose-folder.png" alt="Choose a folder"><figcaption>+ 버튼 → Quick knowledge → Choose a folder</figcaption></figure>

<table><thead><tr><th width="200">파일/폴더</th><th>내용</th><th width="200">어디서 쓰나</th></tr></thead><tbody><tr><td><code>./research-folder/</code></td><td>"리워드 프로그램 도입" 관련 조사 자료 (시장·고객·비용 등)</td><td>STEP 1 (보고서·덱 생성)</td></tr><tr><td><code>./call-transcripts/</code></td><td>영업 콜 녹취록 5개 (한국어). 대표 파일: <code>discovery-acme-corp.txt</code>(한빛테크), <code>discovery-globex.txt</code></td><td>STEP 2 (리드 평가·후속 이메일)</td></tr><tr><td><code>./customer-usage.csv</code></td><td>고객사별 API 사용량 데이터 (고객사·세그먼트·호출수 등)</td><td>STEP 3 (대시보드), STEP 5-2 (Apps)</td></tr></tbody></table>

---

## Workshop data (English)

Sales sample data prepared for the hands-on labs.
> **📥 Download:** [quick-workshop-data.zip](https://github.com/parkminju20211126/gitbook-quick-workshop/raw/master/quick-workshop-data.zip)
>
> Grab the zip and extract it wherever you like. Then click the **`+` button at the bottom-left of the chat input → Quick knowledge → Choose a folder** and point it at the folder you just extracted. From here on, every `./` path in the labs is relative to that folder.

<figure><img src="images/quick-choose-folder.png" alt="Choose a folder"><figcaption>+ button → Quick knowledge → Choose a folder</figcaption></figure>

<table><thead><tr><th width="200">File / Folder</th><th>Contents</th><th width="200">Used in</th></tr></thead><tbody><tr><td><code>./research-folder/</code></td><td>Research materials on "launching a rewards program" (market, customers, cost, etc.)</td><td>STEP 1 (report / deck generation)</td></tr><tr><td><code>./call-transcripts/</code></td><td>Five sales call transcripts (Korean). Featured files: <code>discovery-acme-corp.txt</code> (Hanbit Tech), <code>discovery-globex.txt</code></td><td>STEP 2 (lead qualification / follow-up email)</td></tr><tr><td><code>./customer-usage.csv</code></td><td>API usage data by customer (customer, segment, call count, etc.)</td><td>STEP 3 (dashboard), STEP 5-2 (Apps)</td></tr></tbody></table>

---

## 실습 순서

1. [STEP 1. 첫 Skill 만들기 — branded-report](step-1-branded-report.md)
2. [STEP 2. 두 번째 Skill — qualify-lead (직접)](step-2-qualify-lead.md)
3. [STEP 3. 인터랙티브 HTML 대시보드 — insight-dashboard](step-3-insight-dashboard.md)
4. [STEP 4. Connection — 외부 도구 연결](step-4-connection.md)
5. [STEP 5. Quick 차별 기능](step-5-quick-features.md)
6. [STEP 6. 최종 체크](step-6-checklist.md)
7. [트러블슈팅](troubleshooting.md)

---

## Lab order (English)

1. [STEP 1. Build your first Skill — branded-report](step-1-branded-report.md)
2. [STEP 2. Second Skill — qualify-lead (hands-on)](step-2-qualify-lead.md)
3. [STEP 3. Interactive HTML dashboard — insight-dashboard](step-3-insight-dashboard.md)
4. [STEP 4. Connection — connect external tools](step-4-connection.md)
5. [STEP 5. Quick's distinctive features](step-5-quick-features.md)
6. [STEP 6. Final check](step-6-checklist.md)
7. [Troubleshooting](troubleshooting.md)
