# Quick Advanced Workshop - 참가자용 따라하기

> Amazon Quick Desktop (amazonbi 계정) 핸즈온. 화면 보면서 순서대로 따라가면 됩니다.

## 준비 (시작 전 확인)

1. Quick Desktop 앱 실행 → 계정 선택 화면에서 **"다른 계정 추가"** → **"Quick 계정 이름"** 에 `amazonbi` 입력 → **다음** → 회사 계정으로 로그인
   (이미 amazonbi로 로그인해 뒀으면 계정 선택 화면에서 고르기만 하면 됩니다)

![계정 선택 화면](images/quick-login-account-select.png)

![amazonbi 로그인](images/quick-login-amazonbi.png)

2. 채팅 창 왼쪽 위 어시스턴트가 **"Quick"** 으로 선택돼 있는지 확인

![어시스턴트 선택](images/quick-assistant-select.png)

3. 로컬 파일 쓸 거면: **Settings → Capabilities → Connectors → Local files** 에 워크샵 자료 폴더 추가
4. 응답이 얕으면 채팅 모드를 **Smart** 로 전환 (Fast / Balanced / Smart 중, 기본이자 최고 품질이 Smart). 더 깊게 필요하면 **Thinking** 토글 켜기

---

## 이 워크샵에서 쓰는 데이터

실습용으로 미리 준비된 한국어 샘플 데이터입니다. 참가자 전원이 똑같은 결과를 내도록 통제된 자료이고, 로컬 폴더(OneDrive 마운트)에 들어 있습니다. 실제 본인 데이터가 아니니 마음 편히 써도 됩니다.

| 파일/폴더 | 내용 | 어디서 쓰나 |
|---|---|---|
| `./research-folder/` | "리워드 프로그램 도입" 관련 조사 자료 (시장·고객·비용 등) | STEP 2 (보고서·덱 생성) |
| `./call-transcripts/` | 영업 콜 녹취록 5개 (한국어). 대표 파일: `discovery-acme-corp.txt`(한빛테크), `discovery-globex.txt` | STEP 3 (리드 평가·후속 이메일) |
| `./customer-usage.csv` | 고객사별 API 사용량 데이터 (고객사·세그먼트·호출수 등) | STEP 4 (대시보드), STEP 6-2 (Apps) |

> 파일이 안 열리면: **Settings → Capabilities → Connectors → Local files** 에 위 폴더가 추가돼 있는지 확인하세요. 경로의 `./` 는 그 연결된 폴더 기준입니다.

---

## STEP 2. 첫 Skill 만들기 — branded-report

**① 채팅에 붙여넣고 전송:**

```
branded-report 라는 이름의 Skill을 만들어줘. 이 Skill은 전문적인 임원 보고서 느낌의 HTML 보고서를 생성해야 해. 아래 디자인 기준을 정확히 지켜줘.

[브랜드 색상]
- 진한 색 #232F3E, 강조색 #FF9900, 배경 흰색

[레이아웃]
1. 헤더 띠: 페이지 최상단에 전체 폭 진한 배경(#232F3E) 띠. 왼쪽에 제목(흰색 굵게), 오른쪽에 날짜(연한 회색). 띠 아래 4px 주황색(#FF9900) 라인.
2. 본문 칼럼: 가운데 정렬(최대 너비 약 840px), 좌우 여백 넉넉히.
3. 목차: 본문 맨 위에 연한 배경 + 왼쪽 4px 주황 보더 박스.
4. 섹션 제목: 아래에 연한 주황색 밑줄.
5. 강조 박스: 핵심 결론은 크림색 배경(#FFF8F0) + 왼쪽 4px 주황 보더 박스.
6. 표: 헤더 행 진한 배경(#232F3E) 흰 글씨, 본문 행 한 줄 걸러 연한 회색.
7. 깔끔한 시스템 폰트, 여백 넉넉히.
8. 하단 푸터: "Generated with Amazon Quick"

[본문 언어]
- 보고서 본문은 한국어로 작성

[저장 위치]
- 보고서는 ./output/ 폴더에 저장. 폴더 없으면 생성. 파일명은 report-YYYY-MM-DD.html 형식.

[자동 적용]
- "보고서"라는 단어가 언급되면 이 Skill이 자동 적용되도록.

재사용할 수 있게 Skill을 저장해줘.
```

② 권한 물어보면 → **허용**
③ ✅ 왼쪽 **Agents & skills 패널**에 `branded-report` 보이면 성공

**④ 바로 써보기:**

```
./research-folder/ 폴더의 조사 자료로 임원용 보고서를 만들어줘. 제목은 "리워드 프로그램 결정 — 임원 보고서".
```

**⑤ (선택) 발표 덱까지:**

```
./research-folder/ 폴더의 조사 자료로 "리워드 프로그램 결정" 임원 보고용 프레젠테이션 덱을 만들어줘. 계정 현황, 핵심 과제, 결정 사항, 다음 단계를 포함해줘. 만들기 전에 슬라이드 구성안을 먼저 보여주고 내 승인을 받아줘.
```

→ 구성안 나오면 승인 → .pptx 생성됨

---

## STEP 3. 두 번째 Skill — qualify-lead (직접)

**① skill 생성 (붙여넣고 전송):**

```
qualify-lead 라는 이름의 Skill을 만들어줘. 이 Skill은 영업 콜 녹취록을 읽고 BANT 프레임워크(예산 Budget, 결정권 Authority, 니즈 Need, 시점 Timeline)로 리드를 평가해야 해.

각 콜에 대해 다음을 한국어로 작성해줘:
- BANT 4개 항목별 평가와 확신 수준(상 / 중 / 하), 그리고 녹취록에서 인용한 근거
- 1~10점의 종합 리드 품질 점수
- 권장 다음 단계
- 리스크 요인이나 위험 신호

리드를 평가하거나 영업 콜을 검토해달라고 요청하면 이 Skill이 자동으로 적용되도록 해줘.

재사용할 수 있게 Skill을 저장해줘.
```

**② 테스트:**

```
./call-transcripts/discovery-acme-corp.txt 콜 녹취록의 리드를 평가해줘.
```

**③ (선택) 비교:**

```
./call-transcripts/discovery-globex.txt 콜의 리드도 평가하고, 한빛테크와 비교해줘. 어느 쪽이 더 유망한 기회야?
```

**④ (선택) 개선:**

```
qualify-lead Skill을 수정해서, 콜에 언급된 경쟁사와 잠재 고객이 그에 대해 한 말도 정리하도록 해줘.
```

**⑤ (선택) follow-up-email skill 생성:**

```
follow-up-email 이라는 이름의 Skill을 만들어줘. 영업 콜 녹취록을 바탕으로 그 고객에게 보낼 개인화된 후속 이메일 초안을 한국어로 작성해야 해.

이메일에는 다음을 포함해줘:
- 콜에서 논의된 핵심 내용 요약
- 고객이 표현한 니즈와 우려사항에 대한 응답
- 합의된 다음 단계
- 정중하고 전문적인 톤

리드 평가가 끝난 뒤 "후속 이메일 써줘"라고 하면 이 Skill이 자동 적용되도록 해줘. 재사용할 수 있게 저장해줘.
```

→ 써보기: `방금 평가한 한빛테크 콜을 바탕으로 후속 이메일 초안을 써줘.`

---

## STEP 4. 분석 결과 → 인터랙티브 HTML 대시보드 (insight-dashboard)

> STEP 2가 "정적 보고서"라면, 이건 마우스로 필터/클릭하는 **인터랙티브 대시보드**를 HTML 한 파일로 만듭니다. (브라우저로 바로 열림, 서버 불필요)

**① skill 생성 (붙여넣고 전송):**

```
insight-dashboard 라는 이름의 Skill을 만들어줘. 이 Skill은 데이터나 분석 결과를 받아서 인터랙티브한 HTML 대시보드를 단일 파일로 생성해야 해. 아래 기준을 정확히 지켜줘.

[기술 방식]
- 외부 라이브러리는 CDN으로만 불러오고(Chart.js 등), 결과는 단일 HTML 파일 하나로 완결되게 해줘. 브라우저로 더블클릭하면 바로 열려야 해. 별도 설치나 서버 실행이 필요 없어야 해.

[브랜드 색상]
- 진한 색 #232F3E, 강조색 #FF9900, 배경 흰색

[레이아웃]
1. 상단 헤더 띠: 전체 폭 진한 배경(#232F3E), 왼쪽에 대시보드 제목(흰색 굵게), 오른쪽에 생성 날짜. 띠 아래 4px 주황색(#FF9900) 라인.
2. KPI 카드 줄: 헤더 바로 아래에 핵심 지표 3~4개를 카드로. 카드마다 큰 숫자 + 라벨.
3. 차트 영역: 막대/도넛/라인 등 데이터에 맞는 차트 2~3개. 차트는 반응형(창 크기에 맞게).
4. 필터: 상단에 드롭다운이나 버튼으로 세그먼트/기간 등을 고르면 차트와 표가 실시간으로 갱신.
5. 상세 표: 하단에 정렬 가능한 표(헤더 클릭 시 정렬). 헤더 행 진한 배경(#232F3E) 흰 글씨, 본문 한 줄 걸러 연한 회색.
6. 깔끔한 시스템 폰트, 카드/차트에 옅은 그림자와 둥근 모서리, 여백 넉넉히.

[본문 언어]
- 라벨과 설명은 한국어로 작성

[저장 위치]
- ./output/ 폴더에 저장. 폴더 없으면 생성. 파일명은 dashboard-YYYY-MM-DD.html 형식.

[자동 적용]
- "대시보드"라는 단어가 언급되면 이 Skill이 자동 적용되도록.

재사용할 수 있게 Skill을 저장해줘.
```

② 권한 물어보면 → **허용**
③ ✅ **Agents & skills 패널**에 `insight-dashboard` 보이면 성공

**④ 바로 써보기:**

```
./customer-usage.csv 데이터로 인터랙티브 대시보드를 만들어줘. 고객사별 API 호출수, 세그먼트별 분포, 상위 고객사를 보여주고, 세그먼트로 필터할 수 있게 해줘.
```

→ 생성된 `./output/dashboard-YYYY-MM-DD.html` 을 더블클릭하면 브라우저에서 바로 열림

**⑤ (선택) 우리말로 계속 다듬기:**

```
방금 만든 대시보드에 "월별 추이" 라인 차트를 추가하고, 상위 5개 고객사만 강조해줘.
```

> STEP 6-2의 "Apps"와 차이: Apps는 Quick 안에서 쓰는 앱, 이건 **HTML 파일로 떨어져서 누구에게나 공유 가능**(이메일 첨부·SharePoint 업로드).

---

## STEP 5. Connection — 외부 도구 연결

1. **Settings → Capabilities → Connectors** 열기
2. 도구 선택 (**Outlook** 또는 **SharePoint**)
3. 회사 계정으로 OAuth 로그인
4. 동작 확인:

```
이번 주 내 캘린더 일정 요약해줘.
```

또는

```
[SharePoint 폴더명]에서 최근 문서 3개 찾아서 핵심만 정리해줘.
```

→ 권한 요청 뜨면 허용

> Asana 연결 시: **"Enterprise Asana MCP"** 선택 (기본 커넥터는 기능 4개뿐)

---

## STEP 6. Quick 차별 기능

**6-1. Scheduled Agent:**

```
매일 아침 8시에 내 이메일을 요약해서 알려주는 에이전트를 만들어줘.
```

→ 승인하면 생성 + 즉시 테스트 실행, 결과는 오른쪽 위 **Activity Feed** 에 (※ 이메일 Connection 필요)

변형:

```
회의 30분 전에, 내가 준비 안 한 미팅이 있으면 알려주는 에이전트를 만들어줘.
```

**6-2. Apps (대시보드):**

```
./customer-usage.csv 데이터로 고객 사용량 대시보드 앱을 만들어줘. 고객사별 API 호출수, 세그먼트별 분포, 상위 고객사를 한눈에 볼 수 있게 해줘.
```

**6-3. Knowledge Graph:**

1. **Settings(왼쪽 아래 톱니) → My Context → Knowledge Graph**
2. 노드/관계 확인
3. 채팅:

```
내 Knowledge Graph 보여줘
```

또는 `Quick이 [계정/사람]에 대해 뭘 알고 있어?`

**6-4. Browser (진짜 웹에서 찾아오기, 주로 진행자 시연):**

설정: **Settings → Customization → Browser** → 브라우저 선택(Chrome 등) → **"Use my browser"** 토글 ON → 안내대로 `chrome://inspect/#remote-debugging` 붙여넣고 **Enable remote debugging** → **Test Connection** → "Connected" 확인

![브라우저 커스터마이징](images/quick-browser-customization.png)

써보기:

```
쿠팡에서 "무선 키보드" 검색 결과 페이지를 열어서, 상위 5개 상품의 이름·가격·별점을 표로 정리해줘.
```

→ Quick이 실제로 브라우저를 열어 페이지를 읽어옴 (내 로그인/쿠키 그대로 사용)

> 검색(네이버 등)은 사이트가 막아서 잘 안 될 수 있어요. 쿠팡 검색이 막히면 상품 **URL을 직접** 주고 "이 상품 리뷰 요약해줘"로 하는 게 확실합니다.
> 셋업(remote debugging)이 낯설면 진행자 시연만 봐도 됩니다. 회사 보안정책으로 막힐 수도 있어요.

---

## STEP 7. 최종 체크

- [ ] `branded-report` 패널에 있음
- [ ] `qualify-lead` 직접 만듦
- [ ] `insight-dashboard` 로 HTML 대시보드 만듦
- [ ] Connection 1개 연결
- [ ] Scheduled Agent 만들어봄 / Apps·Knowledge Graph·Browser 봄

---

## 막히면 (트러블슈팅)

| 증상 | 대응 |
|---|---|
| skill이 패널에 안 보임 | 패널 새로고침 / 앱 재시작 |
| 로컬 파일을 못 찾음 | Settings → Connectors → Local files에 폴더 추가 |
| Space/Agent 생성 메뉴가 없음 | **정상** (Desktop은 사용만, 생성은 Web) |
| 응답이 너무 짧음/얕음 | **Smart 모드**로 전환 (필요시 Thinking 토글) |
| Connection 인증 실패 | 회사 계정으로 재인증 (OAuth 90일 만료) |
| 외부 도구 데이터가 안 옴 | Settings에서 연결 확인, 권한 허용 |
