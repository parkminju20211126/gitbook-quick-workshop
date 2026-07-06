# STEP 4. Connection — 외부 도구 연결

> 여기서 연결한 도구들이 다음 STEP의 재료가 됩니다. STEP 5-1의 "매일 아침 이메일 요약" 에이전트는 Outlook 연결이 있어야 돌아가고, qualify-lead로 정리한 리드 리포트나 branded-report 산출물도 SharePoint에 기록·공유되어야 실제 워크플로우가 완성됩니다.

Quick의 강점은 채팅으로 지시하면 여러 도구를 오가며 일을 처리한다는 점입니다. 그러려면 어떤 도구를 다룰 수 있는지 먼저 알려줘야 해요. 이 스텝에서는 워크샵에서 자주 쓰는 커넥터를 한 번에 연결합니다.

---

## ① 연결 화면 열기

**Settings → Capabilities → Connectors** 를 엽니다. 사용 가능한 커넥터 목록이 뜹니다.

---

## ② 커넥터 선택 & 연결

아래 표에서 **필요한 커넥터를 하나씩** 골라 연결합니다. 각 커넥터마다 회사 계정으로 OAuth 로그인 → 권한 허용을 거치면 됩니다.

<table><thead><tr><th width="200">커넥터</th><th>용도</th><th width="220">이 워크샵에서 연결되는 곳</th></tr></thead><tbody><tr><td><strong>Outlook</strong></td><td>캘린더·이메일 조회, 초안 발송</td><td>STEP 5-1 Scheduled Agent (이메일 요약)</td></tr><tr><td><strong>SharePoint</strong></td><td>회사 문서 검색·요약, 산출물 업로드</td><td>보고서·기획 자료 컨텍스트 소스 / branded-report·리드 리포트 기록·공유</td></tr><tr><td><strong>Teams</strong></td><td>채널 메시지 검색, 메시지 발송</td><td>회의 요약을 채널로 공유</td></tr><tr><td><strong>AWS Documentation</strong></td><td>AWS 서비스 공식 문서 검색</td><td>서비스·파라미터 확인, 아키텍처 자문</td></tr><tr><td><strong>AWS Central MCP</strong></td><td>내 AWS 계정/리소스 조회</td><td>비용·리소스 상태 점검</td></tr><tr><td><strong>Salesforce</strong> (선택)</td><td>리드·계정·오퍼튜니티 관리</td><td>STEP 2 qualify-lead 결과를 SF에 기록</td></tr><tr><td><strong>Asana</strong> (선택)</td><td>프로젝트·태스크 관리</td><td>후속 액션 자동 등록</td></tr></tbody></table>

> **Asana 연결 시:** 반드시 **"Enterprise Asana MCP"** 를 선택하세요. 기본 커넥터는 기능이 4개뿐입니다.

---

## ③ 동작 확인 프롬프트

연결한 커넥터별로 한 번씩 돌려보면서 잘 붙었는지 확인합니다. 권한 팝업이 뜨면 **허용**.

**Outlook**

```
이번 주 내 캘린더 일정 요약해줘. 준비가 필요한 미팅은 별도로 표시해줘.
```

**SharePoint**

```
[SharePoint 사이트/폴더명]에서 최근 문서 3개 찾아서 핵심만 정리해줘.
```

**Teams**

```
내가 속한 채널 중에서 이번 주 활발했던 채널 3개 찾아서, 각 채널의 주요 논의 요약해줘.
```

**AWS Documentation**

```
Amazon Bedrock의 최신 지원 리전과 각 리전별로 사용 가능한 파운데이션 모델을 표로 정리해줘.
```

**AWS Central MCP**

```
내 계정에서 이번 달 비용이 가장 많이 나온 서비스 상위 5개를 알려줘.
```

**Salesforce**

```
내가 담당하는 오퍼튜니티 중 이번 분기 클로징 예정인 것들 리스트로 보여줘.
```

---

## ④ (선택) 조합해보기

여러 커넥터를 한 번에 쓰면 진짜 힘이 나옵니다.

```
이번 주 내 캘린더에서 고객 미팅 찾아서, 각 미팅 참석자에 대해 SharePoint에서 이전에 논의한 자료가 있는지 검색하고, 준비 브리핑을 한 페이지로 정리해줘.
```

```
./call-transcripts/discovery-acme-corp.txt 콜을 qualify-lead Skill로 평가한 결과를, [SharePoint 사이트]의 "리드 리포트" 폴더에 파일로 기록해줘. 파일명은 "리드평가-한빛테크-YYYY-MM-DD.md" 형식으로.
```

> **Tip:** 연결이 많아질수록 프롬프트에 "어느 도구를 써야 한다"라고 지정하지 않아도 Quick이 알아서 필요한 커넥터를 골라서 씁니다.

---

## 문제가 생기면

- **인증 실패**: 회사 계정으로 다시 로그인. OAuth 토큰은 90일마다 만료됩니다.
- **커넥터가 목록에 없음**: 조직 관리자에게 활성화 요청 필요.
- **데이터가 안 옴**: Settings에서 해당 커넥터 권한 범위를 다시 확인하세요.

---

> **다음:** [STEP 5. Quick 차별 기능 →](step-5-quick-features.md)
