# STEP 4. Connection — 외부 도구 연결

> 여기서 연결한 도구들이 다음 STEP의 재료가 됩니다. STEP 5-1의 "매일 아침 이메일 요약" 에이전트는 Outlook 연결이 있어야 돌아가고, qualify-lead로 정리한 리드 리포트나 branded-report 산출물도 SharePoint에 기록·공유되어야 실제 워크플로우가 완성됩니다.

연결한 소스가 많을수록 Quick이 내 업무 맥락을 더 정확히 이해합니다. 커뮤니케이션 채널부터 붙이는 게 순서예요.

---

## ① 연결 화면 열기

**Settings → Capabilities → Connections** 를 엽니다. 사용 가능한 커넥터 목록이 뜹니다.

---

## ② 소스 연결하기

<table><thead><tr><th width="180">소스</th><th>Quick이 학습하는 것</th><th width="110">우선순위</th></tr></thead><tbody><tr><td><strong>Outlook / Gmail</strong></td><td>이메일 컨텍스트, 연락처, 후속 스레드</td><td>Must</td></tr><tr><td><strong>Calendar</strong></td><td>예정된 미팅, 참석자, 준비 사항</td><td>Must</td></tr><tr><td><strong>Slack</strong></td><td>팀 대화, 프로젝트 컨텍스트, 사람 간 관계</td><td>High</td></tr><tr><td><strong>Salesforce / AWSentral</strong></td><td>계정·오퍼튜니티·딜 단계·고객 데이터</td><td>High</td></tr><tr><td><strong>Zoom</strong></td><td>미팅 녹화·트랜스크립트·대화 맥락</td><td>High</td></tr><tr><td><strong>AWS Documentation MCP</strong></td><td>Quick 대화에서 AWS 공식 문서 직접 검색</td><td>Recommended</td></tr><tr><td><strong>Local Folders</strong></td><td>내 컴퓨터의 문서·프레젠테이션·노트</td><td>Recommended</td></tr></tbody></table>

**연결 순서 (권장):**

1. **Outlook (또는 Gmail)** 연결 → 접근 권한 승인
2. **Calendar** 연결
3. 가능하면 **Slack** 연결
4. **로컬 폴더** 최소 1개 추가: **Settings → My Computer → Local Folders → Add**
5. 나머지 High / Recommended 커넥터를 시간이 되는 만큼 이어서 연결

각 커넥터마다 회사 계정으로 OAuth 로그인 → 권한 허용을 거치면 됩니다.

---

## ③ 동작 확인 프롬프트

연결한 커넥터별로 한 번씩 돌려보면서 잘 붙었는지 확인합니다. 권한 팝업이 뜨면 **허용**.

**Outlook / Calendar**

```
이번 주 내 캘린더 일정 요약해줘. 준비가 필요한 미팅은 별도로 표시하고, 각 미팅과 관련된 최근 이메일 스레드도 함께 정리해줘.
```

**Slack**

```
내가 속한 채널 중에서 이번 주 활발했던 채널 3개 찾아서, 각 채널의 주요 논의를 요약해줘.
```

**Salesforce / AWSentral**

```
내가 담당하는 오퍼튜니티 중 이번 분기 클로징 예정인 것들을 딜 단계별로 정리해줘.
```

**Zoom**

```
지난주 내 Zoom 미팅 트랜스크립트에서 반복적으로 나온 이슈나 후속 액션을 뽑아줘.
```

**AWS Documentation MCP**

```
Amazon Bedrock의 최신 지원 리전과 각 리전별로 사용 가능한 파운데이션 모델을 표로 정리해줘.
```

**Local Folders**

```
방금 추가한 폴더에서 최근 문서 3개를 찾아 각각 한 문단으로 요약해줘.
```

---

## ④ (선택) 조합해보기

여러 소스를 한 번에 쓰면 진짜 힘이 나옵니다.

```
이번 주 내 캘린더에서 고객 미팅 찾아서, 각 미팅 참석자에 대해 최근 이메일·Slack 대화·Salesforce 계정 노트에서 맥락을 모아 준비 브리핑을 한 페이지로 정리해줘.
```

```
./call-transcripts/discovery-acme-corp.txt 콜을 qualify-lead Skill로 평가한 결과를, 로컬 폴더 안 "리드 리포트" 서브폴더에 "리드평가-한빛테크-YYYY-MM-DD.md" 파일로 저장해줘.
```

> **Tip:** 연결이 많아질수록 프롬프트에 "어느 도구를 써야 한다"라고 지정하지 않아도 Quick이 알아서 필요한 커넥터를 골라서 씁니다.

---

## 문제가 생기면

- **인증 실패**: 회사 계정으로 다시 로그인. OAuth 토큰은 90일마다 만료됩니다.
- **커넥터가 목록에 없음**: 조직 관리자에게 활성화 요청이 필요합니다.
- **데이터가 안 옴**: Settings에서 해당 커넥터 권한 범위를 다시 확인하세요.

---

> **다음:** [STEP 5. Quick 차별 기능 →](step-5-quick-features.md)
